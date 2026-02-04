# PX4-Gazebo-Models — Agent Guidance

This is a **forked submodule** containing Gazebo simulation models used by PX4 SITL.
Agents operating in this directory must follow different rules than the parent repo.

---

## Ownership and authority

- **Upstream:** [PX4/PX4-gazebo-models](https://github.com/PX4/PX4-gazebo-models)
- **Fork:** lpurdy01/PX4-gazebo-models
- Models are resolved at runtime via `PX4_GZ_MODEL_PATH`.

## What agents must NOT do here

- **Do not commit directly** to this submodule
- Do not modify existing upstream model definitions (SDF, config) without human approval
- Do not add new models without explicit instructions
- Do not alter world files used by CI without verifying headless compatibility

## What agents may do here

- **Read** model definitions (SDF/URDF) for reference when writing scenarios or docs
- **Inspect** world files to understand available environments
- **Reference** model parameters (mass, inertia, sensor config) in parent repo code
- **Propose changes** via the patch process defined in the root `AGENTS.md`

## Key directories for reference

| Path | Purpose |
|------|---------|
| `models/` | Aircraft model definitions (SDF) |
| `worlds/` | Gazebo world environments |
| `simulation-gazebo/` | Gazebo plugin source |
| `tools/` | Model utilities |

## Model usage

The default test model is **x500** (quadrotor). Models are loaded by PX4 SITL via:
```
PX4_GZ_MODEL=x500 make px4_sitl gz_x500
```

Available worlds are documented in `/tools/GAZEBO_WORLDS.md` in the parent repo.

## Cross-reference

- Parent repo rules: `/AGENTS.md` (root)
- Patch process: `/AGENTS.md` section 5
- World documentation: `/tools/GAZEBO_WORLDS.md`
