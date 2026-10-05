[requirements.md](https://github.com/user-attachments/files/33040960/requirements.md)
# DataMan Requirements Register

## Project Context

This project modernizes DataMan, a handheld math toy, into a math practice application. The primary users are students practicing independently, often with a teacher or parent nearby but not directly involved. Parents and teachers are secondary users who want to understand what a learner practiced and whether progress is happening.

## Evidence Notes

| ID | Evidence | Source |
|---|---|---|
| E-01 | Teachers report that students may pause practice and return later, and they want a learner's saved practice state to remain available after leaving and returning. | Elicitation case |
| E-02 | The primary learner is a student practicing independently, often with a teacher or parent nearby. Exact device and access conditions have not yet been confirmed. | Elicitation case |
| E-03 | Adults want to understand what the learner practiced and whether progress is occurring. Stakeholders have not agreed on a detailed reporting dashboard. | Elicitation case |
| E-04 | Students may use DataMan on school Chromebooks, phones, tablets, and home computers, and some sessions may be interrupted before intentional sign-out. | Simulation complication |
| E-05 | The original DataMan Answer Checker lets a learner enter an answer to a math problem and indicates whether it is correct. | DataMan manual, Answer Checker |

## Functional Requirements

**FR-01:** The system must allow a learner to submit an answer to a math problem and receive feedback on whether the answer is correct.
*Source/Rationale:* Original Answer Checker behavior (E-05) and the learner's need for immediate feedback while practicing independently (E-02).

**FR-02:** The system must automatically save a learner's practice state throughout a session, without requiring the learner to manually save or sign out.
*Source/Rationale:* Teachers want practice state preserved (E-01), and sessions may end unexpectedly before sign-out (E-04). Saving only on exit would fail in the situations where saving matters most.

**FR-03:** The system must restore a learner's most recently saved practice state when the learner returns to the application.
*Source/Rationale:* Students pause and return later, and teachers want their saved state to remain available (E-01).

**FR-04:** The system must record which problems a learner practiced and whether each answer was correct.
*Source/Rationale:* Adults want to know what was practiced and whether progress is occurring (E-03). That cannot be shown unless practice activity is recorded.

**FR-05:** The system must allow a parent or teacher to review a learner's practice activity and results after a session, without needing to observe the session in real time.
*Source/Rationale:* Adults want visibility into practice and progress (E-03), and the learner often practices without direct adult involvement (E-02). The format of this review is intentionally left open (see Open Questions).

## Non-Functional Requirements

**NFR-01 (Reliability):** If a session ends unexpectedly, all answers the learner submitted before the interruption must still be present when the learner returns.
*Source/Rationale:* Sessions may be interrupted by a closed Chromebook, a dead battery, or a lost tab (E-04), and the core stakeholder need is that students do not lose their work (E-01).

**NFR-02 (Usability):** A student must be able to start, complete, and resume a practice session without help from an adult.
*Source/Rationale:* The primary learner practices independently, with adults nearby but not hands-on (E-02).

**NFR-03 (Compatibility):** The system must be usable on the device types students are expected to use: school Chromebooks, phones, tablets, and home computers.
*Source/Rationale:* The simulation complication identifies these devices (E-04). Exact access conditions are still unconfirmed (E-02), so details are tracked under Open Questions.

## Open Questions / Assumptions

- **Format of parent/teacher visibility:** Stakeholders have not agreed on a dashboard (E-03). A dashboard is a proposed solution, not a confirmed requirement.
- **Device and access conditions:** Will DataMan run in a browser or as an installed app? Will students always have an internet connection? (E-02)
- **Persistence duration:** How long must saved practice state remain available after a learner leaves?
- **Cross-device continuity:** Must saved progress follow a learner from one device to another, such as from a school Chromebook to a home computer? The evidence does not yet say.
- **Definition of progress:** What counts as "progress" for parents and teachers (accuracy over time, topics covered, time spent) has not been defined.
- **Learner identification:** The complication mentions "sign-out," which implies accounts, but how learners and adults are identified has not been confirmed.
- **Student data privacy:** Because the system stores information about students, privacy expectations likely apply, but no specific constraint has been gathered from stakeholders yet.
- **Proposed DataMan 2.0 features:** Adapting questions toward a learner's weakest topics, requiring learners to explain their reasoning, and a missed-question bank for parents and teachers are design ideas, not confirmed stakeholder needs. They need supporting evidence before becoming requirements.
