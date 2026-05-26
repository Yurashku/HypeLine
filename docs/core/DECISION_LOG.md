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

Impact: Task descriptions should focus on concrete work products and downstream use.

## D003 - Replace exact effect forecasting with cautious hypothesis scoring

Status: accepted

Decision: The system must not pretend to predict the exact future pilot result.

Reason: Early hypothesis assessment should support prioritization, not claim proof before an experiment.

Impact: Effect estimates must remain cautious and explicit about uncertainty, basis, assumptions, and limitations.

## D004 - Keep Targeting / Uplift / OPE as a separate post-pilot branch

Status: accepted

Decision: Targeting, uplift, HTE, and OPE are not part of the basic pre-pilot scoring loop.

Reason: These methods are valuable but have stricter data and validity requirements. Prematurely putting them into the core loop would overcomplicate the system.

Impact: They are handled as a separate research branch after post-pilot analysis.

## D005 - Use case-based and expert discussion before heavy benchmarks

Status: accepted

Decision: Early quality checks should rely on worked cases, expert discussion, and downstream usefulness.

Reason: Many artifacts do not yet have stable quantitative benchmarks. Artificial metrics would create noise and false confidence.

Impact: Each task should have realistic quality discussion criteria rather than too many unsourced quality metrics.

## D006 - Add Project Canon as a control artifact

Status: accepted

Decision: The repository uses `docs/core/PROJECT_CANON.md` as a short human sanity-check artifact for the main project meaning.

Reason: The project has several useful documents, but distributed descriptions can drift. A compact control artifact helps the owner and future agents verify that the main ideas remain coherent.

Impact: Major architecture, scope, terminology, or artifact changes should be checked against the canon. If the canon conflicts with another document, the conflict should be resolved explicitly rather than left as competing project meanings.

## D007 - Treat AI Interviewer as a separate reusable tool

Status: accepted

Decision: AI Interviewer is a separate core task for dialogic filling of structured working materials.

Reason: The same scenario repeats across the project: the system has a target form, the user has partial knowledge, and the assistant should collect missing information through a non-intrusive dialogue.

Impact: AI Interviewer is not only a subpart of hypothesis moderation. It can support hypothesis formulation, metric selection, pilot interpretation, memory records, and other artifacts.

## D008 - Expand hypothesis ranking into multi-criteria priority assessment

Status: accepted

Decision: Hypothesis ranking is broader than expected ATE scoring.

Reason: A strong hypothesis should be business-relevant, testable, measurable, supported by evidence or analogues, reasonably safe, and useful for learning. Expected average effect remains important but is not the only criterion.

Impact: The research task portfolio uses “hypothesis quality and priority assessment” rather than a narrow expected ATE scoring task.
