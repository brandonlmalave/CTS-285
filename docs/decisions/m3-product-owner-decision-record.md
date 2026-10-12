# M3 Product Owner Decision Record

## Scenario
StudyTrack release planning under constrained capacity.

## Round 1 — Capacity 13
- ST-01: Create a study task (3 pts)
- ST-02: Mark a study task complete (2 pts)
- ST-03: Recover a missed task (3 pts)
- ST-04: Keyboard-accessible task entry (2 pts)

**Why this release slice was defensible:**
All four items are high value, ready, and support the release goal. ST-01 is the foundation, ST-02 and ST-03 cover planning and recovery, and ST-04 makes task entry keyboard-accessible.

**One intentional deferral and why:**
ST-07, AI study recommendations. It’s 5 points and needs refinement, so committing now risks rework.

## Complication
Capacity dropped from 13 to 10 points. Keyboard accessibility testing revealed that task entry cannot reliably be completed with keyboard navigation, so ST-04 became release-critical.

## Revised Release Slice — Capacity 10
- ST-01: Create a study task (3 pts)
- ST-02: Mark a study task complete (2 pts)
- ST-03: Recover a missed task (3 pts)
- ST-04: Keyboard-accessible task entry (2 pts)

### Removed after complication
- None

### Added after complication
- None

**What changed and why:**
No items changed. ST-04 became required, and it was already in the plan. The capacity drop removed my 3-point buffer, but the core slice still fits exactly.

**Tradeoff accepted:**
I gave up all buffer, so any overrun has no room to absorb it. ST-05 also has to wait for a later release.

## Transfer to DataMan
Before finalizing your DataMan backlog, review whether any item is high value but not ready, depends on unresolved work, consumes disproportionate effort, or should move because it reduces risk or unlocks other work.
