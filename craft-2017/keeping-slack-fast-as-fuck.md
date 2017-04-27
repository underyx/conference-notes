# And the cold start performance goes to... 2.3 seconds

https://craft-conf.com/speaker/ValeraZakharov

- Always start with 'why?'
  - CEO said "A Slack client should be **fast as fuck**"
    in part because they need trust from the users
- Ad hoc 'wait for user reports and then profile' is not perfect,
  since these issues can be very subtle
- Even just changing the ordering of WHERE clauses can affect performance
  and that's not something you can catch in code review
- Performance just gets worse and worse over time when you don't track it,
  'death by a thousand paper cuts'
- Only 1% of Slack's user complaints were about performance,
  so users don't often tell you or even realize these issues,
  it just makes them unhappy.
- So, instead of all the above, take a systematic approach
  that catches these problems early
  - Just like regression tests
  - Except the results are variable, not just pass or fail
    and it can report improvements too
- We want alerts of changes, and history charts
- Track operation timings, resource usage

## App side

- Instrument your app with code block timing
  - Measuring time can be tricky though, especially on mobile
  - Blocks like app resumed to app is usable,
    or password entered to app is usable,
    it would probably be a good idea to just record the events
    and later figure out the durations between them
- Focus on the client, so mock the network operations
  - Stetho can fake a whole network history dump from Chrome, neat
  - But don't go overboard with the mocking, you don't know which
    part of the app will cause performance issues
- The simplest approach is to just have a UI flow to check all interactions
- But you should strive to have smaller self-contained tests
- And in the end, publish a report file

## Analysis side

- There is variability, inherently
- Root cause analysis is difficult
- Prefer less virtualization/no emulators
- Collect a larger dataset to get better signal
- *nimbledroid* is a company that specializes in automatic app analysis
  - They built out a solution for Slack that's for CI
  - And it only works for Android
  - It tracks based on logs
  - And has Slack alerts for performance changes
  - They have a method tracer with a flamechart for profiling
    (though it's a bit difficult to realize what actually changed on that)
  - Pretty nice in general,
    but the runtime is ~1 hour,
    their UX needs work,
    and you have no control over the data
- So Slack started working on a custom solution instead
- Make it easy to adjust the baseline (Slack alert message button)
- Analysis is post-merge now
- Weekly reports are also useful
- With enough users you can also collect timing data from them
  - But it's difficult to normalize,
    noise is introduced from connection speeds, geographic location, etc.

## Q&A

### Plans to open source the toolset?

Would love to. Sometime. Not yet ready.

### Use reference hardware?

Since you track relative change, the only important thing is to be consistent.

### Does startup time really matter compared to in-app?

Think so.
