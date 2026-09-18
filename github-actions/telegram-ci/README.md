# Telegram CI Notification

A small reusable GitHub Actions package for sending CI results to Telegram.

The intended behavior:

- Success: `<7-character SHA> PASS`
- Failure: identify the failed CI stage, capture a concise error summary, and send it to Telegram.
- Telegram bot token and chat ID stay in each repository's GitHub Actions secrets.
- No bot token, chat ID, or other private credential belongs in this package.

## Quick start

Copy the pattern below into the repository's workflow and replace the example CI commands with the project's real stages.

```yaml
name: CI

on:
  push:
  pull_request:

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - name: Install dependencies
        run: |
          # Project-specific setup.

      - name: Test
        id: test
        continue-on-error: true
        run: |
          set -o pipefail
          <your test command> 2>&1 | tee "$RUNNER_TEMP/test.log"

      - name: Build
        id: build
        continue-on-error: true
        run: |
          set -o pipefail
          <your build command> 2>&1 | tee "$RUNNER_TEMP/build.log"

      - name: Determine CI result
        id: result
        if: always()
        shell: bash
        env:
          TEST_OUTCOME: ${{ steps.test.outcome }}
          BUILD_OUTCOME: ${{ steps.build.outcome }}
        run: |
          if [ "$TEST_OUTCOME" = "failure" ]; then
            echo "status=failure" >> "$GITHUB_OUTPUT"
            echo "failed_step=Test" >> "$GITHUB_OUTPUT"
            echo "log_file=$RUNNER_TEMP/test.log" >> "$GITHUB_OUTPUT"
            exit 0
          fi

          if [ "$BUILD_OUTCOME" = "failure" ]; then
            echo "status=failure" >> "$GITHUB_OUTPUT"
            echo "failed_step=Build" >> "$GITHUB_OUTPUT"
            echo "log_file=$RUNNER_TEMP/build.log" >> "$GITHUB_OUTPUT"
            exit 0
          fi

          echo "status=success" >> "$GITHUB_OUTPUT"

      - name: Telegram notification
        if: always()
        uses: Rennll/ai-collaboration/github-actions/telegram-ci@main
        with:
          status: ${{ steps.result.outputs.status }}
          failed-step: ${{ steps.result.outputs.failed_step }}
          log-file: ${{ steps.result.outputs.log_file }}
          bot-token: ${{ secrets.TELEGRAM_BOT_TOKEN }}
          chat-id: ${{ secrets.TELEGRAM_CHAT_ID }}
```

## Adding more CI stages

Give each meaningful stage:

1. a stable `id`;
2. `continue-on-error: true`;
3. a log file under `$RUNNER_TEMP`.

Then add its outcome to the result step. Check stages in the order in which they should be reported.

This pattern deliberately keeps project-specific CI commands in the project. The shared package only handles Telegram delivery and the standard message format.

## Secrets

Every consuming repository must create these Actions secrets:

- `TELEGRAM_BOT_TOKEN`
- `TELEGRAM_CHAT_ID`

The template never contains their values.

Pass only these two secrets to the action; do not broadly expose unrelated secrets.

## Security notes

Do not print the bot token or chat ID.

Treat captured CI logs as potentially sensitive. Only include a concise tail or test-summary section in Telegram; do not send the full log.

Do not expose Telegram secrets to scripts controlled by an untrusted pull request.

## Versioning

The quick-start example uses `@main) so the package can be adopted immediately. For long-lived projects, pin the action to a reviewed commit SHA or a maintained release tag.
