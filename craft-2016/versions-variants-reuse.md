# Versions, Variants, Reuse - Get me out of here!

http://beta.craft-conf.com/speaker/DaniloBeuche

Speaker is a consultant with >15 years experience, mostly with embedded
systems.

- You have no idea what the road ahead of you looks like, so it's difficult to
  plan what you'll reuse when starting out.
- In some cases reuse is actually not advantageous, think of it as a tool
- The two dimensions for categorization are number of variants and products per
  variant
- `dev throughput = asset size * complexity of reuse` (huh? that sounds like it
  should be `1 / dev throughput`)
- Ad-hoc reuse works by exchanging stories of what each team worked on during
  coffee breaks and then copying components from each other's projects - this
  is really cheap to start doing
- Everything is reusable, not just code: tests, docs, requirements, etc.
- Standard asset based reuse is when you have building blocks prepared for
  all of these and people pick these out from a central repo
- When you need a minor change, you can change the existing component, ask
  the customer to reconsider their requirements, or create a totally new
  component.
- Reuse can be platform based, where you have one framework for all projects,
  and anything that's different from the norm is deferred to the scope of the
  projects.
- Product line strategy: select building blocks, configure them, develop the
  rest of the project.
- Note: Honestly at this point I'm not sure what this talk is about. All of
  this sounds trivial, and so fundamental to software architecture that every
  attendee should be familiar with the concepts already.
- Each individual variation doubles number of choices, so to decrease
  complexity you can couple variations together (such as 4 toggles that can
  only be switched together.)
  - Note: the given example was car design, I really don't think this applies
    to or is desirable in the kind of projects I work on normally. Of course
    some coupling is standard, like a debug mode switch which actually
    modifies lots of the code to log more, etc., but I wouldn't do this for
    user facing features unless absolutely necessary, in which case this
    solution will be immediately apparent anyway.
- The real trouble starts after this point, when changes start being needed.

### Retrospective

I guess I expected something entirely different solely due to my ignorance.
Since the presenter as a consultant has obviously been seeing these things
as stuff that needs to be introduced to his client companies, I will just
assume that in their domain reuse concepts are not as fundamental and
immediately apparent as when developing a web application. What's more is
that the talk's subject was reuse for similar products, and not about code
architecture or code sharing between just a few somewhat independent
projects. I'll consider this a failure on my part. :see_no_evil:

