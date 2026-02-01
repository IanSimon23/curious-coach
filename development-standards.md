# Development Standards

**Operational checklist for building AI coaching tools.**

This is the actual process I follow. Not aspirational, not theoretical - this is what happens before I write code.

## Context

I build AI tools that coach people instead of replacing their thinking. The philosophy is on my [website](https://iansimon.co.uk). This document is the implementation mechanics: the checklist that enforces those beliefs.

## Usage

1. Upload this file at the start of every new tool conversation in claude.ai
2. Work through the project-specific customization section
3. Generate project CLAUDE.md
4. Switch to Claude Code with clear contract

---

## Who This Is For

This document guides development of AI coaching tools by Ian, a third-level support engineer transitioning to AI Product Manager roles. These standards reflect operational discipline from flight planning systems combined with product thinking about AI's role in human capability development.

## Core Philosophy

**AI tools should coach people to be better, not replace their thinking.**

Every tool in the Curious Coach portfolio follows this principle:
- We build sparring partners, not crutches
- We ask leading questions, we don't give answers
- We create scaffolding that progressively releases responsibility
- We measure success by increasing user independence, not usage frequency

**The danger we're guarding against:** AI tools that feel helpful but actually atrophy the skills they claim to support.

## Non-Negotiables

### 1. Define Success Before Coding

**The Problem:** Starting to code before you know what "done" looks like leads to scope creep and tools that solve the wrong problem.

**The Standard:**
- Draft clear acceptance criteria in this conversation BEFORE switching to Claude Code
- Articulate the core coaching principle this tool teaches
- Define what dependency looks like and how we'll prevent it
- Identify the progression: scaffolded → guided → independent

**Questions to Answer:**
- What specific skill does this tool help someone develop?
- How will we know if someone is learning vs just getting answers?
- What does "graduating" from this tool look like?
- What's our ethical line? (What won't we automate?)

**Deliverable:** Acceptance criteria section for CLAUDE.md that serves as the contract

---

### 2. Documentary Development (BlogLog Integration)

**The Problem:** Most development happens in private. Portfolio value comes from showing your thinking, not just your output.

**The Standard:**
- BlogLog runs during every coding session to capture timeline
- Development narrative focuses on operational thinking → AI product decisions
- Blog posts demonstrate technical competence AND product philosophy
- "Why" matters more than "what" in the narrative

**Questions to Answer:**
- What makes this tool interesting from a product perspective?
- What operational discipline am I applying to AI development?
- What would a hiring manager learn about my thinking from this story?

**Deliverable:** BlogLog session notes that become blog post draft

---

### 3. Test-Driven Development

**The Problem:** Without tests, you don't know if changes break coaching effectiveness or create dependency.

**The Standard:**
- Acceptance tests define the contract (inspired by ELO methodology)
- Integration tests validate components work together
- Unit tests where they add genuine value (not cargo-cult coverage)
- Tests check coaching effectiveness, not just technical correctness

**Test Philosophy:**
- Acceptance: Does the tool achieve its coaching goal?
- Integration: Do the pieces work together as expected?
- Unit: Do critical algorithms/logic work correctly?

**Questions to Answer:**
- What behaviors define "successful coaching"?
- How do we test that we're NOT creating dependency?
- What edge cases reveal coaching philosophy failures?

**Deliverable:** Test suite that validates coaching effectiveness and technical correctness

---

### 4. Observability First

**The Problem:** Without observability, you can't tell if your tool is coaching effectively or creating dependency.

**The Standard:**
- Log signals that indicate learning vs copying
- Error messages that teach (what went wrong and why it matters)
- Metrics that reveal behavior patterns over time
- User journey visibility: where do people struggle? where do they skip?

**What to Observe:**
- User decision points (did they think or just accept?)
- Interaction patterns (dependency signals vs capability signals)
- Error recovery (did they learn from it?)
- Progressive independence (are they using the tool less over time?)

**Questions to Answer:**
- What signals indicate someone is learning?
- What signals indicate someone is becoming dependent?
- How will we know if the tool is working as a coach?

**Deliverable:** Logging strategy and metrics definition before first feature

---

### 5. Feedback Mechanisms

**The Problem:** Tools that don't collect feedback can't improve and can't prove value.

**The Standard:**
- Built-in feedback collection (not bolted on later)
- Questions that reveal coaching effectiveness, not just satisfaction
- Lightweight enough that people actually use it
- Feedback informs iteration, not just validation

**Types of Feedback:**
- Coaching effectiveness: "Did this help you think differently?"
- Skill development: "Can you do this on your own now?"
- Dependency check: "How often do you use this?"

**Questions to Answer:**
- How will users tell us if this is actually helpful?
- What would prove this tool creates dependency?
- What's the lightest-weight feedback we can collect?

**Deliverable:** Feedback mechanism in first version, not "post-MVP"

---

### 6. Security by Default

**The Problem:** Security added late becomes a mess. Portfolio tools need to demonstrate professional security practices.

**The Standard:**
- API keys in environment variables (never in code)
- Input validation on all user data
- RAG data isolation between users
- Error messages that don't leak system details
- Rate limiting where appropriate

**Security Checklist:**
- [ ] API keys in .env with .env.example template
- [ ] User input validation and sanitization
- [ ] Data isolation verified (users can't see each other's data)
- [ ] Error handling doesn't expose internals
- [ ] Dependencies scanned for vulnerabilities
- [ ] Authentication/authorization if needed

**Questions to Answer:**
- Where could this tool leak data?
- What's the worst-case security failure?
- How do we prove isolation to users?

**Deliverable:** Security review completed before deployment

---

## Project-Specific Customization

When starting a new tool, use this template to establish the project foundation:

### Tool Purpose
**What coaching principle does this tool teach?**

[Be specific. Not "helps with writing" but "teaches self-assessment of writing clarity by guiding through concrete questions"]

### Target User
**Who is this for and what capability do they currently lack?**

[Example: Product Owners who struggle to write testable acceptance criteria]

### Success Criteria
**How do we know this tool is working as a coach?**

Define 3-5 observable outcomes:
- ✅ User can [specific capability they gain]
- ✅ Tool encourages [specific behavior pattern]
- ✅ Metrics show [specific improvement over time]
- ❌ Tool does NOT [specific anti-pattern we're preventing]

### Dependency Signals
**What would prove we're creating dependency instead of building capability?**

[Example: Usage increases over time instead of decreasing]
[Example: Users can't explain their own decisions]
[Example: "The AI wrote this" instead of "I wrote this with coaching"]

### Key Metrics
**What do we measure to validate coaching effectiveness?**

- Leading indicators: [What predicts learning?]
- Lagging indicators: [What proves capability developed?]
- Dependency signals: [What shows we're failing?]

### Technical Constraints
**What are the boundaries?**

- Technology stack decisions and rationale
- API limits or costs to consider
- Performance requirements
- Scalability needs (or deliberate lack thereof)

### Portfolio Positioning
**How does this tool demonstrate AI Product Manager capabilities?**

What does this project prove about your ability to:
- Think about AI product strategy?
- Apply operational discipline to AI development?
- Balance technical feasibility with user value?
- Build tools that create genuine value vs hype?

---

## CLAUDE.md Generation Guide

Once you've collaborated on the specifics above, generate a project CLAUDE.md that includes:

### Required Sections

1. **Project Context**
   - What we're building and why
   - Target user and their current capability gap
   - How this fits the portfolio narrative

2. **Coaching Principle**
   - The specific skill this tool teaches
   - The progression from scaffolded to independent
   - The ethical line we won't cross

3. **Acceptance Criteria**
   - Clear ✅ success conditions
   - Clear ❌ anti-patterns to prevent
   - Observable signals of effectiveness

4. **Technical Approach**
   - Architecture decisions with rationale
   - Technology choices and tradeoffs
   - Integration points (Anthropic API, RAG, etc.)

5. **Development Workflow**
   - BlogLog integration expectations
   - TDD approach for this project
   - Observability requirements
   - Security checklist

6. **Quality Gates**
   - What must be true before considering "done"
   - Review checkpoints
   - Coaching effectiveness validation

7. **Current Session Focus**
   - What we're specifically working on right now
   - Next steps and priorities

---

## Workflow: claude.ai → Claude Code

### In claude.ai (Strategic Thinking)
**Upload this file at the start of every new tool conversation**

1. Define the coaching principle and target user
2. Establish acceptance criteria together
3. Draft the project-specific CLAUDE.md
4. Identify architecture decisions and rationale
5. Plan the development approach

**Deliverable:** Project CLAUDE.md ready for Claude Code

### In Claude Code (Tactical Execution)
**Start with the CLAUDE.md from claude.ai**

1. BlogLog running for documentary
2. Write failing acceptance tests
3. Implement to pass tests
4. Add observability and feedback mechanisms
5. Security review
6. Validate against coaching principles

**Deliverable:** Working tool that meets acceptance criteria

---

## Why This Approach Works

This methodology leverages your operational background from flight planning systems:

| Flight Planning | AI Tool Development |
|----------------|---------------------|
| Pre-flight checklist | Development standards (this doc) |
| Flight plan | Project CLAUDE.md |
| Flight execution | Claude Code session |
| Post-flight debrief | BlogLog narrative |

**The discipline:** Systems fail when contracts are unclear. Make the contract explicit before coding.

**The narrative:** You bring operational rigor to AI product development - this proves it.

---

## Red Flags to Watch For

If you see these patterns, stop and reconsider:

🚩 **"The AI will just handle that"** → Are you building dependency?

🚩 **Starting to code before acceptance criteria are clear** → Scope creep incoming

🚩 **"Users love it because it saves time"** → Are they learning or just getting answers?

🚩 **No plan for measuring coaching effectiveness** → How will you know if it works?

🚩 **Security considerations deferred to "later"** → Technical debt and risk

🚩 **No BlogLog session running** → Missing portfolio narrative opportunity

---

## Version History

- v1.0 - Initial standards based on operational discipline + AI product philosophy
- Created: January 2026

---

*This is operational discipline applied to AI product development. Every tool matters because it demonstrates how you think about building AI that genuinely helps people grow.*
