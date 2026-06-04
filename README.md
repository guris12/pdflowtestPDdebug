# pdflowtestPDdebug

Minimal repo to smoke-test **Ondevtra CI workflow debugger**  
(https://vlsi.ondevtra.com/dashboard/debug).

## What this does

1. GitHub Actions creates fake ORFS-shaped output dirs: `logs/`, `reports/`, `results/`.
2. `actions/upload-artifact` attaches them to the workflow run.
3. In the dashboard: connect `guris12/pdflowtestPDdebug` → pick run → artifact → ask a question.

No real OpenROAD run required for the first test.

## Run the workflow

GitHub → **Actions** → **PD debug smoke (dummy flow outputs)** → **Run workflow**.

## Dashboard E2E

1. Sign in with GitHub at https://vlsi.ondevtra.com/auth/login (needs `repo` scope).
2. Open https://vlsi.ondevtra.com/dashboard/debug
3. **Add** → `guris12/pdflowtestPDdebug`
4. Select the latest **RUN** and artifact **orfs-flow-outputs**
5. Ask: *Which flow stages completed? Summarize the logs.*

## Next: real ORFS

Replace the “Generate dummy ORFS outputs” step with your real `make` / container flow, then keep the same `upload-artifact` step.
