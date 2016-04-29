# The Technical Debt Trap

http://beta.craft-conf.com/speaker/DocNorton

- Prudent <-> Reckless and Deliberate <-> Inadverent dimensions exist when
  people are normally categorizing debt.
  - Reckless-Inadverent: 'What's layering?'
  - Reckless-Deliberate: 'We do not have time to design it'
  - Prudent-Inadverent: 'Now we know we did it wrong'
  - Prudent-Deliberate: 'We know the consequences and we will deal with it'
- Refactoring depends on clean code
  - 'Dirty code to tech debt is what pawn broker is to financial debt; you'll:
    never get your code back.' (paraphrased)
- Ask if you have a plan to pay back, if the business knows about the problem,
  and if no, you don't have technical debt — you have a *mess*. Or *cruft*.
  - The differentiation matters because technical debt is actually good.
- When looking at other industries it gets obvious that 'constructional
  debt' and 'mechanical debt' would be:
  - Reckless-Inadverent is incompetent, like a surgeon's mistake would be
  - Reckless-Deliberate is irresponsible, like a misconstructed house or
    car would be
  - Prudent-Any is what we actually should call technical debt
  - Note: see the actual images on the slides representing these.
- Note: lots of important real life examples that are difficult to explain,
  watch the talk from 10-20 minutes in.
- If you have an if-elif-else, it's time to consider classes. You will end up
  with more code but it will all be in the right place.
- **Cruft is a bad decision.** It slows you down and just keeps multiplying.
- Having cleaning sprints is a bad idea, you need to clean constantly. And you
  should never make an intentional mess.
  - Follow the Boy Scout Rule: leave the codebase better than you found it.
    The small incremental changes will add up over time.
- **You should never have to ask for permission to do your job correctly**.
  It's our professional responsibility.
  - Actually, you should just not ask for permission. We're in high demand —
    if you get fired for doing the right thing, there will be another
    company who wants to hire you for exactly that.
- Note: See chart on comparing the cleaning sprint approach and the constant
  cleaning approach.
- Monitor cruft through coverage, complexity, coupling, and maintainability
  - According to CodeClimate, there's a direct correlation between lines of
    code and code complexity
  - You should be looking at the trends, not the points.
- By the way, technical debt is still a good thing. If you have a plan to pay
  back and you carefully consider your decision.
- TODO: Check SonarQube

