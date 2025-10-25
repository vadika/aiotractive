# AGENTS.md - aiotractive Developer Guide

## Commands
- **Lint**: `make lint` (runs black, isort, pylint, flake8)
- **Format**: `make format` (applies black and isort)
- **Individual linters**: `make black`, `make isort`, `make flake8`, `make pylint`
- **Build package**: `make dist`
- **CI command**: `pipenv run make` (default lint target)
- **No tests**: This project has no test suite currently

## Architecture
- **Type**: Async Python REST API client for Tractive pet tracking service
- **Main entry**: `aiotractive/tractive.py` - `Tractive` class (async context manager)
- **Core modules**: `api.py` (HTTP/auth), `tracker.py`, `trackable_object.py`, `channel.py` (event streaming)
- **Dependencies**: `aiohttp>=3.8.1`, `yarl>=1.7.2`

## Code Style
- **Line length**: 120 chars (black, isort, flake8, pylint)
- **Target**: Python 3.9+
- **Imports**: Use relative imports within package (e.g., `from .api import API`)
- **Docstrings**: Not required (disabled in pylint)
- **Error handling**: Wrap exceptions in custom types (`TractiveError`, `UnauthorizedError`, `NotFoundError`)
- **Formatting**: Use black and isort before committing
