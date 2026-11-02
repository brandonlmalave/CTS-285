
# M4 Investigation Brief

## Product Slice
US-02 — Record practice activity

## Trace to Product Work
US-02 says each answer and whether it was correct must be recorded, but it doesn't say whether that means every attempt or only the final result. US-05 depends on that data later, so it needs to be decided now.

## Initial Design Question
**Question type:** Data / State

**Question:** Should the system record every attempt or only the final result per problem, so adults can review progress later?

## Why This Question Matters
Storing only the final result loses attempt details for good. US-05 would then need the data model rebuilt, and earlier history couldn't be recovered.

## Planned Evidence
- ERD / relationship model
- Field or state table

## Why This Evidence Is a Reasonable Starting Point
The question is about what data gets stored. A field table shows what's saved per submission, and an ERD tests whether a review question can actually be answered.

## Studio Check
During the DataMan Design Studio, record whether the evidence actually answered the question, whether you needed different evidence, and what new question emerged.
