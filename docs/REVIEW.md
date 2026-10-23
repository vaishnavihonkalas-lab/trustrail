# Prototype review — 23 October 2026

## Assessment

Suitable as an idea-stage interactive demonstration after the corrections below. It illustrates payment assurance and exception handling; it is not a working banking or Drunix integration. A functioning Drunix contract and regulated-partner validation remain important next-round work.

## Corrections made

- Calculator now accepts an annual rate in percent (18 means 18%), matching the initial ₹29,589 example. Invalid inputs show an explanation.
- Guided demo opens the selected order and progress controls, and restarts correctly after completion.
- Added delivery evidence during an open dispute without lifting the release freeze, fixing the pre-proof dispute dead end.
- Post-dispatch cancellation now opens a dispute instead of merely adding a review log while leaving payment eligible.
- Audit events no longer advance the simulated clock. The acceptance window cannot expire just because many actions were logged.
- Receipts retain the original payment confirmation timestamp.
- Added positive safe-integer paise/quantity checks and unit-price decimal validation.
- Added stored-state validation, role checks at modal submission, escaping of audit text, keyboard dialog focus handling and small-screen layout fixes.
- Replaced misleading `sha:` demo references with `demo-digest:` labels.
- Added regression tests and CI. Deployment stages only public application files and runs tests before publishing.

## Validation

`node --check app.js` and all 27 tests in `tests/workflow.test.cjs` passed. The suite evaluates the application script with a minimal DOM/storage harness; it verifies core transitions and selected handler/render behavior. It does not simulate browser layout, actual downloads, real signature verification, multiple tabs or real networks.

## Before presenting

1. Open the actual deployed site in an incognito window.
2. Complete all eight guided steps and view the receipt.
3. Demonstrate that disputes and unknown bank outcomes block another payout.
4. Confirm the layout on your phone and check receipt / JSON downloads.
5. Describe all integrations as simulated and the Drunix architecture as proposed.
