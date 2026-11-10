# Configuration

PhaseForge Studio is configured via `config.json` (copy from `config.json.example`).

## Keys

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| `species` | list[str] | `["Al","Ni"]` | Element symbols |
| `lattices` | list[str] | `["FCC_A1"]` | ATAT lattice names |
| `calculator` | str | `"grace"` | Calculator name |
| `device` | str | `"cpu"` | `"cpu"` or `"cuda"` |
| `fmax` | float | `0.01` | Force convergence (eV/Å) |
| `t_min` | float | `298.15` | CALPHAD temperature range min (K) |
| `t_max` | float | `6000.0` | CALPHAD temperature range max (K) |
| `level` | int | `1` | SQS enumeration level |
| `md_scaling_matrix` | int or [x,y,z] | `2` | Supercell scale — scalar or per-axis list |
| `track_trajectory` | bool | `true` | Write per-step extxyz during relaxation |
| `path0` | str | — | Research root directory |
| `path1` | str | — | BLADE staging directory |
| `path2` | str | — | sqsdb base directory |
| `blade_path1` | str | — | BLADE staging directory for the BLADE workspace; defaults to `path1` when blank |
| `blade_toml` | str | `"examples/full_framework.toml"` | TOML config path pre-filled in the BLADE Config tab |
| `active_workspace` | str | `"phaseforge"` | Persisted workspace selection (`"phaseforge"` or `"blade"`) |

## Example

```json
{
  "species": ["Al", "Fe", "Ni"],
  "lattices": ["FCC_A1", "BCC_A2"],
  "calculator": "grace",
  "device": "cuda",
  "fmax": 0.01,
  "t_min": 298.15,
  "t_max": 6000.0,
  "level": 2,
  "md_scaling_matrix": [2, 2, 2],
  "track_trajectory": true,
  "path0": "~/Research",
  "path1": "~/Research/BLADE",
  "path2": "~/Research/PhaseForge/PhaseForge/atat/data/sqsdb",
  "blade_path1": "",
  "blade_toml": "examples/full_framework.toml",
  "active_workspace": "phaseforge"
}
```
