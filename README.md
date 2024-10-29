# Python template for libraries

Run the following to copy the template to `<destination-path>`:

```sh
pixi exec copier copy --trust https://github.com/maurosilber/python-lib-template <destination-path>
```

## What's inside?

- A `src` layout package with a `pyproject.toml` using `hatchling` as a build backend.
  The version is dynamically obtained from the git tag with `hatch-vcs`.

- A `pixi.toml` to manage tasks and dependencies with environments for linting, testing and building the package.

- Lint with `pre-commit` using:

  - `ruff` to check and format Python code,
  - `taplo` to format TOML files,
  - `mdformat` to format markdown files.

- A GitHub Action, `.github/workflows/ci.yml`, to test and publish the package.
  It is:

  - tested for different Python versions,
  - published to PyPI when the commit is tagged.

The `--trust` flag is needed to run the tasks defined in the `_tasks` key of `copier.yml`,
which creates a git repository with an initial commit
and installs the pre-commit hooks.
