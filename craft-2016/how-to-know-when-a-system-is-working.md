# How do we know IT systems are working well?

https://www.youtube.com/watch?v=gSjkvKdaKTQ

Presenter is the founder of CFEngine

- Already a challenge to define the scope of the system, how to judge if it's working,
  and to quantify how well they are working
- Describing 'system':
  - A system has freedoms (inputs/outputs that can change) and constraints (how they
    can change) which work together in balance.
  - Important to see whether it's multiple connected compontents
  - Important to realize how isolated it is from its surroundings
- Things you need to understand about systems, with complimentary fancy bold words:
  - What it **promises** to be doing (what's intended)
  - What **assessment** reveals about what it's doing, about whether it's keeping the promise
  - **Subjectivity** comes into play when different people expect different things from a system
    - It's both good and bad to assess software with its tests
  - Promises are best when defined **autonomously**, without other components affecting what you
    decide to expect
  - Scale and time changes the **perspective** we have when thinking about these promises
- Expectations are based on wrong assumptions, 'The origin agent is the authoritative source'
  - One day I'll probably figure out what the origin agent is in a real world example
- Promise theory is something you should probably check out to learn more, basics are:
  - Agents (components) can only make promises about themselves and their own behavior
  - If they depend on another agent to fulfill this promise, you're doing it wrong
  - 'This article API returns the news articles' is wrong, you need to add 'if the database works correctly' (?)
- Defining problems is complex as well
  - You need to know the original intentions, promises should be a solution to this question
  - With promises will allow you to have a boolean assessment of whether something is working
  - You still have yet to know what the effect is of something not keeping its promise
- Definitions:
  - Error: promise in general not kept by agent
  - Design flaw: wrong promise made
  - Fault: state in which promise is not kept by agent
  - Agent fidelity/accuracy: ratio of cases in which promises are kept vs. broken
  - Dynamic stability/Semantic stability: didn't catch these, but there are agents which can lead to more outcomes
    than inputs, compicating the flow (?), and some simplify it by reducing the number of possible outcomes
- Confidence intervals should be considered when measuring
  - If you make assumptions less specific your results will be less certain as well
- Note: TODO: Try distribution charts/histograms on timeseries metrics
- Scaling has two steps, we first scale things to take less time, and then we dehumanize them and scale the space
  needed to do them.
- Huge messes can work better, modularity is not scalable
  - Chinatown vs. heavily architected/designed cities given as example
  - Microservices architecture optimizes for human knowledge (huh? I'm lost here.)
- So a system is formally a bunch of agents, they work when their promises are kept

