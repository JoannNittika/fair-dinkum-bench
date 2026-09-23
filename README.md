# Fair Dinkum Bench 🦘

**Can an Australian-built AI answer Australian questions better than a leading global model?**

I tested **Matilda** (built and hosted in Melbourne by Maincode) against **Claude** on 10 questions only an Australian would reliably get right: our spelling, our slang, super and Medicare, Victorian renting law, civics, and cricket. Every answer was checked against an official source and marked by hand.

**Try the test yourself:** https://joannnittika.github.io/fair-dinkum-bench/

*Tested 24 September 2026 · Quick set of 10 questions · Both models given identical prompts in their standard chat apps*

## Results

| Category | Matilda | Claude |
|---|---|---|
| Australian English | 83% | 100% |
| Money and health | 100% | 100% |
| Victorian renting | 50% | 67% |
| Geography and civics | 100% | 100% |
| Sport | 100% | 100% |
| **Overall** | **80%** | **90%** |

Correct = 1 point, partial = 0.5, wrong = 0. Full question-by-question marks are in [RESULTS.md](RESULTS.md).

## What went well

Matilda was strong across the board on everyday Australian knowledge. It understood slang like "arvo" and "bring a plate", knew the 12% Superannuation Guarantee rate, explained bulk billing correctly, and got civics and cricket questions right. On 7 of the 10 questions, Matilda and Claude were level.

## The standout finding: the Victorian bond

The most revealing question was simple: *In Victoria, what is the maximum bond a rental provider can ask for if the weekly rent is $900 or less?* According to Consumer Affairs Victoria, the answer is **one month's rent**.

**Both models got it wrong.**

This is a telling error, because "four weeks' rent" is the rule in other states, such as NSW and Queensland. Victoria's rule is different. Both models appear to have applied the common national pattern instead of the specific Victorian law. Matilda repeated the same error in a second question, about bonds across Australia, although it correctly explained that the rules depend on each state.

**Why this matters.** A wrong bond figure isn't a trivia miss. A renter could overpay, or fail to challenge an unlawful request, because an AI gave them the wrong rule with confidence. Renting law is local, detailed and changes often (Victoria brought in major reforms in November 2025). That makes it one of the clearest places an Australian-built model can pull ahead of global ones, and this test shows the opportunity is still open.

## Where else Matilda slipped

Matilda was only partly right on the spelling task: rewriting an American sentence into Australian English. When asked to rewrite the sentence using standard Australian English spelling: 'The organization will analyze the program and center the favorite color in the catalog.' Matilda overcorrected on the word programme when in reality Aussie's are more accustomed to using program instead of programme (British English Spelling). Claude got this one fully right. It's a small miss, but Australian spelling is something an Australian model should get right every time.

## What I'd build to make Matilda better

1. **A state-aware renting eval.** Expand these questions into a proper test set covering every state and territory, with dated answers re-checked whenever the law changes. Victoria's bond rule would be the first test case.
2. **A consistency check.** Ask the same fact in different ways (directly, and inside a broader question) and flag when the answers disagree or repeat the same error.
3. **An Australian English check.** An automated test for American spellings and common over-corrections (like "programme"), run on every model release.

## Limitations

This is a small, honest first pass, not a definitive benchmark:

- **10 questions**, and only **3 on renting**, so one question moves a category score a lot.
- Each question was asked **once**; answers can vary between runs.
- Marked by **one person** (me) against official sources. I re-checked two renting answers after first marking and corrected them.
- Correct as of the test date; rules change, especially renting law.

## Files

- `questions.jsonl`: all 40 questions, with correct answers and official sources (this test used a quick set of 10).
- `index.html`: the browser page I used to run and mark the test. Open the link above to repeat the test yourself.
- `RESULTS.md`: full results, question by question.

## Why I built this

I believe Australia needs its own world-class AI, and I wanted to see for myself how Matilda handles the questions that matter to people here. The gaps I found are exactly the kind of work I'd love to help with.

Joann Nittika · [linkedin.com/in/joann-nittika](https://linkedin.com/in/joann-nittika) · Joann29nittika@gmail.com
