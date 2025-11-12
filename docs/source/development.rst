Development
===========

This project uses `uv <https://docs.astral.sh/uv/>`_ for dependency management and `Ruff <https://docs.astral.sh/ruff/>`_ for linting. The following checklist helps you get a local environment ready for contributions.

Prerequisites
-------------

* Install uv (``curl -LsSf https://astral.sh/uv/install.sh | sh``) or ``pip install uv``.
* Ensure Python 3.10+ is available; uv can install it automatically if needed.

Bootstrap the environment
-------------------------

Create a virtual environment with the dev + test groups:

.. code-block:: console

    uv sync --group dev --extra tests

Common tasks
------------

Run tests:

.. code-block:: console

    uv run pytest

Lint (with autofix) and format:

.. code-block:: console

    uv run ruff check src tests --fix
    uv run black src tests

Update dependencies when ``pyproject.toml`` changes:

.. code-block:: console

    uv lock

Keeping ``uv.lock`` committed ensures CI and local machines resolve identical versions.
