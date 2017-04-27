# Tackling technical debt at scale

https://craft-conf.com/speaker/YvettePasqua

- Keep asking 'Why?' until you get to the root of an issue.
- Speaker proceeds to pitch meetup.com :/
  - For like five minutes
- Start with users becomes start with engineers
  when tackling technical debt
  - Interviews with engineers about how they could be more productive
  - They wanted technical complexity reduced
- Design for reliability, simplicity, speed (of CI pipelines and stuff)
- Meetup.com started with reorganizing teams
  - The engineers working on tackling tech debt kept getting distracted
    by higher priority product issues
  - Platform teams were created, whose job was to empower the product devs,
    with their KPIs being stuff like how fast a product dev can deliver.
- "Technical debt is not always quantifiable."
- You need to prioritize a subset of tech debt,
  and don't even need it quantified.
- Branding was important to shift culture
  so they named the effort 'Continuous Product Health.'
  - Introduced it at an all-hands meeting.
  - Continuous attention to the codebase, not just features.
- People outside engineering had examples too to understand
  - increased test coverage,
  - reduced build times,
  - refactoring,
  - performance improvements.
- Health deteriorates over time if you don't pay attention.
- Convey that the lack of this results in
  - slower feature development,
  - more bugs,
  - bad user experience,
  - bad developer experience.
- The CPH pipeline/loop is
  ideas -> prioritization -> architecting -> review -> ideas
- 198 code health issues were closed in 6 months
- You need to clearly track the impact of work
  - 80% said after half a year that they don't understand the impact.
  - Plotting the first 6 months' results
    everything (lots of items)  seemed low impact and low effort,
    people wanted to do those things.
  - On the next 6 months there were just a few large items,
    but they had clear impact.
- Ideas come from working with engineers
- Prioritization is done with stragists: CTO, directors, etc.
- Architecture is done with team leads
- Review goes back to being done with engineers
- Key point: **prioritize high impact large items**.
- And other one is that you should **make sure the impact is visible**
- High impact items should be classified as such based on:
  - Cost impact,
  - reliability impact,
  - simplicity,
  - development speed.
- Make sure project ownership is clear and well-defined
- Create transparent JIRA boards and sprints for the CPH efforts
- Hold monthly meetings to fail fast and learn.

## Q&A

### Who works on the platform teams?

It's important for these members to dogfood,
but even more important to not get distracted by product responsibilities.
Every engineer can take small tasks in their sprints even outside CPH.

### How to balance feature delivery and tech debt cleanup?

Let engineers focus on only one of the two.
Make sure both sides realize they work towards the same KPIs.

### How do you convince non-technical people about the time investment?

Marketing. Clear, concise language, use metrics. Be data-driven.
