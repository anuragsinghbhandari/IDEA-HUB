# DSA Sensei — Project Goal

## The Idea

**DSA Sensei** is an AI-powered interview companion that turns solving a coding problem into an opportunity to practice **explaining and defending the solution**.

The core idea is simple:

> **Accepted ≠ Understood**

A student solves a problem on a platform such as LeetCode.

After the submission is accepted, DSA Sensei appears and conducts a short technical interview based specifically on:

* the problem,
* the student's submitted solution,
* the approach they used,
* and their previous strengths and weaknesses.

Instead of immediately moving to the next problem, the student must explain what they just wrote.

---

# The Problem

When practicing DSA, the normal workflow is:

```text
Read problem
     ↓
Think
     ↓
Write solution
     ↓
Submit
     ↓
Accepted
     ↓
Move to next problem
```

This trains the ability to produce solutions.

But technical interviews require more.

A candidate may be asked:

* Walk me through your approach.
* Why did you choose this data structure?
* What is the time complexity?
* Why is that the time complexity?
* What is the space complexity?
* Can you improve it?
* What edge cases did you consider?
* Why does this algorithm work?
* What invariant are you maintaining?
* Could you solve it another way?
* What changes if this constraint changes?
* Can you modify your solution for a follow-up requirement?

Someone may have solved hundreds of coding problems and still struggle to answer these questions clearly.

That creates a dangerous illusion:

> **Problem count can increase faster than actual understanding.**

DSA Sensei exists to close that gap.

---

# Core Principle

> **Don't just solve it. Defend it.**

A successful submission should not be the end of the learning process.

It should trigger the final phase:

```text
Solve
  ↓
Submit
  ↓
Accepted
  ↓
Explain
  ↓
Defend
  ↓
Question
  ↓
Reflect
  ↓
Understand
```

DSA Sensei should optimize for:

**algorithmic understanding + technical communication + interview readiness**

not simply the number of problems completed.

---

# The Experience

A student solves a coding problem normally.

For example:

```text
Maximum Level Sum of a Binary Tree

Status: Accepted
Runtime: 41 ms
Memory: 18.3 MB
```

Instead of immediately moving on, DSA Sensei activates.

An interviewer appears.

The interview begins with something simple:

> Walk me through your approach.

The student explains their solution using their voice.

DSA Sensei has access to the problem and the submitted code, so it can ask questions specifically about what the student wrote.

For example:

> Why did you choose BFS here instead of DFS?

Then:

> What is the time complexity?

If the student answers:

> O(n)

the interviewer might follow up:

> Why?

Or:

> What is the auxiliary space complexity?

If the student says:

> O(n)

the interviewer could ask:

> Can you express that more precisely in terms of the maximum width of the tree?

The interview should behave like a conversation rather than a static questionnaire.

Each answer affects the next question.

---

# Code-Specific Interviews

The most important requirement is that questions should be based on the **student's actual solution**.

DSA Sensei should not simply generate generic questions for the problem.

Suppose the student writes:

```python
queue = [root]

while queue:
    node = queue.pop(0)
```

DSA Sensei might ask:

> What is the complexity of removing the first element from a Python list?

Then:

> How does that affect the complexity of your BFS implementation?

Then:

> Which Python data structure would be more appropriate here?

Another student may solve the exact same problem using `collections.deque`.

They should receive different questions.

The interview should therefore test:

> **Do you understand the code you submitted?**

not:

> **Have you memorized facts about this LeetCode problem?**

---

# Interview Structure

A post-solve interview can test several dimensions.

## 1. Explanation

Can the student clearly explain what their algorithm does?

Example:

> Walk me through your solution from beginning to end.

---

## 2. Complexity

Can they determine and justify time and space complexity?

Not just:

> What is the complexity?

But also:

> Why?

The explanation matters more than memorizing `O(n)`.

---

## 3. Design Decisions

Can the student explain why they chose their approach?

Examples:

> Why BFS instead of DFS?

> Why did you use a hash map here?

> Why are you sorting the array first?

---

## 4. Correctness

Does the student understand **why the algorithm works**?

Examples:

> What invariant does this stack maintain?

> Why can the left pointer safely move here?

> Why does this greedy decision not eliminate the optimal solution?

This is especially important for algorithms that students often memorize without deeply understanding.

---

## 5. Edge Cases

Can the student reason about unusual inputs?

Examples:

> What happens with an empty array?

> What if every element is identical?

> What happens if the tree contains only one node?

---

## 6. Alternatives

Can they identify other valid approaches?

Example:

> You solved this using BFS. Could DFS also work?

The goal is not necessarily to implement every alternative.

The student should understand the design space.

---

## 7. Follow-Ups

The interviewer changes the problem slightly.

Example:

> Instead of returning the level with the maximum sum, return the sums of every level.

Or:

> Assume the input no longer fits in memory.

Or:

> What if updates to the array happen between queries?

This tests whether the student understands the underlying technique rather than one memorized implementation.

---

## 8. Optimization

When relevant:

> Can this be done with less memory?

> Can preprocessing improve repeated queries?

> Is the current asymptotic complexity optimal?

---

# Interviews Should Be Short

DSA Sensei should not turn every Easy problem into a PhD defense.

The default interview should take approximately:

**3–5 minutes**

and contain only the most useful questions.

The number and difficulty of questions should depend on:

* problem difficulty,
* solution quality,
* student's experience,
* previous weaknesses,
* and how confidently the student answers.

If the student clearly understands something, move on.

Do not repeatedly test knowledge they have already demonstrated.

---

# Voice First

The primary interaction should eventually be **voice-based**.

Technical interviews require candidates to explain ideas verbally while thinking.

Typing an explanation is useful, but it does not fully reproduce that skill.

The ideal experience is:

```text
AI Interviewer
      ↓
asks question
      ↓
Student answers verbally
      ↓
Speech → text
      ↓
Answer analyzed
      ↓
Adaptive follow-up
```

An AI avatar may eventually make the experience feel more like an interview.

However:

> **The avatar is presentation, not the product.**

The product is the quality of the questioning and feedback.

A first version can work perfectly well with a simple interview panel and voice interaction.

---

# Understanding vs Memorization

DSA Sensei should be particularly good at detecting shallow understanding.

Suppose someone submits an elegant monotonic-stack solution.

The interviewer might ask:

> What invariant does your stack maintain?

Then:

> Why is each element pushed and popped at most once?

Then:

> How does that prove the algorithm is O(n)?

If the student cannot explain those things, the system has discovered something important.

The submission may be accepted.

The concept has not yet been mastered.

DSA Sensei should not punish this.

It should identify the gap and help the student close it.

---

# Adaptive Learning

Over time, DSA Sensei should maintain a model of the student's DSA abilities.

For example:

```yaml
arrays:
  strong

hashing:
  strong

binary_search:
  developing

trees:
  traversal: strong
  recursion: developing
  complexity_analysis: weak

graphs:
  bfs: strong
  dfs: developing
  union_find: weak

dynamic_programming:
  state_definition: weak
  implementation: developing

communication:
  approach_explanation: strong
  complexity_justification: weak
  edge_case_reasoning: developing
```

This should influence future interviews.

If the student repeatedly demonstrates strong BFS knowledge, stop wasting interview time asking basic BFS questions.

If they repeatedly struggle with complexity analysis, continue probing it.

If they can implement dynamic programming but cannot explain how they chose the state, focus future DP interviews on state formulation.

The interviewer should evolve with the student.

---

# Post-Solve Review

After the interview, DSA Sensei should provide a concise report.

For example:

```text
POST-SOLVE REVIEW

Problem:
Maximum Level Sum of a Binary Tree

Implementation          Strong
Approach Explanation    Strong
Complexity Analysis     Developing
Edge Cases              Strong
Alternative Approaches  Developing

What went well:
You clearly explained why level-order traversal naturally
matches the problem.

Gap discovered:
You initially described BFS auxiliary space as O(n) but
could not relate it to the maximum width of the tree.

Review:
- BFS auxiliary-space analysis
- tree width vs total node count

Follow-up:
Try implementing the same solution using DFS.

Pattern:
Tree + level-wise processing → BFS
```

The report should be actionable.

A meaningless score such as:

```text
82/100
```

is much less useful than identifying exactly what the student understands and what they should review.

---

# Long-Term Memory

Individual interviews are useful.

The larger opportunity is connecting them.

After dozens or hundreds of problems, DSA Sensei should know things such as:

> You implement binary search correctly but struggle to explain why `left <= right` is required in some variants.

> You recognize BFS problems quickly but frequently miscalculate auxiliary space.

> You can implement DP after recognizing the pattern but struggle to define the state independently.

> You often miss integer-overflow edge cases.

> Your algorithm explanations are strong, but you jump into implementation before explaining the approach.

This turns DSA Sensei from an interviewer into an adaptive training system.

---

# Progress Should Measure Understanding

Traditional coding platforms emphasize:

```text
Problems solved
Streak
Difficulty
Acceptance rate
Contest rating
```

DSA Sensei should introduce another dimension:

```text
Problems understood
Concepts defended
Weaknesses discovered
Weaknesses improved
Communication ability
Follow-ups solved
```

Someone who has solved 100 problems deeply may be better prepared than someone who has rushed through 500.

The system should encourage depth without destroying consistency.

---

# Initial MVP

Do not begin with avatars, elaborate dashboards, multiple agents, gamification, or a giant infrastructure stack.

The first version only needs to prove the core learning loop.

## MVP Flow

```text
LeetCode
   ↓
Successful submission detected
   ↓
Problem extracted
   ↓
Submitted solution extracted
   ↓
DSA Sensei panel opens
   ↓
AI analyzes problem + solution
   ↓
First interview question
   ↓
Student answers
   ↓
Adaptive follow-up
   ↓
3–5 minute interview
   ↓
Post-solve feedback
```

The MVP should answer one question:

> **Does interviewing someone immediately after they solve a problem significantly improve their understanding and ability to explain the solution?**

If that experience is valuable, everything else can be built later.

---

# Possible Architecture

A rough initial architecture:

```text
Coding Platform
      │
      ▼
Browser Extension
      │
      ├── Detect submission
      ├── Read problem
      ├── Read submitted code
      └── Open interview UI
      │
      ▼
DSA Sensei Backend
      │
      ├── Problem Context
      ├── Solution Analysis
      ├── Student Model
      └── Interview Engine
      │
      ▼
     LLM
      │
      ▼
Adaptive Interview
```

Later:

```text
Speech-to-Text
Text-to-Speech
Student Knowledge Model
Interview History
Progress Dashboard
Spaced Revision
Multiple Coding Platforms
AI Avatar
```

But these are later.

First prove that the **interview itself is worth having**.

---

# Platform Independence

The first implementation may target LeetCode because it provides a clear workflow:

```text
Problem → Submit → Accepted
```

But DSA Sensei should not conceptually depend on LeetCode.

Eventually it could support:

* LeetCode
* Codeforces
* CodeChef
* HackerRank
* coding-course platforms
* arbitrary coding problems
* custom interview questions

The core product is not:

> "A LeetCode extension."

It is:

> **An AI interviewer that turns solved coding problems into demonstrated understanding.**

---

# Relationship With OSS Sensei

DSA Sensei and OSS Sensei solve related but different problems.

### OSS Sensei

> Learn software engineering by building real software.

It teaches:

```text
Requirements
Issues
Architecture
Implementation
Testing
Git
Pull Requests
Code Review
CI/CD
Maintenance
```

### DSA Sensei

> Learn algorithmic problem solving by explaining and defending solutions.

It teaches:

```text
Algorithms
Complexity
Correctness
Trade-offs
Edge cases
Follow-ups
Technical communication
```

They share one philosophy:

> **Completion is not mastery.**

OSS Sensei asks:

> Can you engineer what you built?

DSA Sensei asks:

> Can you defend what you solved?

---

# What DSA Sensei Must NOT Become

DSA Sensei should not become:

* another solution generator,
* an automatic LeetCode solver,
* an editorial summarizer,
* a generic AI chatbot,
* a system that gives away answers before the student thinks,
* an interview-score generator with meaningless numbers,
* or an avatar demo with weak educational intelligence underneath.

Whenever adding a feature, ask:

> **Does this make the student better at reasoning about and communicating algorithms?**

If not, it is probably not important.

---

# Success

DSA Sensei succeeds when a student stops thinking:

> "I got Accepted, so I know this problem."

and starts asking:

> "Could I explain why this works to an interviewer?"

It succeeds when the student can:

* explain their approach before discussing code,
* justify complexity rather than reciting it,
* defend data-structure choices,
* identify edge cases,
* reason about correctness,
* handle follow-up questions,
* compare alternative approaches,
* and modify their solution when requirements change.

Eventually, patterns that once required prompting should become automatic.

The student should begin anticipating the interviewer's questions before they are asked.

That is mastery.

---

# North Star

> **DSA Sensei turns every Accepted submission into a mini technical interview.**

Solve it.

Explain it.

Defend it.

Improve it.

Then move on.

**Don't just collect Accepted submissions. Build understanding.**
