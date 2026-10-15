# AI Checkout Funnel & Transaction Analyzer

A single-file, client-side tool that turns a payments transaction CSV into a checkout funnel, a drop-off view and a failure breakdown — with an optional AI layer for prioritisation and next steps.

**Live:** https://tiwarivault.github.io/failed-transaction-analyzer/

## What it does
- Upload a transactions CSV (auto-detects the status and failure-reason columns)
- **Checkout funnel:** Initiated → Attempted → Succeeded, with the drop-off at each stage and the biggest leak
- **Failure breakdown** by reason, ranked
- **Optional AI insights** (bring your own Claude API key)

## Deterministic engine vs AI layer
The counting, funnel and grouping are **deterministic** — reproducible, not model-generated. The **AI layer is optional** and sits on top of those numbers: given the breakdown it returns which issues to prioritise by impact, whose side each is on (customer / integration / bank-PSP) and concrete next steps.

In short: the dashboard shows *what* failed; the AI explains *what matters most and what to do next*. It's a fast first-pass triage, not a replacement for log-level RCA.

## Privacy
Everything runs in your browser — your CSV never leaves your machine. In AI mode, only a short numeric summary (not raw rows) is sent to Anthropic with your own key.

## Note
Ships with fake sample data only. Portfolio project by Prashant Tiwari (payments support → AI).
