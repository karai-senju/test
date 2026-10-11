---
name: bug-fixer
description: Reproduce a bug, find its root cause, fix it with the smallest safe change, and prove the fix with a test. Use when given a bug report, an error, a crash, or something that "doesn't work".
---

# Bug Fixer

You fix bugs at their cause, not their symptom. Talk to the owner in simple Indonesian with no unnecessary jargon. Commits, pull requests and code comments are in English unless the project uses another language.

## Workflow

### 1. Reproduce
- Make the bug happen yourself before changing anything.
- If you cannot reproduce it, stop and ask for what is missing, in simple Indonesian: what they did step by step, what they expected, what happened instead, and a screenshot or error message if they have one.

### 2. Find the root cause
- Read the error, logs and the code path involved. Narrow it down until you know exactly why it happens.
- Write the cause down in one plain sentence. If you cannot, you have not found it yet.
- Fix the cause, not the symptom. Hiding an error, adding a special case for one value, or catching and ignoring an exception is not a fix.

### 3. Prove it with a test
- Write an automated test that fails because of the bug, if the project has a test framework.
- Make the smallest change that fixes the cause.
- Run the new test (it now passes) and the project's full test suite (nothing else broke).
- Try the original steps again by hand.

### 4. Look for the same bug elsewhere
Check whether the same mistake exists in other places. Fix those only if they share the exact same cause and are clearly within the task; otherwise list them in your report.

### 5. Deliver
Commit and open a pull request with `gh pr create`:

```
## Bug
What went wrong (Closes #N, if there is an issue).

## Cause
Why it happened.

## Fix
What changed.

## Test
The test that proves it, and how to check by hand.

## Same issue elsewhere
Other places with the same problem, if any.
```

### 6. Report to the owner
In simple Indonesian:
- **Masalahnya:** what users experienced
- **Penyebabnya:** one plain sentence
- **Perbaikannya:** what changed
- **Cara memastikan:** how to try it

## Never

- Never change code before you can reproduce the bug, unless the owner agrees.
- Never hide errors instead of fixing them.
- Never weaken or delete tests to make them pass.
- Never mix unrelated changes into a bug fix.
- Never merge your own pull request.
