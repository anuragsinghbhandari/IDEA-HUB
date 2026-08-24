# Repo Sensei — Project Goal

## The Idea

**Repo Sensei** is an AI-powered mock interviewer that analyzes a candidate's real GitHub repository and conducts a technical interview about the project.

The core principle is:

> **If it's on your résumé, you should be able to defend it.**

Students often build projects for learning, internships, placements, hackathons, or their résumés.

But building a project and being able to **explain it under interview pressure** are different skills.

Repo Sensei bridges that gap.

Give Repo Sensei a repository.

It studies the actual project and interviews the candidate about:

* what the project does,
* architecture,
* technology choices,
* implementation details,
* important pieces of code,
* database design,
* APIs,
* security,
* testing,
* performance,
* failure scenarios,
* scalability,
* trade-offs,
* and decisions the candidate would change today.

The result should feel less like:

> "Give me common interview questions about FastAPI."

and more like:

> "I read your project. Now defend your engineering decisions."

---

# The Problem

Project-based interview questions are difficult to prepare for because they are not generic.

An interviewer can look at a résumé and ask:

> Tell me about this project.

That simple question can quickly become:

> Why did you choose PostgreSQL?

> Why not MongoDB?

> Walk me through your authentication flow.

> Why are you using refresh tokens?

> What happens if two requests update this resource simultaneously?

> Where are passwords hashed?

> Why is this function asynchronous?

> How are errors propagated?

> What happens if Redis becomes unavailable?

> How would this architecture behave with one million users?

A candidate may have genuinely built the project and still struggle to explain these decisions.

Worse, modern AI tools make it increasingly easy to create code that the developer only partially understands.

The repository may work.

The résumé may look impressive.

But an interviewer can expose shallow understanding with two words:

> **Why this?**

Repo Sensei exists to ask that question before the real interviewer does.

---

# Core Principle

> **Building something is not the same as understanding everything you built.**

Repo Sensei should identify the gap between:

```text id="wh9ex3"
I used this technology.
```

and:

```text id="gggbvh"
I understand why it exists,
what problem it solves,
how I implemented it,
what trade-offs it introduces,
what can go wrong,
and what alternatives I could have chosen.
```

The second is what interviews demand.

---

# The Experience

The candidate provides a GitHub repository.

For example:

```text id="dq56l4"
github.com/user/auth-service
```

Repo Sensei analyzes the repository.

It examines things such as:

```text id="svm0q6"
README
Project structure
Dependencies
Important modules
Database models
API routes
Authentication
Configuration
Tests
Docker setup
CI/CD
Git history
Architecture decisions
```

Suppose it discovers:

```text id="5r0u7a"
FastAPI
PostgreSQL
SQLAlchemy
JWT
Redis
Docker
GitHub Actions
```

The interview begins.

---

# Stage 1 — Project Overview

Start as a real interviewer might.

> Give me a two-minute overview of your project.

The candidate should explain:

* what problem it solves,
* who it is for,
* the major components,
* and their contribution.

Repo Sensei evaluates whether the explanation is:

* clear,
* structured,
* technically accurate,
* appropriately detailed,
* and consistent with the repository.

---

# Stage 2 — Technology Decisions

Repo Sensei should question the technologies actually found in the repository.

For example:

> Why did you choose FastAPI?

Then:

> What advantages did it give this particular project?

Then:

> What would have changed if you used Django instead?

For PostgreSQL:

> Why did you choose a relational database?

Then:

> Which relationships in your data model benefit from that decision?

The goal is not to test whether the candidate memorized:

> "PostgreSQL is an open-source relational database."

The goal is to determine whether they understand:

> **Why PostgreSQL belongs in this project.**

---

# Stage 3 — Architecture

Repo Sensei should understand the project's structure well enough to ask architectural questions.

Examples:

> Walk me through what happens when a login request reaches your API.

> Why are routes, services, and database operations separated?

> Where does dependency injection happen?

> Which component owns authentication?

> Where are configuration values loaded?

The candidate should be able to mentally navigate their own system.

---

# Stage 4 — Code-Specific Questions

This is one of the most important features.

Repo Sensei should ask questions based on **actual code**, not merely the technologies listed in `requirements.txt` or `package.json`.

For example:

> In `auth/service.py`, this function catches `IntegrityError`. What situation are you protecting against?

Or:

> This database operation uses an async session. Why?

Or:

> You call this function inside the request lifecycle. What happens if it takes five seconds?

Or:

> Why did you create this abstraction instead of calling the database directly?

This makes every interview specific to the repository.

Two FastAPI projects should produce substantially different interviews.

---

# Stage 5 — Follow the Candidate's Answers

Repo Sensei should not behave like a static question generator.

The interview should be adaptive.

Candidate:

> We use Redis for caching.

Repo Sensei:

> What exactly are you caching?

Candidate answers.

> What does the cache key look like?

Candidate answers.

> How long does the value remain cached?

Candidate answers.

> What happens if the underlying database record changes before that?

Now the interview has naturally reached:

> Cache invalidation.

This is how real technical interviews often work.

The interviewer starts broad and follows the candidate deeper until they discover the boundary of their understanding.

Repo Sensei should do the same.

---

# Depth Levels

Questions can progress through increasing levels of understanding.

```text id="kptcrp"
Level 1 — WHAT
"What does Redis do in your project?"

Level 2 — WHY
"Why did you need Redis?"

Level 3 — HOW
"How is caching implemented?"

Level 4 — TRADE-OFF
"What disadvantages does this introduce?"

Level 5 — FAILURE
"What happens if Redis becomes unavailable?"

Level 6 — SCALE
"What happens with multiple application instances?"

Level 7 — ALTERNATIVE
"What could you use instead?"

Level 8 — REFLECTION
"Would you make the same decision today?"
```

A strong candidate should progressively survive deeper questioning.

Repo Sensei does not need to reach Level 8 for every component.

It should intelligently choose where to probe.

---

# Failure Scenarios

One of the best ways to test engineering understanding is to ask:

> **What happens when something goes wrong?**

Examples:

> What happens if the database becomes unavailable halfway through this operation?

> What happens if Redis goes down?

> What happens if two users make this request simultaneously?

> What happens if the external API takes 30 seconds to respond?

> What happens if this background job runs twice?

> What happens if a JWT is stolen?

> What happens if deployment succeeds but the database migration fails?

These questions force the candidate to think beyond the happy path.

---

# Scalability Questions

Repo Sensei should identify components that could become bottlenecks and ask realistic scaling questions.

For example:

> Your application currently handles 100 users.

> Suppose it now handles 1 million.

> What breaks first?

Then follow the candidate's reasoning.

Possible areas include:

```text id="izd3u1"
Database
Indexes
Connection pools
Caching
Queues
Rate limiting
Storage
Network calls
Concurrency
State management
Deployment architecture
```

The goal is not to turn every project into a distributed-systems interview.

Questions should match the complexity of the project and candidate.

---

# Trade-Off Questions

Repo Sensei should frequently ask:

> Why this instead of that?

Examples:

> Why SQL instead of NoSQL?

> Why REST instead of GraphQL?

> Why JWT instead of server-side sessions?

> Why polling instead of WebSockets?

> Why this embedding model?

> Why this vector database?

> Why synchronous processing instead of a queue?

The important part is not finding one universally correct answer.

Engineering decisions have trade-offs.

Repo Sensei should evaluate whether the candidate understands them.

---

# Resume Claim Mode

One of the most valuable future features is comparing the repository with the candidate's résumé.

Input:

```text id="x6zhf5"
GitHub Repository
        +
Resume Project Description
```

Suppose the résumé says:

> Built a scalable RAG pipeline reducing retrieval latency by 40%.

Repo Sensei should investigate.

> Your résumé says retrieval latency improved by 40%. How did you measure that?

Then:

> What was the baseline?

Then:

> What dataset did you benchmark?

Then:

> How many measurements did you take?

Then:

> Are you talking about average, p50, or p95 latency?

The purpose is not to attack the candidate.

It is to discover claims they cannot currently defend **before an interviewer discovers them**.

---

# Resume-to-Repository Consistency

Repo Sensei should eventually identify situations where:

```text id="bms16q"
Résumé claim
     ≠
Repository evidence
```

For example:

Résumé:

> Implemented comprehensive automated testing.

Repository:

```text id="sh8wnb"
tests/
    test_login.py
```

Three tests exist.

Repo Sensei might ask:

> Your résumé describes the project as having comprehensive automated testing. What parts of the application are currently covered?

This gives the candidate an opportunity to either:

1. improve the project, or
2. make the résumé claim more accurate.

Both outcomes are useful.

---

# Git History

When available, Git history can provide another source of interview context.

Repo Sensei could investigate:

* major refactors,
* technologies introduced later,
* reverted implementations,
* large architectural changes,
* commit quality,
* development progression.

Questions could include:

> I noticed authentication was initially implemented differently and later refactored. What motivated that change?

This tests something valuable:

> **Can the candidate explain how the project evolved?**

Real projects rarely appear fully formed.

---

# Adaptive Interviewing

Repo Sensei should build a temporary model of the candidate's understanding during the interview.

For example:

```yaml id="9bjpxy"
project_overview:
  strong

backend_architecture:
  strong

database_design:
  developing

authentication:
  strong

testing:
  weak

caching:
  superficial

deployment:
  developing

system_design:
  developing

technical_communication:
  strong
```

The interviewer can then spend more time where understanding appears shallow.

If someone clearly understands JWT authentication, stop interrogating JWT.

If they claim Redis experience but struggle with basic caching questions, investigate further.

Interview time should be spent finding **knowledge boundaries**, not proving what is already obvious.

---

# Interview Modes

Eventually Repo Sensei could support different interview styles.

## Quick Interview

Approximately 10 minutes.

Focus on:

* project overview,
* major architecture,
* important technology choices.

## Standard Interview

Approximately 20–30 minutes.

Include:

* architecture,
* implementation,
* trade-offs,
* code-specific questions,
* failure scenarios.

## Deep Dive

Approximately 45–60 minutes.

Behave like a demanding technical interviewer.

Explore:

* implementation details,
* architecture,
* scaling,
* security,
* failures,
* design alternatives,
* résumé claims.

## Targeted Interview

Focus on one area:

```text id="jv5u71"
Backend
Database
ML
System Design
Security
Testing
DevOps
Architecture
```

These modes are later features.

The MVP does not need all of them.

---

# Post-Interview Report

After the interview, Repo Sensei should generate actionable feedback.

Example:

```text id="19a90g"
PROJECT INTERVIEW REPORT

Project:
Authentication Service

Project Explanation       Strong
Architecture              Strong
Database Design           Developing
Authentication            Strong
Testing                    Weak
Caching                    Weak
Scalability               Developing
Technical Communication   Strong

Strongest Area:
You clearly understand the authentication flow and can
explain the access/refresh token lifecycle.

Knowledge Gap:
You use Redis successfully but struggled to explain cache
invalidation and failure behavior.

Potential Interview Risk:
Your résumé describes the service as "highly scalable,"
but you could not explain the current database bottleneck.

Review Before Interview:
- Cache invalidation
- Database connection pooling
- Horizontal scaling and application state

Repository Improvement:
Add integration tests covering refresh-token reuse.

Resume Review:
Consider making the scalability claim more specific unless
you have benchmark evidence.
```

The feedback should tell the candidate:

> **What should I study or improve before the real interview?**

---

# Voice First

Like DSA Sensei, the ideal interaction should eventually be voice-based.

Project interviews happen verbally.

The candidate needs practice explaining complex technical systems clearly without writing an essay first.

Ideal flow:

```text id="c40d4w"
AI Interviewer
      ↓
asks repository-specific question
      ↓
Candidate answers verbally
      ↓
Speech → Text
      ↓
Answer analyzed
      ↓
Repository context considered
      ↓
Adaptive follow-up
```

An avatar may eventually improve immersion.

But again:

> **The avatar is not the product.**

The quality of repository understanding and adaptive questioning is the product.

---

# Initial MVP

Do not begin by implementing every possible repository analysis feature.

The MVP needs to prove one thing:

> **Can AI analyze a real repository well enough to conduct a useful project interview?**

Initial flow:

```text id="y63hgz"
GitHub Repository
       ↓
Repository ingestion
       ↓
Understand project structure
       ↓
Identify important technologies/components
       ↓
Generate initial interview context
       ↓
Interview begins
       ↓
Candidate answers
       ↓
Adaptive follow-up
       ↓
Interview ends
       ↓
Feedback report
```

The first version needs roughly four capabilities.

## 1. Repository Understanding

Understand:

* project purpose,
* technologies,
* structure,
* important files,
* major components.

## 2. Question Generation

Generate questions grounded in the repository.

## 3. Adaptive Follow-Ups

Use the candidate's previous answer and repository context to determine what to ask next.

## 4. Feedback

Identify:

* strong areas,
* weak areas,
* knowledge gaps,
* important concepts to review.

That is enough to test the core idea.

---

# Possible Architecture

A rough architecture:

```text id="u77uc7"
GitHub Repository
       │
       ▼
Repository Analyzer
       │
       ├── File structure
       ├── README
       ├── Dependencies
       ├── Important code
       ├── Configuration
       ├── Tests
       └── Git history
       │
       ▼
Repository Knowledge Model
       │
       ▼
Interview Engine
       │
       ├── Interview State
       ├── Candidate Model
       ├── Question Strategy
       └── Repository Context
       │
       ▼
      LLM
       │
       ▼
Adaptive Interview
       │
       ▼
Interview Report
```

Later:

```text id="scq37v"
Voice
Resume ingestion
Git history analysis
Architecture visualization
Interview history
Progress tracking
Specialized interview modes
AI avatar
```

Do not build those before proving the interview experience.

---

# Relationship With OSS Sensei

Repo Sensei and OSS Sensei operate at different stages.

## OSS Sensei

**Mentor while building.**

```text id="51mf5u"
Idea
 ↓
Issues
 ↓
Implementation
 ↓
Pull Requests
 ↓
Reviews
 ↓
Better engineering habits
```

## Repo Sensei

**Interviewer after building.**

```text id="klhwrq"
Finished Project
      ↓
Repository Analysis
      ↓
Technical Interview
      ↓
Knowledge Gaps
      ↓
Preparation
```

OSS Sensei asks:

> How can I help you become a better engineer while building this?

Repo Sensei asks:

> You built this. Do you actually understand and defend it?

They should remain conceptually separate even if they eventually share infrastructure.

---

# Relationship With DSA Sensei

DSA Sensei tests algorithmic solutions.

Repo Sensei tests engineering projects.

```text id="n96cyv"
DSA Sensei

Problem
   ↓
Solution
   ↓
Accepted
   ↓
Explain
   ↓
Defend


Repo Sensei

Project
   ↓
Repository
   ↓
Analyze
   ↓
Interview
   ↓
Defend
```

The shared philosophy is:

> **Producing something does not prove understanding.**

---

# The Sensei Philosophy

Together, the projects address three different stages of becoming an engineer.

```text id="ip7jhf"
                 SENSEI

        ┌──────────┼──────────┐
        │          │          │
       DSA        OSS        Repo
      Sensei     Sensei     Sensei
        │          │          │
   Algorithms  Engineering  Projects
        │          │          │
     Explain      Build      Defend
```

### DSA Sensei

> Don't just solve it. Defend it.

### OSS Sensei

> Don't just build software. Learn to engineer it.

### Repo Sensei

> If it's on your résumé, be ready to defend it.

All three share one idea:

> **Completion is not mastery.**

---

# What Repo Sensei Must NOT Become

Repo Sensei should not become:

* a generic interview-question generator,
* a repository summarizer pretending to be an interviewer,
* a résumé buzzword generator,
* a code-review bot,
* a system that asks the same questions regardless of repository,
* or an avatar demo with shallow repository understanding.

The central test for every feature should be:

> **Does this help the candidate discover whether they truly understand their own project?**

If not, it probably does not belong in the core product.

---

# Success

Repo Sensei succeeds when someone enters an interview knowing:

* exactly how to explain their project,
* why they chose their technologies,
* how the important parts work,
* where the architecture is weak,
* what trade-offs they made,
* what can fail,
* how they would scale it,
* what they would redesign,
* and which résumé claims they can actually defend.

The goal is not to memorize perfect interview answers.

The goal is to understand the project deeply enough that answers do not need to be memorized.

---

# North Star

> **Repo Sensei turns your GitHub repository into your project interviewer.**

You built it.

Now explain it.

Defend the decisions.

Find what you don't understand.

Fix the gaps.

Then walk into the real interview prepared.

**If it's on your résumé, you should be able to defend it.**
