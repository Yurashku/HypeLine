# Decision Log

This file records durable project decisions. It is not a diary and should not include every chat turn.

## D001 - Use artifact-based project memory

Status: accepted

Decision: ChatGPT sessions are working sessions. Durable project state is stored in repository artifacts.

Reason: Long chats accumulate obsolete versions, conflicting decisions, and noisy intermediate reasoning.

Impact: New sessions should start from `docs/context/CONTEXT_PACK.md`, not from raw chat history.

## D002 - Remove the Capability Block layer from current planning

Status: accepted

Decision: The current task structure does not use a `Capability Block` layer.

Reason: For external and practical work, a clear task with a concrete artifact is more useful than an additional abstract hierarchy level.

Impact: Task descriptions should focus on role, input, output, acceptance, and out-of-scope items.

## D003 - Replace broad effect forecasting with Expected ATE Prior

Status: accepted

Decision: The early scoring task estimates a cautious expected average treatment effect prior.

Reason: For hypothesis ranking, a rough direction/band/confidence estimate is more realistic than an exact forecast of a future pilot.

Impact: Scoring outputs should include `direction`, `rough_band`, `confidence`, `basis`, and `caveats`.

## D004 - Keep Targeting / Uplift / OPE as a separate post-pilot branch

Status: accepted

Decision: Targeting, uplift, HTE, and OPE are not part of the basic pre-pilot scoring loop.

Reason: These methods are valuable but have stricter data and validity requirements. Prematurely putting them into the core loop would overcomplicate the system.

Impact: They are handled as a separate research branch after post-pilot analysis.

## D005 - Use case-based and expert acceptance before heavy benchmarks

Status: accepted

Decision: Early quality checks should rely on worked cases, expert acceptance, and downstream usefulness.

Reason: Many artifacts do not yet have stable quantitative benchmarks. Artificial metrics would create noise and false confidence.

Impact: Each task should have realistic acceptance criteria rather than too many unsourced quality metrics.

## D006 - Add Project Canon as a control artifact

Status: accepted

Decision: The repository uses `docs/core/PROJECT_CANON.md` as a short human sanity-check artifact for the main project meaning.

Reason: The project has several useful documents, but distributed descriptions can drift. A compact control artifact helps the owner and future agents verify that the main ideas remain coherent.

Impact: Major architecture, scope, terminology, or artifact changes should be checked against the canon. If the canon conflicts with another document, the conflict should be resolved explicitly rather than left as competing project meanings.
