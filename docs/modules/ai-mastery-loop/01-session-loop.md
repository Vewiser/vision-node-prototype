# 01 // The Four-Stage Study Session

Use one loop for one concept. Keep the session small enough to finish.

## Session card

Before starting, complete:

```markdown
# Mastery Loop // YYYY-MM-DD

Topic:
Primary source:
Why it matters:
What I already think it means:
What I should be able to do afterward:
Safe lab:
Stop time:
```

## Stage 1 — Read

Read one bounded source section for 10–20 minutes.

Capture only:

- Five important terms
- Three main ideas
- One confusing point
- One real use case
- One risk or failure mode

Then close the source and write:

> In my own words, this means...

Do not ask AI for a summary before making the first attempt.

### Read gate

- [ ] I can name the purpose.
- [ ] I can define the key terms.
- [ ] I identified what I do not understand.
- [ ] I know what action this knowledge supports.

## Stage 2 — Ask AI

Give AI your explanation and ask it to evaluate the gaps.

Use:

```text
I am learning [TOPIC] from [PRIMARY SOURCE].

Here is my current explanation:
[YOUR EXPLANATION]

Act as a patient technical coach.

1. Identify what I understand correctly.
2. Point out missing or inaccurate ideas.
3. Explain the gaps in plain language.
4. Give one simple analogy and one practical Vision Node example.
5. Separate verified facts from inference.
6. Point me to the exact official documentation I should verify.
7. Do not give me the lab solution yet.
8. End with three questions I should be able to answer.
```

Continue asking focused questions:

- What problem does this solve?
- What happens underneath?
- What changes if this fails?
- What is commonly confused with it?
- How would I recognize it in a real system?
- What should I inspect before changing it?
- How would this differ on Ubuntu, Amazon Linux, Docker, or EC2?

### Ask gate

- [ ] My original explanation was corrected.
- [ ] I verified unstable or security-sensitive claims.
- [ ] I can explain the concept without repeating AI wording.
- [ ] I know what I will practice.

## Stage 3 — Quiz

Close the source, notes, terminal history, and AI explanation.

Request:

```text
Quiz me on [TOPIC].

Rules:
- Ask one question at a time.
- Start simple and increase difficulty.
- Mix definitions, scenarios, command interpretation, troubleshooting, and safety.
- Do not reveal the answer before I commit to mine.
- After each answer, score it 0–2:
  0 = incorrect or missing
  1 = partly correct
  2 = correct and clearly explained
- Explain only the gap.
- Keep a list of weak areas.
- Finish with one teach-back question and one practical challenge.
```

### Passing score

- Minimum: 16/20
- No safety question may score 0
- The teach-back must be understandable without jargon
- Failed questions return to Read and Ask AI

## Stage 4 — Apply

Complete one real action in a safe lab.

Use the progression:

1. Predict what will happen.
2. Run one action.
3. Observe the result.
4. Explain the result.
5. Validate against the expected state.
6. Create one safe failure.
7. Diagnose it from evidence.
8. Recover the system.
9. Repeat without copying.
10. Record proof.

### Hint ladder

If blocked, ask AI in this order:

1. Ask for a question that points toward the issue.
2. Ask which evidence to inspect.
3. Ask for the relevant concept.
4. Ask for pseudocode or a partial example.
5. Request the complete command only after attempting the solution.

### Apply gate

- [ ] I predicted the outcome.
- [ ] I completed the action.
- [ ] I understood the output.
- [ ] I recovered from one safe failure.
- [ ] I repeated the task without copying.
- [ ] I recorded sanitized proof.

## Close the loop

At the end, write:

- What I understand now
- What I still confuse
- What failed
- What fixed it
- What I can now do without AI
- When I will review it again

Schedule reviews for approximately:

- One day
- Three days
- Seven days
- Fourteen days
- Thirty days

Adjust the interval: weak recall returns sooner; strong independent performance returns later.
