# DataMan Product Backlog

## Sources

This backlog uses these files from my repository:

- `docs/requirements.md`
- `docs/decisions/m3-backlog-triage-record.md`
- `docs/decisions/m3-product-owner-decision-record.md`

## Priority Order

1. US-01
2. US-02
3. US-03
4. US-04
5. US-05

## Stories

### US-01 — Check an answer and get feedback

**Requirement ID:** FR-01, NFR-02, NFR-03

**User Story:** As a learner practicing on my own, I want to submit an answer and immediately see whether it is correct so that I know how I'm doing without waiting for an adult.

**Acceptance Criteria:**

- Given a math problem is shown, when the learner submits an answer, then the system shows whether the answer is correct or incorrect.
- Given the learner has submitted an answer, when feedback is shown, then it appears before the learner moves to the next problem.
- Given a learner opens the application, when they start a problem and submit an answer, then they complete it without help from an adult.
- Given the learner is on a school Chromebook, phone, tablet, or home computer, when they submit an answer, then feedback is shown the same way on each device.

**Relative Effort:** S — The smallest story in the backlog; it carries over the original Answer Checker behavior and has no open questions.

**Dependency / Constraint:** None. Must work on the expected device types (NFR-03).

**Priority:** 1

**Readiness:** Move Forward

**Priority Rationale:** High value, small effort, and no dependencies. It is the core learning loop from the original DataMan (E-05), and every other story depends on it, so building it first unlocks the rest of the backlog.

---

### US-02 — Record practice activity

**Requirement ID:** FR-04

**User Story:** As a parent or teacher, I want each practiced problem and its result recorded so that there is a reliable history of what the learner practiced.

**Acceptance Criteria:**

- Given a learner submits an answer, when the answer is checked, then the problem and whether the answer was correct are recorded.
- Given a learner answers 5 problems in a session, when the record is checked, then it lists all 5 problems and the result for each.

**Relative Effort:** S — Similar in size to US-01; it records results the answer check already produces.

**Dependency / Constraint:** US-01 (answers must exist before they can be recorded).

**Priority:** 2

**Readiness:** Move Forward

**Priority Rationale:** Small and ready, with a dependency that is already first in line. It shows nothing to adults yet, but it collects the data US-05 needs, so building it now reduces rework later. It ranks below US-01 because it depends on it.

---

### US-03 — Save practice automatically

**Requirement ID:** FR-02, NFR-01

**User Story:** As a learner, I want my practice saved automatically as I work so that I don't lose my answers if my session suddenly ends.

**Acceptance Criteria:**

- Given a learner has submitted answers, when the session ends without sign-out (tab closed, device shut, battery dies), then every answer submitted before the interruption is still saved.
- Given a learner is practicing, when they submit answers, then their work is saved without the learner pressing a save button or signing out.

**Relative Effort:** M — Larger than US-01 and US-02 because saving must survive unexpected interruptions, and the scope may grow once open questions are answered.

**Dependency / Constraint:** US-01. Blocked by open questions Q-01 (learner identification) and Q-02 (persistence duration).

**Priority:** 3

**Readiness:** Refine

**Priority Rationale:** Highest stakeholder value after the core loop, because teachers do not want students losing work (E-01, E-04). But saving "a learner's" state depends on how a learner is recognized, which is not decided. Committing now risks rework, so it stays in Refine until Q-01 and Q-02 are answered.

---

### US-04 — Resume where I left off

**Requirement ID:** FR-03, NFR-02

**User Story:** As a learner, I want to pick up where I left off when I come back so that I don't have to start over.

**Acceptance Criteria:**

- Given a learner has saved practice state, when they return to the application, then their most recently saved state is shown.
- Given a learner returns to the application, when their saved state is shown, then they can continue practicing without help from an adult.

**Relative Effort:** M — Similar to US-03, but it could become L if progress must follow a learner across devices (Q-03).

**Dependency / Constraint:** US-03. Blocked by Q-01 (learner identification). Scope depends on Q-03 (cross-device continuity).

**Priority:** 4

**Readiness:** Refine

**Priority Rationale:** Completes the "don't lose my work" need, but it cannot be restored before it is saved, so it ranks after US-03. Cross-device continuity is the biggest uncertainty in the backlog and could change its size, so it stays in Refine rather than being treated as ready.

---

### US-05 — Review practice after a session

**Requirement ID:** FR-05

**User Story:** As a parent or teacher, I want to review what a learner practiced and how they did after a session so that I can follow their progress without watching in real time.

**Acceptance Criteria:**

- Given a learner completed a session, when a parent or teacher reviews it later, then they can see which problems were practiced and whether each answer was correct.
- Given a learner practiced without an adult present, when the adult reviews the session afterward, then the same results are available as if they had been watching.

**Relative Effort:** L — The largest and least certain story; its format, its definition of progress, and adult access are all unsettled.

**Dependency / Constraint:** US-02. Blocked by Q-04 (review format), Q-05 (definition of progress), Q-01 (how adults are identified), and Q-06 (student data privacy).

**Priority:** 5

**Readiness:** Defer

**Priority Rationale:** A real stakeholder need (E-03), but too many details are unresolved to estimate or test it well. Because US-02 already records the activity data, deferring this story loses nothing. Revisit once stakeholders agree on the review format and what "progress" means.

---

## Open Questions Carried Forward

- **Q-01 — Learner identification:** US-03, US-04, and US-05 wait on this. Saving, restoring, and reviewing work all depend on knowing which learner (and which adult) is using the system.
- **Q-02 — Persistence duration:** US-03 waits on this. How long saved state must last affects what "saved" means.
- **Q-03 — Cross-device continuity:** US-04 waits on this. If progress must follow a learner between devices, the story grows significantly.
- **Q-04 — Format of parent/teacher visibility:** US-05 waits on this. A dashboard is a proposed solution, not a confirmed requirement, so no dashboard story exists.
- **Q-05 — Definition of progress:** US-05 waits on this. Stakeholders have not defined whether progress means accuracy, topics covered, or time spent.
- **Q-06 — Student data privacy:** US-02 and US-05 are affected. No specific privacy constraint has been gathered yet.
- **Q-07 — Device and access conditions:** Affects all stories through NFR-03. Whether DataMan runs in a browser or as an app, and whether it needs internet, is unconfirmed.
- **Q-08 — Proposed DataMan 2.0 features:** No stories exist for adaptive questions, explaining reasoning, or a missed-question bank. They are design ideas without stakeholder evidence, so they stay out of the backlog until validated.

## Revisions After Triage and Release Planning

- **US-03 and US-04 — kept in Refine instead of Move Forward — Backlog Triage record.** In triage, saving learner progress was deferred once the identity approach was not ready. The same dependency exists here (Q-01), so these high-value stories are not treated as ready.
- **US-01 — ranked first — both records.** Immediate feedback was required for the first release in triage, and the Product Owner simulation put core, ready work first. US-01 follows the same reasoning.
- **US-05 — Defer — both records.** Both simulations deferred reporting work with unsettled scope (the analytics dashboard and the parent dashboard). US-05 is deferred for the same reason, and the dashboard idea stays out of the backlog.
- **US-02 — moved up to Move Forward — Product Owner decision record.** The release-planning simulation showed the value of moving work that unlocks later items. Recording activity now keeps US-05 from needing rework later.
