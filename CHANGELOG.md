# Changelog

All notable changes to PhaseForge Studio are documented here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [1.1.0] — 2026-11-10

### Added
- BLADE workspace tab: switch between PhaseForge and the full BLADE pipeline dashboard (SQS, TDB, Plots, Config) via workspace tabs in the header
- BLADE Config tab: view and edit `full_framework.toml` settings as a structured form grouped by section; comment-preserving write-back via `patch_toml()`
- `/blade/api/*` route family: all BLADE dashboard endpoints served from the PhaseForge Studio process under `/blade/api/`, isolated from PhaseForge endpoints
- `blade_path1`, `blade_toml`, `active_workspace` config keys for BLADE workspace support
- `/api/switch_workspace` POST endpoint for workspace persistence
- Animated GIF generation for phase diagrams on ternary and higher-order systems (pycalphad + Pillow)
- `/api/delete` endpoint for deleting files from the Files/ tree with path-traversal protection
- Error display now shows full Python traceback in the analysis panel

### Fixed
- Phase diagram filter mismatch in the frontend energy chart ("all in system" Y-axis now rescales to include all compositions)
- 3D viewer zoom timing deferred to `requestAnimationFrame` to prevent zoom-before-render on tab switch
- Live button repositioned to page header for visibility; refactored to CSS class state management

## [Unreleased]

### Added
- In-memory multi-frame trajectory playback with ⬤ Live auto-follow mode
- Energy chart with three modes: all-compositions final energies, per-structure step convergence, all-in-system step curves overlaid
- On-demand phase diagram generation for binary and N-component TDB files via pycalphad
- Readable job names (`AlNiFe BCC_A2 #1`) with clickable history panel
- Real-time `updated HH:MM:SS` refresh badge
- Per-axis supercell scaling (x/y/z) inputs
- Composition-sorted SQS energy diagram
- Force vector overlay on 3D structure viewer
- 14 MaterialsFramework analyzers (EOS, elastic constants, Bain path, USFE, phonon, surface, NEB, …)
- File browser with POSCAR/CONTCAR/TDB/PNG inline preview
- SSH port-forwarding quickstart in README
