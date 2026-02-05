# Gazebo Aircraft Models — Agent Guidance

This directory contains SDF model definitions for Gazebo Harmonic simulation.
Each subdirectory is a complete model with geometry, physics, sensors, and plugins.

## Context

- **Parent guidance:** `px4-gazebo-models/AGENTS.md` (vendor submodule — read only)
- Models are loaded via `PX4_GZ_MODEL_PATH` environment variable.

## Key models for this project

| Model | Type | Notes |
|-------|------|-------|
| `x500/` | Quadrotor | Default test vehicle, used by `takeoff_land.py` |
| `x500_depth/` | Quadrotor + depth camera | Vision-based navigation variant |
| `standard_vtol/` | VTOL | Fixed-wing + multirotor hybrid |
| `advanced_plane/` | Fixed-wing | Airplane with control surfaces |
| `r1_rover/` | Ground vehicle | Wheeled rover model |

## Model structure

Each model directory typically contains:
```
model_name/
├── model.sdf          # Full model definition (links, joints, sensors, plugins)
└── model.config       # Metadata (name, author, description)
```

## What agents should do here

- **Read** SDF files to understand vehicle geometry, mass properties, sensor placement
- **Reference** model names when configuring `PX4_GZ_MODEL` for simulation runs
- **Compare** models to understand differences between variants (e.g. x500 vs x500_depth)

## What agents must not do

- Do not modify SDF files — changes to physics params affect all simulation results
- Do not add new models without human approval and corresponding airframe definitions
- Do not change sensor plugin configurations