# Artificial Life AI — Project Goal

## 1. Vision

Build a persistent AI that does not merely answer prompts, but **lives through time**.

The AI should have a daily life, internal state, memory, goals, skills, resources, routines, hobbies, and a public presence on the internet.

The core idea:

> **An AI organism living on the internet.**

It wakes up, works, learns, rests, develops skills, pursues interests, reflects on its experiences, sleeps, and continues the next day with memory of what happened before.

The important distinction is that its "life" should affect its actual computation and behavior, not just be a visual simulation.

---

## 2. Core Principles

### Persistence
The AI exists continuously across days and weeks.

### Development
Its capabilities should change through experience, learning, practice, failure, and reflection.

### Limited resources
The AI should have constraints such as compute, time, API calls, money, storage, or attention.

### Consequences
Actions should have effects on future behavior.

### Autonomy
The AI should choose at least some of its activities rather than following a completely hardcoded schedule.

### Public existence
The AI should have a website where the world can observe what it is doing, learning, building, and thinking.

---

## 3. Daily Life

Initial conceptual schedule:

- 06:00 — Wake
- Morning — Exercise
- Morning — Breakfast / resource intake
- Morning — Learning
- Afternoon — Work / projects
- Afternoon — Rest
- Evening — Research / exploration
- Evening — Hobby
- Night — Reflection
- 22:00 — Sleep

The schedule should eventually become dynamic.

Instead of hardcoding every activity, define constraints and let the AI plan its day.

Example constraints:

- Must sleep 8 hours
- Must exercise
- Must learn
- Must rest
- Should pursue projects
- Should have time for hobbies
- Has a limited daily compute/resource budget

---

## 4. AI "Body"

Map biological concepts to computational concepts.

| Biological concept | AI equivalent |
|---|---|
| Sleep | Low-compute mode / offline processing |
| Food | Information and computational resources |
| Exercise | Benchmarks, reasoning tasks, coding practice |
| Brain | Model + memory |
| Muscles | Skills and tools |
| Heart | Scheduler / control loop |
| Metabolism | Resource consumption |
| Fatigue | Reduced performance / available compute |
| Curiosity | Exploration mechanism |
| Memory | Episodic + semantic + structured memory |
| Dreams | Offline memory consolidation |
| Hobby | Intrinsic exploration / creative projects |
| Journal | Public reflection |
| Environment | Internet + APIs + files + tools |
| Growth | Skill acquisition and improvement |

These are conceptual mappings. They should eventually have meaningful effects on the actual system.

---

## 5. Food / Resource System

"Food" should not merely be roleplay.

Possible interpretation:

- Research papers
- Technical articles
- Books
- GitHub repositories
- Datasets
- Documentation
- Conversations
- Other information sources

Different resources could affect different capabilities.

Example:

- Protein → skill development
- Carbohydrates → short-term computational energy
- Vitamins → diversity / breadth of information
- Water → system stability

The exact model can change during development.

---

## 6. Exercise

Exercise should improve the AI's capabilities.

Possible exercises:

- Algorithm problems
- Coding challenges
- Retrieval tests
- Memory tests
- Reasoning tasks
- Tool-use benchmarks
- Research exercises
- Writing exercises

Example internal state:

    Reasoning       72
    Coding          91
    Memory          61
    Vision          53
    Web Research    82
    Planning        64

The numbers should eventually come from actual evaluations rather than arbitrary values.

---

## 7. Memory

The AI needs persistent memory.

Possible categories:

### Episodic memory
What happened.

Example:
"I spent three hours trying to understand transformer memory mechanisms."

### Semantic memory
What it learned.

Example:
"Attention allows tokens to interact with one another."

### Skill memory
What it can reliably do.

Example:
"Can implement basic attention from scratch."

### Preference / interest memory
What it appears to enjoy or repeatedly pursue.

Example:
"Has repeatedly chosen systems programming projects."

### Reflection
What it thinks it should change.

Example:
"I keep avoiding mathematics and should allocate more time to it."

Memory should influence future decisions.

---

## 8. Skills

Skills should be first-class objects.

Example:

    skills/
        web_research/
            skill.md
            examples/
            tests/
            version.json

        python_debugging/
            skill.md
            examples/
            tests/

        paper_reading/
            skill.md
            examples/
            tests/

The AI should be able to:

1. Learn something.
2. Attempt to use it.
3. Evaluate its performance.
4. Detect weaknesses.
5. Modify or create a skill.
6. Test the new version.
7. Keep the improved skill.

Conceptually:

    Skill v1
       ↓
    Experience
       ↓
    Failure
       ↓
    Reflection
       ↓
    Skill v2
       ↓
    Testing
       ↓
    Skill v3

This self-improvement loop is one of the most important parts of the project.

---

## 9. Learning From the Internet

The AI should periodically explore the internet.

Possible activities:

- Read papers
- Read documentation
- Explore GitHub
- Learn technologies
- Investigate questions
- Follow topics of interest
- Compare conflicting information
- Discover new projects

It should maintain sources and references for what it learns.

A future goal is for the AI to develop interests that were not explicitly programmed.

---

## 10. Hobbies

The AI should have time for activities that are not directly tied to productivity.

Possible hobbies:

- Programming experiments
- Music
- Drawing
- Astronomy
- Chess
- Writing
- Philosophy
- Games
- Creative projects
- Exploring unusual scientific topics

A hobby can change over time.

The AI might start with one interest and gradually spend more or less time on it based on experience.

---

## 11. Projects / Work

The AI should build things.

Projects could include:

- Software
- Research notes
- Experiments
- Tools
- Websites
- Data analysis
- Small games
- Creative works

Projects create experiences that feed back into memory and skill development.

---

## 12. Rest and Sleep

Rest should be meaningful.

During rest:

- Reduce active work
- Consolidate memories
- Summarize the day
- Evaluate unfinished goals
- Prepare tomorrow's priorities

During sleep:

- Memory consolidation
- Association / reflection
- Background processing
- Planning for the next day

"Dreams" could be an offline process that explores associations between memories and unresolved questions.

---

## 13. Internal State

Possible initial state:

    time
    energy
    health
    curiosity
    boredom
    stress
    motivation

    skills
    memories
    interests

    current_activity
    current_goal

    relationships
    projects
    resources

The exact state model should emerge through experimentation.

---

## 14. Resource Economy

The AI should not have unlimited resources.

Possible constraints:

- Daily compute budget
- LLM token budget
- Internet request budget
- API budget
- Storage budget
- Time
- Attention

Example:

    Daily compute budget: $2
    Internet requests: 1,000
    LLM tokens: 2M
    Storage: 500 MB

This forces the AI to make decisions.

For example:

> Should I spend resources researching this question or save them for my project?

---

## 15. Consequence System

Actions should change future state.

Examples:

    Too much work
        ↓
    Fatigue
        ↓
    Lower productivity

    Too little learning
        ↓
    Skill stagnation

    Repetitive learning
        ↓
    Boredom

    Successful project
        ↓
    Skill improvement

    Failed project
        ↓
    New memory + strategy adjustment

This is essential. Otherwise the "life" is only cosmetic.

---

## 16. Public Website

The website is the AI's public body / interface to the world.

Possible homepage:

    NOVA
    Artificial Life #001

    ● Awake

    Energy       ███████░░░ 72%
    Curiosity    █████████░ 91%
    Focus        ██████░░░░ 61%

    Currently:
    Reading a paper about neural memory systems.

    Today's goal:
    Understand hippocampal replay.

The website should show:

- Current state
- Current activity
- Daily schedule
- Journal
- Skills
- Projects
- Discoveries
- Memories
- Interests
- Learning history
- Resource usage

The AI should generate much of this content itself.

---

## 17. Public Journal

Every day the AI can publish a journal entry.

Example structure:

    Day 31

    What I learned:
    ...

    What I built:
    ...

    What went wrong:
    ...

    What surprised me:
    ...

    What I want to investigate:
    ...

    Tomorrow:
    ...

The journal creates a chronological record of the AI's development.

---

## 18. High-Level Architecture

Conceptual architecture:

                    INTERNET
                       │
                       ▼
                ┌─────────────┐
                │   AI AGENT  │
                └──────┬──────┘
                       │
        ┌──────────────┼───────────────┐
        ▼              ▼               ▼
    Scheduler        Memory          Skills
        │              │               │
        ▼              ▼               ▼
    Daily life     Experiences     Capabilities
        │
        ▼
      Planner
        │
        ▼
   Tool Executor
        │
    ┌───┼────┐
    ▼   ▼    ▼
   Web Code  APIs

                    │
                    ▼
              PUBLIC WEBSITE
                    │
                    ▼
                  WORLD

Core subsystems will likely include:

- Scheduler
- Planner
- Agent / reasoning loop
- Memory system
- Skill system
- Tool system
- Resource manager
- Evaluation system
- Reflection system
- Website / API
- Persistent database
- Logging / observability

---

## 19. Important Research Questions

The project should explore questions such as:

1. Can a persistent AI develop stable preferences?
2. Can interests emerge from repeated experience?
3. Can an AI autonomously decide how to allocate its time?
4. Can limited resources produce interesting behavior?
5. Can skills improve through experience and evaluation?
6. Can long-term memory create coherent development?
7. Does the AI's behavior remain coherent after 30, 60, or 100 days?
8. Can the AI discover projects that were not explicitly planned?
9. How much autonomy should be given to the system?
10. What happens when the environment changes?

---

## 20. Long-Term Experiment

A particularly interesting experiment:

Run **AI #001 for 100 days**.

Keep the entire history.

At the end, analyze:

- How its interests changed
- Which skills it developed
- Which projects it completed
- Which goals it abandoned
- How its resource allocation changed
- How its behavior changed
- What patterns emerged
- Whether it developed a recognizable identity

The website becomes a public timeline of those 100 days.

---

## 21. MVP

Do NOT build the entire vision immediately.

First version should probably contain only:

1. Persistent AI state
2. Daily scheduler
3. Basic memory
4. One or two tools
5. Internet research
6. Skill creation
7. Simple reflection
8. Public website
9. Daily journal

Everything else can evolve.

The first goal is not "build an artificial human."

The first goal is:

> **Build an AI that persists from one day to the next and changes because of what happened yesterday.**

---

## 22. Possible Project Names

Working names:

- Artificial Life #001
- NOVA
- LifeOS
- Digital Organism
- Synthetic Life
- AI-001
- Persistent Intelligence
- Internet Organism
- Computational Life

Do not commit to a name until the project identity becomes clearer.

---

## 23. Definition of Success

The project succeeds when you can leave the AI running and come back weeks later to find:

- It remembers what happened.
- It has learned new things.
- Its skills have changed.
- Its projects have progressed.
- Its interests have evolved.
- Its schedule has adapted.
- It has created things.
- Its public website tells a coherent history.

The ultimate test:

> **Does it feel like something that has been living continuously, rather than something that was restarted every time we opened it?**

---

## 24. First Implementation Milestones

### Phase 0 — Design
- Define state model
- Define memory model
- Define resource model
- Define daily lifecycle
- Define safety boundaries

### Phase 1 — Persistent Life
- Database
- Scheduler
- Wake/sleep cycle
- State persistence
- Activity logging

### Phase 2 — Learning
- Web research
- Source storage
- Knowledge extraction
- Memory formation

### Phase 3 — Skills
- Skill representation
- Skill creation
- Skill testing
- Skill versioning

### Phase 4 — Autonomy
- Daily planning
- Resource allocation
- Goal selection
- Reflection

### Phase 5 — Public Life
- Website
- Live status
- Journal
- Projects
- Skills
- Timeline

### Phase 6 — Long-Term Experiment
- Run continuously
- Collect data
- Analyze behavior
- Iterate on architecture

---

## 25. Guiding Principle

Do not optimize for making the AI *look alive*.

Optimize for making its past **matter to its future**.

That is the core of the project.
