# Constructive Code Review

- Goal of code review is not just to build the product,
  but also people — including yourself
- Creative work is powered by enthusiasm
  - Don't get paid to program,
    Get paid to get to spend your time programming

## Clarity of explanation

- Your review also has to be durable;
  use permalinks, be descriptive
  (don't write 'do the thing we said yesterday')
- Care about formatting
- Upgrade to higher bandwidth communication when needed,
  but make sure to write down the result

## Clarity of expectation

- 'I would love blank, but it doesn't need to block the merge'
- Explicitly note 'that's all I see, after these changes it's ready'

## Tact Hacks

- Write questions ('can you remind me of use cases for this?')
  - This can also save you some embarrassment
- You vs. We vs. This make a huge difference
- Compliment sandwich!
  - 'Thanks for refactoring this scary mess' is a good one to start with

## Antipatterns

- Write a prose overview of your patch if you have a 1000 line patch,
  so people don't have to reverse engineer your entire brain
  - Add benchmark results if relevant
- Keep small commits with good commit messages
  - GitX is a good GUI tool for splitting commits
  - FileMerge (part of XCode) is a good diff visualizer

## Nitpicks

- It's a cultural problem.
  People trying to justify their existence.
  The solution is self-confidence.
- You need to give others the needed self-confidence, though.
- Style guides let you have every argument only once.
- Use linters, but if they're overzealous they make your code worse.
  - Don't serve your tools.

## Meta stuff

- Be quick with merging.
- Be clear about whether you can follow up and handle the patch.
  - Be quick with saying no.

## Humans

- Insecurity means fear
- Everyone is wrapped up in themselves, that makes things easy
- Nobody loses in code review, you get smarter
- What's the worst that could happen?
- Cognitive therapy can sometiems be needed, too
- When you're stuck in some bad emotion, go for lunch
- If you feel short on time:
  - you can lower your standards and still not get everything done,
  - or never sleep,
  - or pace and prioritize. David Allen's GTD recommended.
- 'Takes <2 mins? Then do it' is the best part of GTD,
  has high impact and is great for managing guilt.
- Inbox Zero is useful cause an email inbox is a crappy to-do list UI.
  Too much linear scanning and stuff. It's a nice morale boost, too.
- Speaker filters OSS requests
  and goes through them with GTD once a week.
- Guilt doesn't help with anything.
- 'Level up' newcomers
  - At level 1 give them docs, tutorials, and fix their stuff.
  - At level 2 don't fix their code, maybe write tests for them.
- For 'legacy reasons' face to face is the easiest way to build trust.
  - This way you can 'Trust Bank' like with horse training

## Questions

### How do you sounds sincere if you learned this stuff in a talk?

Always be sincere. The question mark makes this the easiest.

### How do you deal with nitpickers?

Ask 'is this something we can block this patch on?'
Or 'is there a way to automate it?'
Make friends with them to get to actually tell them.

### What to use for GTD?

Things app. And 2do. Or why not paper.

### How do apply this to a team of one?

Well you can apply it to support requests.
