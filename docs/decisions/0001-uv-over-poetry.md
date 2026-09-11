# 0001 — uv rather than other packages

- Status : Approved
- Date : 09/11/2026

## Context
The project needs a tool for:

Python version management
Virtual environment isolation
Dependency management
Reproducible installations
CI and local development

The project is currently Python-centric and its dependencies are available through the standard Python/PyPI ecosystem.

## Considered Options

### uv
Pros

Fast dependency resolution and installation
Manages Python versions, virtual environments, dependencies and lockfiles
Compatible with pyproject.toml and standard Python packaging
Well suited for CI and containerized environments

Cons

Newer than Poetry
Primarily focused on the Python ecosystem

### Poetry
Pros

Mature Python project-management workflows
Dependency locking and virtual-environment management
Good support for Python packaging

Cons

Do not provide a significant capability required by this project that uv does not already cover
Introduce their own project-management workflows and conventions

### Pixi
Pros

Can manage Python and non-Python dependencies
Strong reproducibility for Conda-based and multi-platform environments
Well suited for projects requiring native libraries, CUDA, or multi-language environments

Cons

Introduces the Conda ecosystem in addition to PyPI
Provides capabilities that are not currently required by this project


## Decision
Use uv as the primary tool for Python version management, virtual environments, dependency management and dependency locking.
uv provides the functionality required by the project with less tooling complexity than the alternatives considered.


## Reconsider decision if
Re-evaluate Pixi or another environment manager if the project starts requiring reproducible management of significant
non-Python dependencies, such as CUDA, native system libraries, or multi-language tooling.

