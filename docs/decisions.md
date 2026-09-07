# Decisions and current status

Decisions agreed on September 7, 2026:

- An umbrella repository and independent experiment repositories connected through submodules.
- Experiment dependencies pinned to commits, including nested submodules.
- Personal setup under emoullet; no changes to ISIR-EXTENDER.
- Collaborative discussion in Drive; the applicable protocol versioned in Git.
- A local web interface that starts the entire stack, supervises it and runs sessions.
- Local data storage outside Git, with optional Drive sharing after finalization.
- Identities kept in a register separate from experimental data.
- Repository content, filenames, comments and GitHub metadata written in English.

## Status

Initial repository structure and documentation. Snake-specific decisions,
agreed parameters and open questions are in `snake/protocol/` and
`snake/docs/work_status.md`. The interface, supervisor, acquisition and analysis
still need implementation. No version has been declared validated on the robot.

The names `exp_snake` and `dependencies/` are initial structural conventions.
Snake is private; the umbrella repository retains its existing public visibility.

## Next step

Resolve the technical questions in the Snake repository, then build a minimal
simulation workflow: fictitious participant, session, trial, acquisition,
report and plot. Organizational migration and scientific publication are outside
the scope of this setup.
