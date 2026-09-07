# Working methodology — decisions of September 7, 2026

## Purpose

Link each result to what was evaluated and how it was evaluated:
protocol, sources, executables, parameters, setup, events and data.

## Organization

`robot_experiments` is an umbrella repository. Each experiment has an independent
repository and references its dependencies through submodules. Branches support
development; commits pin versions. Nested dependencies are also identified.
Versions must remain accessible to anyone authorized to reproduce an experiment.

Preparation takes place under the personal emoullet account. Any later migration
to ISIR-EXTENDER requires a separate decision.

## Work, Drive, Codex and Git

| Workspace | Responsibility |
| --- | --- |
| Work and Drive | Literature review, design, discussion, collaborative writing and interpretation |
| Codex and local repositories | Checking the actual code, feasibility, implementation and verification |
| Experiment Git repository | Applicable protocol versions, tools, configurations and dependency references |
| Local storage | Raw data and manifests; copying to Drive after finalization and verification |

Discussions can continue in either tool. Shared context consists of explicit
documents rather than assumed chat synchronization. A handoff records decisions,
their rationale, open questions, expected changes and how to verify those changes.
The researcher makes the scientific decisions.

Drive holds versions under discussion. Git preserves the versions applicable to
acquisitions. Editing Drive does not retroactively change a session. A proposal
generated in Work is not automatically an agreed decision.

## Workflow

1. Design: hypotheses, conditions, tasks, measurements and planned analysis.
2. Implement and pilot: instrumentation, interface, trials and documented adjustments.
3. Identify an experiment version: protocol, code, parameters and setup.
4. Acquire: record actual versions, phases, trials and deviations.
5. Analyze: identify input data, code and parameters; produce reproducible results.
6. Interpret and write with references to the generated results.

## Three distinct objects

- Experiment version: the intended definition of the protocol and system.
- Session: a pseudonymized participant's actual session using that version.
- Analysis: an identified processing run over a set of sessions, possibly performed later.

A commit captures neither local modifications nor the actual build.
Manifests must describe the environment that was really used. The approach to
build provenance and archiving local changes still needs implementation.

## Operation and data

The principal experimenter may have assistance. A local web application should
start and supervise the stack, guide sessions and provide analysis.
Software startup and motion authorization are separate.
The application operates independently of a Work/Codex conversation or connection.

Raw data are stored locally outside Git, with unique identifiers and temporally
aligned events and signals. Derived results can be regenerated.
Interruptions never delete previous acquisitions. The identity-to-pseudonym
register remains separate and is excluded from sharing exports.

Each experiment has a dedicated build workspace. Shared supervision and session
features will be considered based on Snake; no common framework is imposed yet.

## Language convention

Write repository content in English, including documentation, filenames,
comments, user-facing text, commit messages and GitHub descriptions.
Keep external-source provenance explicit: an English translation is labeled as a
translation, and the original remains available through its source link.
This convention does not require rewriting the history or pinned contents of
third-party dependency repositories.
