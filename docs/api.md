# API Reference

PhaseForge Studio exposes a JSON HTTP API on the same port as the UI.

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/` | GET | Serve `index.html` |
| `/api/config` | GET / POST | Read / persist `config.json` |
| `/api/calculators` | GET | Available calculators with device/model flags |
| `/api/lattices` | GET | sqsdb lattice names |
| `/api/status` | GET | Job state, name, and elapsed time |
| `/api/jobs` | GET | Current job + history list |
| `/api/stream` | GET | SSE log + state events |
| `/api/run` | POST | Start pipeline |
| `/api/stop` | POST | Signal stop |
| `/api/structure` | GET | Latest structure as extxyz |
| `/api/live_structure` | GET | Most recent trajectory frame (live) |
| `/api/energies` | GET | Final energies sorted by composition |
| `/api/energies/system` | GET | All step-energy curves for a system |
| `/api/trajectory/xyz` | GET | Full multi-frame extxyz for a label |
| `/api/outputs` | GET | TDB / PNG listing |
| `/api/analyze` | POST | Run a MaterialsFramework analyzer |
| `/api/browse` | GET | File browser entries |
| `/api/convert_xyz` | GET | POSCAR → extxyz conversion |
| `/api/phase_diagram` | GET | Generate phase diagram PNGs from a TDB |
| `/files/<rel>` | GET | Serve file from `path1` |

## Workspace

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/switch_workspace` | POST | Persist `active_workspace` (`"phaseforge"` or `"blade"`) to config |

## BLADE routes

All BLADE dashboard endpoints are prefixed `/blade/`. The BLADE dashboard HTML is served at `/blade/` with all internal `/api/` calls transparently rewritten to `/blade/api/`.

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/blade/` | GET | BLADE dashboard (HTML with rewritten API prefix) |
| `/blade/api/status` | GET | Pipeline stage status |
| `/blade/api/sqs` | GET | SQS run tiles (10 parallel mcsqs jobs) |
| `/blade/api/structure` | GET | ATAT structure as XYZ for a given run |
| `/blade/api/trajectory` | GET | Live trajectory XYZ for a composition |
| `/blade/api/compositions` | GET | All compositions with stage-completion flags |
| `/blade/api/energy` | GET | Energy convergence data for a composition |
| `/blade/api/plots` | GET | Output PNG/GIF listing |
| `/blade/api/image` | GET | Serve image from BLADE `Files/` |
| `/blade/api/live_trajectory` | GET | Most recently modified trajectory file |
| `/blade/api/log` | GET | Last N lines of `nohup.out` |
| `/blade/api/toml` | GET | Raw TOML config text |
| `/blade/api/toml_read` | GET | Parsed TOML as JSON dict |
| `/blade/api/toml_write` | POST | Patch one or more TOML keys in-place (comment-preserving) |
