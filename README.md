# CareCaller_ps1
Call Quality Auto-Flagger: A system that automatically detects calls that require human review.

# Objective
Given a call's metadata, transcript, and Q&A responses, predict whether the call should be flagged for human review
(has_ticket = True). This is a binary classification task with a ~9% positive rate -- the challenge is catching subtle
anomalies across different issue types.
# What Counts as a Ticket?
Outcome miscategorization -- Call marked as wrong outcome (e.g., patient opted out but call says 'completed')
STT mishearing -- Speech-to-text errors on critical values (e.g., weight '62' instead of '262')
Agent skipped questions -- AI agent marked call complete but missed required health questions
Wrong number misclassification -- Patient said 'not interested' but classified as wrong_number
Agent gave medical advice -- AI agent violated guardrail by offering medical guidance
Data capture errors -- Responses recorded incorrectly despite patient giving correct answers
