# pdflowtestPDdebug

Minimal repo to smoke-test **Ondevtra CI workflow debugger**  
(https://vlsi.ondevtra.com/dashboard/debug).

## What this does

1. GitHub Actions creates an **ORFS-shaped** tree under `logs/sky130hd/gcd/base/`, `reports/…`, `results/…` (stage logs `1_`–`6_`, STA report with **WNS −0.12 ns**).
2. `actions/upload-artifact` uploads artifact **`orfs-flow-outputs`**.
3. Dashboard: https://vlsi.ondevtra.com/dashboard/debug → connect this repo → run → ask.

No container required for the smoke test.

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
