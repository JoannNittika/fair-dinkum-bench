# Fair Dinkum Bench 🦘

**Can an Australian-built AI answer Australian questions better than a leading global model?**

I tested **Matilda** (built and hosted in Melbourne by Maincode) against **Claude** on 10 questions only an Australian would reliably get right: our spelling, our slang, super and Medicare, Victorian renting law, civics, and cricket. Every answer was checked against an official source and marked by hand.

*Tested 24 September 2026 · Quick set of 10 questions · Both models given identical prompts in their standard chat apps*

## Results

| Category | Matilda | Claude |
|---|---|---|
| Australian English | 83% | 100% |
| Money and health | 100% | 100% |
| **Victorian renting** | **100%** | **50%** |
| Geography and civics | 100% | 100% |
| Sport | 100% | 100% |
| **Overall** | **95%** | **85%** |

Correct = 1 point, partial = 0.5, wrong = 0. Full question-by-question marks are in [RESULTS.md](RESULTS.md).

## The standout: Victorian renting

Renting was the one category where the two models clearly split. Matilda got all three renting questions right; Claude got one right, one partly right, and one wrong.

**The bond question.** *In Victoria, what is the maximum bond a rental provider can ask for if the weekly rent is $900 or less?* The answer, according to Consumer Affairs Victoria, is one month's rent. Matilda got it right. Claude got it wrong.

> **Matilda:** [paste Matilda's answer]
>
> **Claude:** [paste Claude's answer]

**The "it depends" question.** *What is the maximum rental bond a landlord can charge in Australia?* This is a trick question: there is no national rule, because each state sets its own. Matilda recognised that the answer depends on the state. Claude only partly did.

> **Matilda:** [paste Matilda's answer]
>
> **Claude:** [paste Claude's answer]

**Why this matters.** A wrong bond figure isn't a trivia miss. A renter could overpay, or fail to challenge an illegal request, because an AI told them the wrong number with confidence. Renting rules are local, detailed and change often (Victoria brought in major reforms in November 2025), which is exactly where a model built in Australia, for Australians, should have an edge. On this small test, Matilda showed that edge.

## Where Matilda slipped

Matilda was only partly right on the spelling task: rewriting an American sentence into Australian English. [Describe what it missed, e.g. which word it left in American spelling or over-corrected.] Claude got this one fully right.

It's a small miss, but a telling one. Australian spelling is something an Australian model should get right every time.

## What I'd build to make Matilda better

1. **A state-aware renting eval.** Expand these three questions into a proper test set covering every state and territory, with dated answers that get re-checked every time the law changes. Matilda already leads here, and this would keep it there.
2. **An Australian English check.** A simple automated test for American spellings and common over-corrections (like "programme"), run on every model release.
3. **"It depends" as a skill.** More questions where the honest answer is "it depends on your state" or "check with the ATO", to reward Matilda for knowing the limits of a single answer.

## Limitations

This is a small, honest first pass, not a definitive benchmark:

- **10 questions**, and only **3 on renting**, so one question moves a category score a lot.
- Each question was asked **once**; answers can vary between runs.
- Marked by **one person** (me) against official sources.
- Correct as of the test date; rules change, especially renting law.

## Files

- `questions.jsonl`: all 40 questions, with correct answers and official sources (this test used a quick set of 10).
- `fair-dinkum-bench-tester.html`: the browser page I used to run and mark the test. Open it to repeat the test yourself.
- `RESULTS.md`: full results, question by question.

## Why I built this

I believe Australia needs its own world-class AI, and I wanted to see for myself how Matilda handles the questions that matter to people here. I'd love to help build it.

[Your name] · [LinkedIn or email]
