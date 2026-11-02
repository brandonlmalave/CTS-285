

# M4 Lab Evidence Record

## Answer Flow Lab
**Initial design decision tested:** Two-attempt rule location

**Scenario that exposed the issue:** Wrong, then correct

### Consequence Observed
Second-try success was recorded the same as first-try success. The interrupt reset the attempts, and the rule couldn’t be reused outside that screen. Three of five checks failed.

### Revision Made
I moved the rule to reusable business logic, stored separate Attempt records with try_number, and saved them through a data boundary. The curator has to be able to tell attempt outcomes apart.

### What Changed After Revision
All five checks passed. Second-try success was distinguishable and survived the interrupt.

---

## Memory Bank & Curator Retrieval Lab
**Initial design decision tested:** Attempt/session/result storage

**Scenario that exposed the issue:** Curator retrieves prior learner results

### Consequence Observed
Only final_score was stored, with no link to a learner or session. When the curator tried to retrieve prior results, there was no way to tell which problems were missed, and the result didn’t persist after the session.

### Revision Made
I stored Attempt(problem_id, try_number, correct, session_id) records tied to a persistent Session/Result linked to the Learner. The curator’s query needs problem-level attempts connected to a learner and session.

### What Changed After Revision
All five checks passed. The curator could retrieve which problems the learner missed, and the results persisted after the session closed. Still open: how learners and curators are identified.

---

## Cross-Lab Finding
Reading the requirements, “record the result” seemed like enough. But when I ran the labs, saving only the final result meant I couldn’t tell a second-try fix from a first-try answer, I couldn’t see which problems were missed, and an interruption wiped everything. The curator could only look things up later once I saved each attempt per problem, linked to a learner and session, and put the rules in business logic instead of the screen.

## Revised / New Design Question
For US-02, what do I actually need to save for each attempt and session so a parent or teacher can later see which problems a learner missed (US-05), and how do I know which learner it is (Q-01)?
