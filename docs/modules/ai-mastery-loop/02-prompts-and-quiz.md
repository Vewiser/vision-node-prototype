# 02 // AI Coach, Quiz, and Study Prompts

These prompts turn AI into a coach. Replace placeholders and remove private information before use.

## Explain without taking over

```text
Explain [CONCEPT] in three layers:

1. Like I am completely new
2. Like I am operating Vision Node
3. Like I am preparing to support a client

Include:
- What it is
- Why it exists
- What it connects to
- One safe example
- One common mistake
- How I can verify it myself

Do not give me a command to run until I explain the concept back to you.
```

## Compare two concepts

```text
Help me compare [A] and [B].

Use a table with:
- Purpose
- Where it runs
- What it controls
- Typical failure
- Security risk
- Vision Node example
- How to choose

Then ask me to explain the difference without looking.
```

## Command interpreter

```text
I am studying this command:

[REDACTED COMMAND]

Do not execute it.

Break down every part:
- Program
- Options
- Arguments
- Input
- Output
- Required permissions
- What it changes
- How to preview or test safely
- How to validate the result
- How to reverse it when possible

Flag destructive, privileged, network-exposing, or cost-creating behavior.
```

## Socratic troubleshooting coach

```text
I am troubleshooting [PROBLEM] in an isolated lab.

Known-good state:
[STATE]

Observed symptom:
[SYMPTOM]

Sanitized evidence:
[EVIDENCE]

Do not give me the fix yet.

Ask one diagnostic question at a time. Help me separate:
- Symptom
- Evidence
- Hypothesis
- Test
- Cause
- Fix
- Validation
- Prevention

Stop if the next step could delete data, expose a service, increase cloud cost, affect another system, or require authorization.
```

## Closed-book quiz

```text
Give me a 10-question closed-book quiz on [TOPIC].

Include:
- 2 definitions
- 2 concept relationships
- 2 command/output interpretations
- 2 troubleshooting scenarios
- 1 security question
- 1 teach-back question

Ask one at a time.
Do not reveal answers early.
Score each response 0–2.
Track weak areas.
At the end, give:
- Total score
- Safety score
- Weak areas
- What to reread
- One practical lab
```

## Scenario drill

```text
Create a realistic but synthetic Vision Node scenario involving [TOPIC].

Give me:
- Goal
- Known-good state
- Symptom
- Sanitized evidence
- Constraints

Do not reveal the cause.
Let me investigate step by step.
Only provide evidence I explicitly request.
Score my final diagnosis, fix, validation, and prevention plan.
```

## Teach-back reviewer

```text
I will teach [TOPIC] in two minutes.

Evaluate my explanation for:
- Accuracy
- Clarity
- Missing ideas
- Unnecessary jargon
- Safety
- Practical usefulness

Do not rewrite it immediately.
First ask me to correct the weakest section myself.
```

## AI error audit

```text
Audit the explanation below.

[AI OUTPUT]

Create three sections:
1. Claims that are stable and likely correct
2. Claims that depend on version, provider, price, configuration, or date
3. Claims that require official verification

For each item in sections 2 and 3, identify the primary documentation source I should check.
Do not invent a source.
```

## Prompt discipline

A strong request includes:

- The single concept
- The source being studied
- Current understanding
- Known-good state
- Sanitized evidence
- Desired learning outcome
- Safety and cost boundaries
- What AI must not do yet

A weak request is simply:

> Fix this.

The purpose is to improve your thinking, not hide it.
