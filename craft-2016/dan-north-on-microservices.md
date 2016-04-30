# Microservices: software that fits in your head

http://beta.craft-conf.com/speaker/DanNorth

- Microservices is just one instance of an architectural style
- The point of software dev is to have *positive* business impact
- The goal of software dev is to *sustainably* minimize lead time to business
  impact
  - Note that it's not to produce software.
- Code is not the asset. The asset is business impact and code is the cost.
  - All code is debt, good code is just less debt.
  - Writing code, waiting for, changing, and understanding code are all costs.
- Code in terms of understandability can be categorized as 'code I know',
  'code everyone knows', 'code no one knows'.
  - The last category include most code written by others or yourself 6 months
    ago
- Code no one knows needs to be either stabilized or kill off **fast**.
- Story about one of the best and most productive software teams presenter
  has seen: they had really short *software half-life*, half the codebase
  was changed every six weeks.
- Devs should have no emotional attachment to any of their code to let this
  happenpr
- Write discrete components and have clear component boundaries, purposes
  and responsibilities.
- You will need to invest in stabilizing part of the code
- The team will need to be stable
- 'Fits in my head' needs to be followed on all dimensions and scales
  - An overview of the codebase from afar should fit in your head the same
    way as a function's code should.
  - Keep a consistent architectural style and consider what your coworkers
    would do. Agree on principles and idioms with your team.
- Optimize for replaceability in components
  - 'Little computer passing messages' is a quote by Alan Kay about OOP, and
    microservices is actually the same concept.
  - When you have a replaceable component architecture (microservices can be
    that) you can reason about each component by isolating a component and
    considering only itself and its messages.
  - These are not necessarily small by the way
- Takeaway: **kill code fearlessly!!** (And write code that can be killed
  fearlessly.)

