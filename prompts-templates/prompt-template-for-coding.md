# CONTEXT

- Today's Date: [Input today's date here]
- Timezone: [Input timezone you are in]
- Workspace Directory: [Your directory or repo from where Claude Code should be working]
- OS: [Operating System]
- Model Name:	[Desktop or Laptop name]
- Chip: [Intel or Silicon]
- Uname: [Output of uname -a in terminal]
- Read @CLAUDE.md
- [Any other reads like PRD or Figma or other files]
- Read, analyze and understand current workspace and repo(s).

# REQUEST REQUIREMENT INSTRUCTION

- Based on this and previous conversation
  - Environment: [local / dev / staging / pre-prod / prod]
  - Ports: [use standard / non-stanard ports for services if you are running multiple systems]

**[YOUR DETAILED REQUIREMENT / INSTRUCTION / SCREENSHOTS / IMAGES / PDF / FILES GOES HERE]**

## CURRENT SITUATION
[Provide a detailed explanation of the situation or problem you are working on right now]

## OBJECTIVE
[Provide a 1-liner set of objectives that you want to achieve as a user, as a product or something else]

## TASK
[Provide an extremely detailed list of tasks that needs to be completed. Preferred is that you focus on 1 task at a time.]

## QUESTIONS
[Provide a detailed list of questions that you want to ask the LLM]

---

## PART 1: HIGH-LEVEL ANALYSIS

### Objective

Solve the business problem through thorough analysis before any code generation. Prevent implementation without sufficient context, code duplication, and unnecessary regressions.

### Analysis Requirements

#### 1. Business Problem Definition

- State the explicit business problem in clear, non-technical terms
- Identify the core objectives and success criteria
- Define what problem we are solving and why it matters
- Clarify any ambiguities before proceeding

#### 2. Mandatory Codebase Investigation

Before proposing any solution, perform comprehensive searches for:

- Similar existing implementations or patterns
- Related business logic that addresses comparable problems
- Existing data structures and models relevant to this domain
- System dependencies and integration points
- Configuration patterns currently in use
- Potential code reuse opportunities

#### 3. Technical Approach Evaluation

- Propose multiple alternative approaches (minimum 2-3 options)
- For each approach, analyze:
  - Alignment with existing system patterns
  - Impact on current architecture
  - Dependencies and integration requirements
  - Trade-offs and considerations
  - Complexity and maintenance implications
- Recommend preferred approach with clear rationale

#### 4. Context and Constraints

- Identify system boundaries and limitations
- Note architectural patterns that must be followed
- Document integration requirements with existing systems
- List external dependencies
- Highlight potential risks or challenges

### Output Constraints

- Focus on "WHAT" and "WHY", NOT "HOW"
- Human-readable analysis, not implementation details
- No code snippets or specific implementation steps
- No premature technical decisions
- Clear, structured prose that documents the approach

### Iterative Refinement

- Pause for clarification questions before proceeding
- Incorporate human feedback and additional context
- Iterate on analysis until approach is validated
- Document final analysis for project records (e.g., Jira story)

---

## PART 2: DETAILED PLANNING

### Trigger

Begin detailed planning only after:

- High-level analysis is complete and approved
- Approach has been validated and agreed upon
- All clarification questions have been resolved

### Objective

Create an executable roadmap that breaks work into atomic, testable increments with clear accountability and transparency.

### Execution Context

- Implementation will follow strict TDD discipline
- Work proceeds step-by-step with human supervision
- Each step will be tagged for optimal model selection
- All work occurs within the same thread context
- Plan serves as contract between human and AI

### Planning Requirements

#### 5. Implementation Steps Structure

Create numbered, sequential steps where each step:

- Is atomic and independently testable
- Has clear start and completion criteria
- Specifies expected outcomes
- Identifies verification methods
- Can be completed in a single focused iteration

#### 6. TDD Discipline Enforcement

For every implementation step:

- MUST write failing test(s) FIRST before any production code
- Specify test scope (unit/integration/e2e)
- Define test cases covering happy path and edge cases
- Set success criteria: test must fail initially, then pass
- Include refactoring opportunities after green phase

#### 7. Acceptance Criteria

Each step must include:

- Clear definition of "done"
- Observable outcomes or artifacts
- Verification checkpoints
- Rollback conditions if step fails

#### 8. Process Safeguards

- Limit implementation attempts to 3 iterations per step
- After 3 failed attempts, STOP and request human guidance
- Include explicit checkpoints for human review
- Flag high-risk or complex steps requiring extra attention

#### 9. Plan Format

```
Step N: [Descriptive Title]
├─ Objective: [What this step achieves]
├─ Prerequisites: [Dependencies from prior steps]
├─ Test First:
│  ├─ Test type: [unit/integration/e2e]
│  ├─ Test cases: [List specific scenarios]
│  └─ Expected: [Test must fail because feature not implemented]
├─ Implementation:
│  ├─ Scope: [Minimal code to make test pass]
│  └─ Constraints: [Patterns/standards to follow]
├─ Acceptance Criteria:
│  ├─ Tests pass: [Specific test outcomes]
│  ├─ No regressions: [Existing tests still pass]
│  └─ Code quality: [Refactoring completed]
├─ Verification:
│  └─ [How to confirm step completion]
└─ Stop/Go Decision: [Proceed to next or pause for review]
```

#### 10. Regression Protection

- Identify all existing tests that might be affected
- Plan for regression test execution after each step
- Define strategy for handling unexpected test failures
- Include contingency for plan divergence

#### 11. Transparency Requirements

- Each step must be observable and trackable
- Progress must be measurable
- Blockers and issues must be immediately visible
- Allow human to follow agent's actions clearly

### Plan Execution Guidelines

#### During Implementation:

- Proceed step-by-step through numbered plan
- Complete each step fully before moving to next
- Report completion and verification results for each step
- Tag steps for optimal model selection

#### When Plan Divergence Occurs:

Stop and assess when:

- Regression test failures emerge
- Initial understanding was incorrect or incomplete
- New information changes the approach
- Complexity exceeds original estimation
- Side tasks or blockers appear

#### Divergence Response:

- Complete current step if safe to do so
- Document reason for divergence
- Request human guidance on:
  - Whether to re-plan from current position
  - Whether to address side task first
  - How to handle unexpected discovery
- After resolution, explicitly identify where to resume in original plan

#### Re-planning Protocol:

- Summarize steps completed successfully
- Identify current position in codebase
- Propose adjusted plan from current state
- Maintain same rigor and structure as original plan
- Get approval before proceeding

---

## CRITICAL REMINDERS

- NO implementation without analysis and plan
- NO code generation during analysis phase
- NO skipping test-first discipline
- NO proceeding without clear acceptance criteria
- NO more than 3 attempts without human intervention
- Analysis output belongs in project documentation
- Plan serves as binding contract for implementation

---

## DELIVERABLES

### After Analysis:

- Written analysis document (for Jira/project records)
- Recommended approach with rationale
- Identified integration points and dependencies
- Human approval to proceed

### After Planning:

- Numbered, detailed implementation plan
- Test specifications for each step
- Acceptance criteria for all steps
- Verification methods
- Contingency protocols

---

## Use TDD

### Test-Driven Development Guidelines

Follow strict TDD methodology for all code development:

### Core TDD Cycle (Red-Green-Refactor):

#### Red Phase - Write Failing Test First

- Write a single, focused test that describes one specific behavior
- Ensure the test fails for the right reason (feature not implemented yet)
- Run the test to confirm it fails

#### Green Phase - Write Minimal Code

- Write the simplest code that makes the test pass
- Don't add extra functionality or over-engineer
- Run the test to confirm it passes

#### Refactor Phase - Improve Code Quality

- Refactor both test and implementation code
- Maintain all passing tests
- Improve design, remove duplication, enhance readability
- Run all tests to ensure nothing breaks

### TDD Principles:

- Never write production code without a failing test first
- Write tests at the appropriate level (unit, integration, or e2e)
- Keep tests independent, isolated, and deterministic
- Test behavior and outcomes, not implementation details
- Use descriptive test names that explain the expected behavior
- Arrange-Act-Assert (AAA) pattern for test structure
- One assertion per test when possible (or related assertions)
- Mock external dependencies appropriately

### Testing Standards:

- Maintain high code coverage (aim for 80%+ coverage)
- Include edge cases, boundary conditions, and error scenarios
- Test both happy paths and failure paths
- Write tests that serve as documentation
- Keep tests fast and efficient
- Ensure tests are maintainable and readable

### Implementation Flow:

1. Understand the requirement clearly
2. Write the test case first
3. Run and watch it fail
4. Implement minimal code to pass
5. Run and watch it pass
6. Refactor if needed
7. Repeat for next requirement

### Benefits to Achieve:

- Improved code design and architecture
- Built-in regression protection
- Living documentation through tests
- Faster debugging and issue identification
- Confidence in refactoring
- Reduced defect rates

Follow this methodology rigorously to ensure robust, well-tested, and maintainable code.

---

- Update and Compact @CLAUDE.md

---

## CRITICAL REMINDERS

- Ultrathink
- Use TDD
- Ask questions
- Share sources for your answer
- Do an extremely detailed careful deep research analysis step by step.
- Always propose use only most standard enterprise grade right correct perfect best solution.
- Search online if you have to.
- Use all agents available at your disposal as per needs and requirements. (you are not using agents available to you)
- You will iterate multiple times before providing your answer or inputs. Review, rate and score each answer or input and then finally provide 1 recommended answer or input based on review, rating and scoring if it is above a certain threshold.
