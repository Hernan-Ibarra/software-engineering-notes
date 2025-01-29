# Ideas for the Accelerator Tech Talk 2025

## How Git works internally

- Alternative title: How does git really work?
- Dive into the structure of the .git directory.
- Commits store a copy of all the repo (modulo compression).
- Branches are just pointers to commits.
- Get into the hashing.
- Live demo could be good for this.
- History of Git. How Linus Torvalds invented git under pressure.

## P versus NP

- A million dollars, blah, blah.
- Travelling salesman problem
- Recognize when a problem in NP-hard
- Give many examples of problems in NP
- How to work around NP problems: probabilistic approach
- PRIMES is in P

## Scheme

- A brief history of Lisp
- No for-loops, or while loops. Everything is recursive.
- Everything is a linked list
- Procedures as data
- Current applications

## ML/AI - Chess

- Deep Blue versus Garry Kasparov
- Minimax and Monte Carlo simulations
- Stockfish 11+
- Alpha Zero
- Personalised chess engines

## Advanced Vim Trickery

- Why you shouldn't use Vim
- All of this should probably be a live demo
- Macros and recursive macros
- The global and normal commands
- Using external programs

## Category Theory for Software Engineers

- Quick introduction to categories, functors, natural transformations
- Monads?
- Databases as categories
- Emphasis on real-world modelling of problems

## Formal Verification (or how to go beyond tests)

- History of logic:
  - Aristotle
  - 20th century logicians
- Need for formal verification in high-stakes software use
- Achievements in mathematics
- LEAN
- How to check the checkers (kernel)

## Navigating Privacy in the Digital Era

- Cookies and why it is hard to reject them
- How companies make money off of you
- Apple recent lawsuit
- Snowden
- Ways of protecting yourself
- Ethical issues you should consider when building software

## Fediverse, ActivityPub, and the Future of Social Media

- Twitter -> X. Facebook -> Metaverse.
- Need for decentralization.
- How a unified protocol can make this happen (enter ActivityPub)
- What instances are and how they work.

## How 1 engineer outperforms 138: A History of Lichess

- Chess.com is the largest chess platform on the internet
  - 138 full-time employees.
- Lichess.org is the second-largest chess platform on the internet
  - 2 full-time employees.
  - Much better than chess.com in my opinion.
- User experience over frontend.
- How databases are handled
- How servers are handled
- General philosophy on how to build something

## Code Completion and Language Server Protocols

- Have you ever wondered how on Earth code completion works?
- Turns out to be an interesting story
- In the old times, each editor had to cater to every single language out there
- Very difficult to mantain, since languages evolve
- Also a lot of duplicated work: each editor does the same kind of things
- Microsoft was trying to solve this problem for VSCode
- Invented Language Server Protocol (LSP) as a way for languages to communicate with editors
- The editor (client) sends real time data about what is being typed to the language server. The language server communicates back with suggestions, among other things.
- By decoupling clients and servers, the process becomes much more streamlined.
- You can write your own LSP now!
