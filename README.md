# AI Checkout Funnel & Transaction Analyzer

A single-file, client-side tool that turns a payments transaction CSV into a checkout funnel, a drop-off view and a failure breakdown — with an optional AI layer for prioritisation and next steps.

**Live:** https://tiwarivault.github.io/failed-transaction-analyzer/

## What it does
- Upload a transactions CSV (auto-detects the status and failure-reason columns)
- **Checkout funnel:** Initiated → Attempted → Succeeded, with the drop-off at each stage and the biggest leak
- **Root-cause & pattern analysis:** breaks success rate down by every usable dimension (payment mode, bank/issuer, amount band) and surfaces the worst-performing segments and hidden patterns — e.g. "ICICI cards are 0% success (7/7 failed)" — with tailored recommended actions
- **Failure breakdown** by reason, ranked
- **Optional AI insights** (bring your own Claude API key)

## Deterministic engine vs AI layer
The counting, funnel, **segment analysis and pattern detection are all deterministic** — reproducible, not model-generated. The **AI layer is optional** and sits on top of those numbers: it reads the detected patterns and returns a prioritised, side-attributed action plan.

In short: the dashboard shows *what* failed **and finds the root-cause segment**; the AI explains *what matters most and what to do next*. It's a fast first-pass triage, not a replacement for log-level RCA.

## Privacy
Everything runs in your browser — your CSV never leaves your machine. In AI mode, only a short numeric summary (not raw rows) is sent to Anthropic with your own key.

## Note
Ships with fake sample data only. Portfolio project by Prashant Tiwari (payments support → AI).
