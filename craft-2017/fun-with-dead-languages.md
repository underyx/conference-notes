# Fun With Dead Languages

https://craft-conf.com/speaker/DamianConway

- Bananas have a surprising history
  - Commercial bananas are sterile clones, they have no genetic diversity,
    which makes all bananas vulnerable to just one (theoretical) virus
- This should point to the dangers of monoculture
- Everything is '…for Java' and that's no good
  - Especially cause of people who can only code in one language
- These people think their way of thinking is *the* way of thinking
- There's much to be learned from disecting dead languages

## Dead Language #1: PostScript

- Printing, typesetting today
- But in olden times NeXT had the whole GUI in PostScript
- Stack based language, no variables
  - All languages work like this, but PostScript doesn't abstract it away
  - `/Arial findfont 32 scalefont setfont`, Yoda function calls, like this one
  - `/squared` push name on stack
  - `{dup mul}` push code on stack (duplicate and multiply)
  - `def`: consume stack and combine it into a function
- No dynamic memory at all
- But it's actually a high level, functional language
- It replaces variables with procedures and redefinitions of those
- Very impressive and entertaining demo, watch the video!

## Dead Language #2: C++

- More like a dead paradigm. Where the paradigm is 'declarative'.
- You could use operator overloading
  to draw finite state machine diagrams in ASCII
  and execute that as code
- Again, you gotta see the demo, this is super fun.
- Basically does reactive programming with closures

## Dead Language #3: Latin

- The word order doesn't matter!
- It works cause of inflection,
  each word has suffixes that describe everything what affects it
- So how do we apply this to programming?
  - Programming languages are mostly based on English grammar
  - Normally the left argument of binary operators are being modified
  - You could try naming all these arguments like `add(target=3, data=1)`
- Please watch the video :D

I'll stop here, my battery is dying and this is better seen firsthand anyway.
