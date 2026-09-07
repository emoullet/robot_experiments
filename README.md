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
