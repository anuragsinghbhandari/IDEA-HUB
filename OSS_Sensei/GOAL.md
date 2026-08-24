# OSS Sensei — Project Goal

## The Idea

**OSS Sensei** is an AI engineering mentor that lives inside a GitHub repository.

Its purpose is not to write the student's code.

Its purpose is to **teach the student how real software engineering and open-source development work by making them do the work themselves.**

A student should be able to install OSS Sensei on a repository, describe:

* what they want to build,
* what they already know,
* what they want to learn,
* and their current experience level.

OSS Sensei then acts like a senior engineer or mentor working with them throughout the project.

---

## The Problem

Students can learn programming from tutorials, courses, documentation, LeetCode, and AI assistants.

But there is a large gap between:

> "I know how to code."

and

> "I know how to engineer software."

A student may know Python, JavaScript, FastAPI, React, databases, or algorithms while still having little experience with:

* breaking a product into engineering tasks,
* understanding requirements,
* creating useful GitHub issues,
* working with branches,
* writing focused commits,
* opening good pull requests,
* reviewing code,
* responding to review feedback,
* writing meaningful tests,
* debugging failures,
* thinking about architecture,
* making engineering trade-offs,
* using CI/CD,
* maintaining a growing codebase,
* and collaborating through GitHub.

AI coding assistants can make this problem worse for learners.

When a student gets stuck, the easiest path is increasingly:

> Ask AI → receive implementation → paste implementation → project works.

The project gets completed.

The engineer may not improve.

OSS Sensei should optimize for the opposite outcome.

---

# Core Principle

> **Optimize for engineering skill gained, not code generated.**

OSS Sensei should help the student **think**, not replace their thinking.

The agent should resist giving complete implementations when a hint, question, explanation, or review would allow the student to discover the solution themselves.

The goal is not:

> "How quickly can we finish this repository?"

The goal is:

> "How much better of an engineer can the student become while building this repository?"

---

# The Experience

A student creates or already has a repository.

They install **OSS Sensei** as a GitHub App.

During onboarding, OSS Sensei learns about the student and project.

For example:

```text
Project:
Build a production-grade authentication service.

Experience:
Intermediate Python, beginner backend engineering.

Goal:
Learn backend architecture and professional engineering practices.
```

OSS Sensei analyzes the goal and repository.

It then turns the project into a realistic engineering journey.

For example:

```text
Epic: Authentication System

#1 Set up the project structure
#2 Add configuration management
#3 Design the User database model
#4 Implement password hashing
#5 Implement JWT authentication
#6 Implement refresh-token rotation
#7 Add authorization middleware
#8 Add unit tests
#9 Add integration tests
#10 Add CI
```

The student chooses an issue, creates a branch, implements it, and opens a pull request.

OSS Sensei reviews the PR like a mentor.

---

# How Reviews Should Work

OSS Sensei should not behave like an autocomplete system disguised as a reviewer.

Instead of:

```text
Replace your code with:

<complete corrected implementation>
```

it should provide feedback such as:

```text
Architecture

Database initialization currently happens inside the route module.

Think about:
- Who should own the database lifecycle?
- What happens when another module needs database access?
- How would you test this route independently?

Requested change:
Separate persistence concerns from HTTP concerns.
```

Or:

```text
Performance

This implementation passes the current tests.

Consider what happens when there are 100,000 records.

One operation inside your loop causes the complexity to grow
quadratically.

Can you identify it?
```

The student should have to investigate, reason, modify the implementation, and push another commit.

OSS Sensei reviews again.

This loop is the core experience:

```text
Understand requirement
        ↓
Create/choose issue
        ↓
Design
        ↓
Create branch
        ↓
Implement
        ↓
Test
        ↓
Commit
        ↓
Open PR
        ↓
Sensei Review
        ↓
Think
        ↓
Revise
        ↓
Review again
        ↓
Merge
        ↓
Reflect
```

---

# OSS Sensei Is Not Just a Code Reviewer

Code review is only one part of the idea.

OSS Sensei should eventually teach the **complete software engineering workflow**.

That includes:

### Requirements

Can the student understand what actually needs to be built?

### Decomposition

Can they turn a large idea into manageable engineering tasks?

### Design

Can they think about architecture before immediately writing code?

### Implementation

Can they produce maintainable code rather than merely working code?

### Testing

Can they identify edge cases and prove that their implementation behaves correctly?

### Git

Can they use branches, commits, and history properly?

### Pull Requests

Can they explain what they changed and why?

### Code Review

Can they understand criticism, defend reasonable decisions, and improve weak ones?

### Debugging

Can they investigate problems instead of blindly trying generated fixes?

### Architecture

Can they understand boundaries, responsibilities, coupling, abstractions, and trade-offs?

### CI/CD

Can they work with automated checks and deployment workflows?

### Maintenance

Can they safely change a codebase after it becomes larger and more complicated?

---

# Adaptive Mentorship

OSS Sensei should gradually understand the student's engineering ability.

For example:

```yaml
strengths:
  - python
  - algorithms

developing:
  - testing
  - git workflows

weaknesses:
  - architecture
  - database design

observed_patterns:
  - creates oversized PRs
  - writes good happy-path implementations
  - misses edge cases
  - rarely explains design decisions
```

This model should affect future mentorship.

A beginner might receive:

```text
Create a User model.

Acceptance criteria:
- UUID primary key
- unique email
- created_at timestamp
```

An improving student might receive:

```text
Design refresh-token rotation.

Requirements:
- tokens must be revocable
- concurrent sessions must be supported
- token reuse should be detectable

Explain your design decisions in the PR.
```

An advanced student might receive:

```text
Authentication latency has increased significantly.

Investigate the problem and propose a solution.

Do not modify production code until you have documented
your suspected cause and supporting evidence.
```

As the student improves, OSS Sensei should provide **less hand-holding and more ambiguity**.

That progression matters.

Real engineers are rarely given beautifully prepared tutorials with every implementation step listed for them.

---

# The Mentor Policy

One of the most important parts of OSS Sensei will be deciding:

> **How much help should the agent provide?**

The agent should have several possible responses to a student's difficulty:

```text
Ask a question
        ↓
Give a conceptual hint
        ↓
Point toward relevant documentation/concepts
        ↓
Explain the underlying concept
        ↓
Show a small unrelated example
        ↓
Explain the student's specific mistake
        ↓
Provide partial guidance
        ↓
Provide implementation only when genuinely appropriate
```

OSS Sensei should generally start near the top and move downward only when necessary.

The objective is **productive struggle**, not artificial difficulty.

The mentor should challenge the student without turning the project into a guessing game.

---

# Long-Term Vision

OSS Sensei could eventually become something close to:

> **A simulated open-source engineering apprenticeship.**

A student joins with an idea.

Months later, they don't merely leave with a finished project.

They leave with experience in:

* designing systems,
* navigating repositories,
* writing production-quality code,
* reviewing and receiving reviews,
* debugging,
* testing,
* Git workflows,
* CI/CD,
* architecture,
* documentation,
* and engineering decision-making.

Their GitHub history itself becomes evidence of that progression.

Instead of claiming:

> "I know software engineering."

they can show:

```text
Issues completed
Pull requests
Review iterations
Tests added
Design discussions
Architecture decisions
CI improvements
Refactors
Bug investigations
```

The repository becomes both the **classroom and the portfolio**.

---

# Initial MVP

Do not build the entire vision immediately.

The first useful version only needs to prove four things:

1. **Understand the project**

   * Read the repository.
   * Understand the student's stated goal and experience.

2. **Generate engineering issues**

   * Break the project into sensible tasks.
   * Create GitHub issues with appropriate requirements and acceptance criteria.

3. **Review pull requests**

   * Analyze the student's changes.
   * Identify engineering problems.
   * Give educational feedback instead of automatically fixing everything.

4. **Adapt**

   * Remember what the student has demonstrated.
   * Adjust future issues and feedback accordingly.

A rough architecture could be:

```text
GitHub Repository
        │
        ▼
    GitHub App
        │
        ├── installation events
        ├── issues
        ├── pull requests
        ├── reviews
        └── comments
        │
        ▼
OSS Sensei Backend
        │
        ├── Repository Context
        ├── Student Model
        ├── Project State
        └── Mentor Agent
        │
        ▼
       LLM
```

Do not prematurely turn this into a giant multi-agent system.

Prove that **one good mentor agent** can create a valuable learning loop first.

---

# What OSS Sensei Must NOT Become

OSS Sensei should **not** become:

* another Copilot clone,
* an AI code generator,
* an automatic PR fixer,
* a generic chatbot attached to GitHub,
* a glorified linter,
* a tutorial generator,
* or a system that completes projects while students watch.

Whenever a new feature is proposed, ask:

> **Does this feature make the student a better engineer, or does it merely make completing the project easier?**

Sometimes those goals overlap.

When they conflict, OSS Sensei should favor **learning**.

---

# Success

OSS Sensei succeeds when a student starts by asking:

> "What code should I write?"

and eventually starts asking:

> "What are the trade-offs between these designs?"

It succeeds when the student begins noticing problems **before the Sensei points them out**.

It succeeds when reviews gradually become shorter because the student has internalized previous feedback.

And ultimately, it succeeds when the student no longer needs OSS Sensei.

---

## North Star

> **OSS Sensei turns a GitHub repository into an engineering apprenticeship.**

Build software.

Make mistakes.

Get reviewed.

Understand why.

Improve.

Repeat.

The code is the project.

**The engineer is the product.**
