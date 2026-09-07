# Robot experiments

Personal experiment umbrella repository under **emoullet**. Each experiment is
an independent repository referenced here as a submodule at a specific commit.
This setup does not modify repositories in the ISIR-EXTENDER organization.

| Experiment | Repository | Status |
| --- | --- | --- |
| Snake | [emoullet/exp_snake](https://github.com/emoullet/exp_snake) | Versioned planning documents and bringup draft; application not implemented |

## Clone the experiments

```bash
git clone --recurse-submodules https://github.com/emoullet/robot_experiments.git
```

The umbrella repository is public; some experiments and dependencies are private.
Recursive cloning requires the corresponding GitHub permissions. Clone the
umbrella repository without recursion to read the methodology without those permissions.

After switching versions, from a clean working tree:

```bash
git submodule update --init --recursive
```

Do not use `--remote` to reproduce a version: commits recorded in the parent
repositories are authoritative. Publish dependency commits first, then the
experiment commit, then its updated reference in this umbrella repository.
Build each experiment in a workspace separate from ongoing development.
`COLCON_IGNORE` prevents accidental discovery of these nested package copies.

## Verify the submodule checkout

Run from this repository's root:

```bash
git submodule status --recursive
git status --short
git submodule foreach --recursive 'git status --short'
```

The first character of each `submodule status` line describes its state:

| Prefix | Meaning |
| --- | --- |
| Space | Checked out at the commit recorded by its immediate parent |
| `-` | Not initialized |
| `+` | Checked out at a different commit |
| `U` | Merge conflict |

The short status commands also reveal modified or untracked files: a matching
commit alone does not prove a clean working tree. `foreach` prints repository
headings even when there are no changes. Names in parentheses in `submodule status`
are descriptive references, not necessarily active branches. Detached HEAD is
normal for pinned submodules.

To initialize missing submodules or restore the recorded versions, first preserve
any local work, then run:

```bash
git submodule update --init --recursive
```

This checks source retrieval, not compilation or robot behavior.
See the [Snake build instructions](snake/README.md#build-in-an-isolated-workspace)
and [dependency revision workflow](snake/dependencies/README.md#select-a-dependency-revision).
These links require the Snake submodule to be available.

## Record an updated experiment

Publish in dependency order: dependency commits, experiment commit, umbrella commit.
After committing and pushing a change in Snake, return to this repository's root:

```bash
git diff --submodule=log
git add snake
git commit -m "Update Snake experiment revision"
git push origin main
```

These publishing examples assume you are working on `main`; use your development
branch and review workflow when appropriate. Do not create experiment commits on
an unnoticed detached HEAD: check `git status` and create or switch to a working
branch first. Never publish a parent reference to a dependency commit that others
cannot fetch.

Reference: [Git submodule documentation](https://git-scm.com/docs/git-submodule).

## Methodology and decisions

- [Working methodology](docs/methodology.md): how Work, Drive, Codex and Git fit together.
- [Decisions and current status](docs/decisions.md): agreed choices and remaining work.
- Snake's scientific and operational details are in its private repository.

This repository catalogs experiment versions. Each experiment's own commit remains
the primary reference for identifying a session. Data and identity registers are
stored outside Git.

## Repository language

Write repository documentation, filenames, code comments, user-facing text and
GitHub metadata in English. Label translations of external sources explicitly
and link to the originals.
