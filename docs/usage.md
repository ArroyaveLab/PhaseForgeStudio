# Usage

## Running a job

1. Set **Species** and **Lattices** in the Configure panel
2. Choose a **Calculator** (GRACE, MACE, CHGNet) and device
3. Click **Run** — the job name (e.g. `AlNiFe BCC_A2 #1`) appears in the header
4. Watch the structure relax live in the Visualize panel; click **⬤ Live** to auto-follow

## Trajectory playback

- Use the slider to scrub through relaxation frames
- Dragging away from the last frame pauses live mode
- Dragging back to the last frame resumes it
- Click **▶** to play back at 5 fps

## Energy chart

Switch modes with the tab buttons above the chart:

| Mode | Shows |
|------|-------|
| **all** | Final energies for all compositions, sorted by composition |
| **step** | Per-step convergence curve for the selected structure |
| **all in system** | All step curves for the same composition system overlaid |

## Phase diagrams

Click a `.tdb` file in the Outputs panel → click **Generate Phase Diagram**. For N-component systems, all C(N,2) pseudo-binary sections are generated and saved as PNGs alongside the TDB file.

## BLADE workspace

Click the **BLADE** tab in the header to switch to the full BLADE pipeline dashboard. The BLADE dashboard loads in an embedded frame and shows the same SQS, TDB, Plots, and Config views as the standalone BLADE dashboard server.

Configure the BLADE workspace in the Configure panel:

- **BLADE path1** — the BLADE staging directory (`Files/`, jobs, logs); defaults to your PhaseForge `path1` if left blank
- **BLADE TOML config** — relative path to the TOML config file pre-filled in the Config tab (default: `examples/full_framework.toml`)

Click the **Config** tab inside the BLADE view to load and edit your `full_framework.toml` settings as a structured form. Changes are written back to the file on disk without altering comments or formatting.
