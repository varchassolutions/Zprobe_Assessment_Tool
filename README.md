# ZProbe — Impedance Scanning & Stability Assessment

**Official releases of the ZProbe Assessment Tool by
[Varchas Solutions](https://www.varchassolutions.com.au/).**

This repository hosts the **release packages only** (no source). Download the
latest `ZProbeApp_standalone_v<ver>.zip` from the
[Releases page](https://github.com/varchassolutions/Zprobe_Assessment_Tool/releases),
verify it against `SHA256SUMS.txt`, unzip anywhere on a Windows 10/11 x64 PC —
**no Python, no internet, no admin rights needed** — and double-click a
launcher:

| Launcher | What it does |
|---|---|
| `ZProbe Desktop.bat` | opens the app in its own native window |
| `ZProbe Browser.bat` | opens the app in your default browser |
| `Create Desktop Shortcut.bat` | puts a ZProbe icon on the desktop |

First start takes a few seconds (the embedded Python warms up).

## What's inside

- Embedded CPython 3.12 runtime + all libraries (streamlit, plotly, numpy,
  matplotlib, openpyxl, pywebview) — fully offline, fully self-contained.
- The ZProbe app: free-form impedance-matrix composition (single / sum /
  product / blockdiag / parallel / subtract / loopgain / closedloop /
  multiport / expression), Bode, eigenvalues / Generalized Nyquist,
  participation, singular values / condition number, passivity, loop &
  disk margins, what-if sweeps, vector fitting (SISO + common-pole MIMO
  with state-space export), Excel / PDF reports, headless batch API,
  built-in self-update.

## Try it in ten minutes — worked examples

Download
[**`ZProbe_Examples.zip`**](https://github.com/varchassolutions/Zprobe_Assessment_Tool/releases/latest/download/ZProbe_Examples.zip):
three ready-to-open studies (a healthy IBR connection, a weak-grid ~38 Hz
PLL oscillation you can diagnose and retune in the What-if tab, and a
two-plant multi-port system with cross-coupling), plus a step-by-step guide
([`EXAMPLES_GUIDE.pdf`](https://github.com/varchassolutions/Zprobe_Assessment_Tool/releases/latest/download/EXAMPLES_GUIDE.pdf),
also included in the zip) that walks every analysis tab and composition
mode with verified expected results. Unzip, point the app's *Project root
folder* at the folder, and follow the guide. The examples are regenerated
and re-certified against every release, so these links always match the
latest version.

## Data it reads

Point the sidebar's *Project root folder* at a folder of case folders, each
holding `matrices/impedance_side1.npz` / `impedance_side2.npz` produced by the
ZProbe extraction pipeline.

## Updating

The app checks this repository's latest release on start (sidebar **Updates**
expander) and can download, verify (SHA-256) and stage the update itself;
you apply it with the generated `Apply Update.bat` after closing the app.
The previous version is kept as `app_previous/` for rollback. Air-gapped
machines: download `ZProbeApp_update_v<ver>.zip` manually. Set
`ZPROBE_NO_UPDATE_CHECK=1` to disable all checks.

## Verification

Every release is built from a validated source state and re-verified **inside
the shipped package** (the build aborts otherwise): the packaged Python re-runs
the application's self-validation suite after packaging. Always check your
download against `SHA256SUMS.txt`.

## License / use

© [Varchas Solutions](https://www.varchassolutions.com.au/). Licensed
material — use as agreed with Varchas Solutions. The compiled modules may
not be reverse-engineered, modified or redistributed.
