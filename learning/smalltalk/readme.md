<img width="2732" height="1061" alt="Ilustración_sin_título" src="https://github.com/user-attachments/assets/d06e6955-35d2-4877-b58d-7e026aee4954" />

# Learning Smalltalk

<img width="2388" height="1668" alt="Ilustración_sin_título" src="https://github.com/user-attachments/assets/a075e905-e511-4bfb-b375-46b017bb1862" />

<img width="2388" height="1668" alt="Ilustración_sin_título" src="https://github.com/user-attachments/assets/34765e1e-bdab-41cb-a521-6860d17f5683" />

## Principles

### 1. 🧱 Everything is an Object

- Every value is an object — numbers, strings, classes, code blocks, even the IDE itself.
- Objects communicate only by sending messages.

Design Insight:

> You don’t “call a function”, you send a message to an object. This models decentralized systems, like cells in a body or people in a society.

Alan Kay: `OOP to me means only messaging, local retention and protection, and hiding of state-process, and extreme late-binding of all things.`

### 2. 🧬 Code and Environment Are the Same

- There’s no separate compiler, REPL, or file structure.
- The IDE is the system. You explore and modify everything live — from the UI down to the VM internals.

Design Insight:

> This enables a fluid, iterative process of software design, where your system is always alive, malleable, and changeable.

`Contrast this with tools where you stop everything, edit a file, compile, test, restart — in Smalltalk, you’re always in the system.`

## 3. 🪞 Reflection and Introspection

- The entire system is built with objects — and you can inspect, modify, or replace any of them.
- Tools like the Inspector, Debugger, Browser, etc., let you explore the running system at any level.

Design Insight:
`Your system is transparent and explorable — you’re never debugging from the outside, you’re walking inside the world you’ve built.`

## 4. 🧩 Uniformity and Simplicity

- Very small syntax (often fewer than 10 core concepts).
- No special cases — message sending is always the same.
- The class hierarchy is deep but simple (Object at the top, everything descends from it).

Design Insight:
`Cognitive load is reduced — the fewer rules you have, the more power you gain from composition and reuse.`

## 5. 🧠 Programming as Thinking and Modeling

- The goal isn’t just building code — it’s about modeling real-world domains through live, manipulable systems.
- Programs are living models of concepts — they should evolve as your understanding deepens.

Design Insight:
`Code isn’t a fixed artifact. It’s part of a dynamic knowledge-building process.`

Alan Kay: `The computer is an instrument whose music is ideas.`

## 6. 🛠️ Tools Are Not Separate From the Language

- The debugger, inspector, file browser, unit tester — all written in Smalltalk.
- You can improve, extend, or customize any part of your tools within the same language and environment.

Design Insight:
`Tooling is not a service outside the language — it’s part of the same living system. This enables moldable tools and domain-specific views.`

## 🔄 The Pharo Take: Moldable and Live Software

Pharo builds on all of the above and adds:

- 🌐 Live remote systems: You can inspect and modify a Pharo system running on another machine.
- 🧠 Moldable Development: Build custom tools for understanding your domain, not just for manipulating code.
- 🖼️ Domain-specific inspectors: Replace boring object views with charts, dashboards, visual trees — whatever fits your problem.
- 📈 Self-aware systems: Systems that expose their internals to you in a friendly, useful way.

# Smalltalk for classic programmers

`Glamorous Toolkit GT - sculptural development`

- GT is the IDE but also is the system. The Pharo image contains all the code needed running.
- GT it's a very different approach of develop software. It's a live and visual enviroment, there is no comparation with classical IDEs.
- Instead of have a bunch of files with class definitions, you'll have a way of visuallize objects and its definition in tables of methods and instance variables.
- The fact of have  a live system is the possibility of explore the system itself in real time, you can add breakpoints, look the class implementation, look for implementors, look for senders, open a notebook and start to craft your code.
- It's impressive see how easy is to create things as you need, the GT help you to craft all what you need very easy, it feels like TDD spirit.

`Moldable Development Skills`

- Follow the messages: look at the objects and its message passing, there should be always a method to receive that messages.
- Inspect everything, inspect the objects, the classes.
- Use the lepiter notebook to craft what you need.
- The playground can send messages to the current object.

---

### My Own Mental Models

`Smalltalk Programmer Toolbox: Living inside the system`

- Everything is an object.
- Everything happens by message passing.
- The system itself is live during development.
- Live exploration through live states.
- Systems should be grown not built.
- You model reality as interconnected networks of responsibility.
- Develop a new intuition. 

`Code Exploration`

- `Causal loops`: Traceable runtime behavior that emerges from message passing between live objects — causality lives in the interaction
- `XRay analysis`: Pause and examine the internal state of objects mid-flight, inspecting their variables, messages, and behavior in situ.
- `Open-heart surgery`: Exploring or patching objects directly from the Playground.
- `Tinkering Toolkit`: Use Lepiter notebooks and playgrounds to run small, safe experiments on a live system
- `Exploration Questions`: Craft questions about `what I need to know to understand this?`

`More Ideas`

- `Moldable microscope`: Creating a custom view to visualize what matters in your domain.
- `Cognitive Cartography`: Mapping out mental models of how a part of the system behaves.
- `Shell Listening`
- `Storm Sketching`
- `Seasons`
- `Slow Motion`

`Exploratory Programming`

- `Lost in the forest`: Recognize you're lost and it's part of the journey. 
- `Black Holes`: Black Holes are regions of the system or knowledge space that feel massive, intimidating, or undefined. Instead of rushing in, mark them, orbit them, and slowly illuminate their boundaries.
- `Rabbit Holes`: Spaces in the system that feels curious and it's a place to understand things.
- `Turtle Steps`: This is the technique of moving deliberately and observably, making small, reversible changes and inspecting the results. It’s how you build deep understanding without overwhelm.
- `White belt`: White Belt is a mindset of humility and openness — letting go of the need to know, so that you can truly observe, ask, and grow. It reminds you that mastery begins with surrender.
- `Retrospective Maps`: Retrospective Maps are a way to chart where you’ve been, not just to document it, but to redesign it. By mapping the steps you took — or wish you’d taken — you can recognize patterns, refine your process, and gain meta-awareness.
