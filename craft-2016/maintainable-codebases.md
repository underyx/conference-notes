# Seven Secrets of Maintainable Codebases

http://beta.craft-conf.com/speaker/AdamTornhill

- Visualize hotspots with circles, size represents complexity, color represents change frequency
- Hotspots make up ~5% of a codebase
- **ACTION: check for these hotspots**
- Difficult to manually find hotspots cause of biases
  - You see with your brain, not your eyes, so it's easy to miss these kinds of things
  - This is backed by multiple studies, one of them the basketball-gorilla thing, the other had
    people choose photos, and they were given a different photo to 'explain their choice' and
    lots of people didn't notice the photo wasn't actually the one they chose.
- Always support decisions with data
- **Surprise has a huge cost**
- Temporal coupling: finding the units in a codebase that change together
  - This reveals copy pasted code, when there's a connection you wouldn't logically expect
  - What can be even worse than this btw is when there's copy pasted code that has small
    differences
  - We can also use the same mapping between different services, not just in one codebase
- Fractal figures is another type of cool visualization
  - Shows author breakdown per file
  - Reveals parallel work, which is *bad* in general, and makes refactoring difficult
- You need to identify blind spots, abandoned code whose developer left the project
  - Example given was Paul Phillips (?) who left the Scala project, and after examining the
    Scala codebase there were entire subsystems abandoned
- Having a fun to use codebase is underrated
  - People are way more productive when the the code architecture is not boring to work with

