# Retrospective Analysis Prompt for AI-Assisted Development Sessions

## Purpose & Context

Execute a comprehensive retrospective analysis of our recent development session to identify collaboration patterns, intervention effectiveness, and actionable improvements. This analysis focuses exclusively on controllable variables: prompt engineering, process design, and human-AI interaction patterns.

---

## Analysis Framework

### Phase 1: Session Summary

Provide a concise overview of the development session including:

- **Primary Objective**: What was the stated goal?
- **Scope Boundaries**: What was in/out of scope?
- **Deliverables Achieved**: What was successfully completed?
- **Deliverables Incomplete**: What remains pending and why?
- **Session Duration & Iteration Count**: Time invested and number of PDCA cycles

### Phase 2: Critical Moments Analysis

Identify and analyze the **2-3 pivotal moments** that most significantly impacted session success or failure:

For each critical moment, document:

1. **Timestamp/Context**: When did this occur in the workflow?
2. **Trigger Event**: What precipitated this moment? (e.g., unclear requirement, AI misunderstanding, design decision)
3. **Decision Point**: What choices were available?
4. **Action Taken**: What decision was made and by whom (human/AI)?
5. **Impact Assessment**: 
   - Immediate consequences
   - Downstream effects on remaining work
   - Success/failure contribution (quantify if possible)
6. **Alternative Paths**: What could have been done differently?
7. **Root Cause**: Why did this moment become critical?

### Phase 3: Human Intervention Effectiveness Analysis

Evaluate the quality and timing of human interventions:

**Successful Interventions**:

- Which human corrections or guidance were most valuable?
- What characteristics made these interventions effective? (timing, specificity, clarity)
- Were there early signals the AI could have recognized to request guidance proactively?

**Missed Intervention Opportunities**:

- Where did the AI proceed sub-optimally without seeking clarification?
- What red flags should have triggered a pause-and-verify moment?
- Which ambiguities should have been escalated earlier?

**Intervention Patterns**:

- Was there a pattern to when interventions were needed? (e.g., requirements interpretation, architecture decisions, test design)
- Did intervention frequency increase/decrease as the session progressed?

### Phase 4: Technical & Process Insights

#### Collaboration Patterns

Analyze the collaboration dynamics:

1. **Communication Clarity**: Rate the precision of requirements, feedback, and questions (1-10 scale)
2. **Iterative Refinement**: How many iterations did typical tasks require?
3. **Assumption Management**: Were assumptions explicitly stated and validated?
4. **Context Retention**: Did the AI maintain critical context throughout the session?
5. **Plan Adherence**: Frequency and severity of deviations from the established plan

#### Acceleration Opportunities

Identify what would have accelerated progress:

1. **Prompt Improvements**: What additional context or constraints in initial prompts would have prevented rework?
2. **Process Adjustments**: Which workflow steps could be reordered or combined?
3. **Tooling Gaps**: Were there manual steps that could be automated?
4. **Pre-Session Preparation**: What research or setup should occur before engaging the AI?

#### Process Element Evaluation

Assess each process component:

| Process Element            | Effectiveness (1-10) | What Worked Well | Needs Improvement |
| -------------------------- | -------------------- | ---------------- | ----------------- |
| Requirements Specification |                      |                  |                   |
| Plan Phase                 |                      |                  |                   |
| Test-First Approach        |                      |                  |                   |
| Implementation Execution   |                      |                  |                   |
| Code Review & Validation   |                      |                  |                   |
| Retrospection              |                      |                  |                   |

### Phase 5: Waste & Wrong Path Analysis

**Wasted Effort Identification**:

- List work that was discarded or significantly reworked
- Estimate percentage of total effort that was non-productive
- Categorize waste: (a) Due to unclear requirements, (b) Due to AI misunderstanding, (c) Due to technical obstacles, (d) Due to changing requirements

**Wrong Path Detection**:

- When did we realize we were on a wrong path?
- What signals were present earlier that we missed?
- How can we detect similar situations faster in the future?

**Cost-Benefit of Corrections**:

- Did we correct course appropriately, or was there over-correction?
- Were there instances where we should have abandoned an approach sooner?

### Phase 6: Success Metrics Assessment

Calculate and evaluate the following metrics for commits in this session:

| Metric                                                                           | Target     | Actual | Status | Analysis                                          |
| -------------------------------------------------------------------------------- | ---------- | ------ | ------ | ------------------------------------------------- |
| **Large Commit %** <br>(>100 lines changed)                                      | <20%       |        |        | Why did large commits occur? Were they justified? |
| **Sprawling Commit %** <br>(>5 files touched)                                    | <10%       |        |        | Were changes properly scoped?                     |
| **Test-First Discipline Rate** <br>(% commits with both test & production files) | >50%       |        |        | How well did we maintain TDD?                     |
| **Avg Files Changed per Commit**                                                 | <5 files   |        |        | Were commits atomic?                              |
| **Avg Lines Changed per Commit**                                                 | <100 lines |        |        | Were changes bite-sized?                          |

**Metric Interpretation**:

- Which metrics exceeded targets? What enabled this success?
- Which metrics missed targets? What systemic issues caused this?
- Are there trade-offs between metrics? (e.g., smaller commits but more sprawling?)

### Phase 7: Prompt Engineering Recommendations

Based on the session analysis, suggest **specific prompt improvements**:

**Prompt Structure**:

- Should prompts include more/less context?
- Are there missing constraint specifications?
- Would examples or anti-patterns improve clarity?

**Prompt Content**:

- Which domain knowledge should be pre-loaded?
- What assumptions need explicit statement?
- Are success criteria sufficiently precise?

**Prompt Patterns to Adopt**:

- List 2-3 specific prompt patterns that would have improved this session
- Provide before/after examples for each

**Prompt Patterns to Avoid**:

- Identify ambiguous phrasing that led to misinterpretation
- Highlight over-constraint that limited creative problem-solving

### Phase 8: Developer Behavior Recommendations

Focus on **actionable changes to human behavior**:

**Pre-Session Preparation**:

1. What research should be completed before engaging the AI?
2. What documentation should be gathered?
3. What mental models or frameworks would improve session effectiveness?

**During-Session Behaviors**:

1. When should the developer intervene vs. let the AI continue?
2. How should ambiguity be addressed? (immediate clarification vs. iterative refinement)
3. What validation checkpoints should be mandatory?

**Post-Session Follow-Up**:

1. What documentation should be created/updated?
2. What learnings should be captured for future sessions?
3. What should be prepared for the next session?

### Phase 9: The One Most Valuable Change

After comprehensive analysis, identify the **SINGLE MOST IMPACTFUL CHANGE** for the next session:

**The Change**: [State it clearly in one sentence]

**Rationale**: 

- Why is this the highest-leverage improvement?
- What percentage of issues would this have prevented?
- How does this address root causes vs. symptoms?

**Implementation Plan**:

1. **Immediate Action**: What can be done right now?
2. **Template/Checklist**: What artifact ensures this becomes standard practice?
3. **Validation Method**: How will we verify this change is effective in the next session?

**Expected Impact**:

- Time savings estimate
- Quality improvement prediction
- Risk reduction assessment

---

## Output Format

Present your retrospective analysis in the following structure:

```markdown
# Session Retrospective - [Date] - [Project/Feature Name]

## Executive Summary
[2-3 paragraph overview of session and key findings]

## Session Metrics
[Phase 1 summary table]

## Critical Moments
[Phase 2: Detailed analysis of 2-3 pivotal moments]

## Intervention Analysis
[Phase 3: Human intervention effectiveness]

## Technical & Process Insights
[Phase 4: Collaboration patterns, acceleration opportunities, process evaluation]

## Waste Analysis
[Phase 5: Wasted effort and wrong paths]

## Success Metrics Dashboard
[Phase 6: Metrics table with analysis]

## Improvement Recommendations

### Prompt Engineering
[Phase 7: Specific prompt improvements with examples]

### Developer Behavior
[Phase 8: Actionable behavior changes]

## The One Most Valuable Change
[Phase 9: Single highest-impact improvement with implementation plan]

## Appendix
- Commit log summary
- Code quality metrics
- Time breakdown by activity
```

---

## Analysis Guidelines

1. **Be Brutally Honest**: Identify failures and inefficiencies without sugar-coating
2. **Focus on Root Causes**: Don't just describe symptoms; dig into underlying issues
3. **Be Specific**: Vague recommendations like "communicate better" are not useful; provide concrete, actionable guidance
4. **Quantify When Possible**: Use metrics, percentages, and time estimates
5. **Prioritize Controllable Variables**: Focus on what the developer can change (prompts, process, behavior)
6. **Balance Positive and Negative**: Acknowledge successes to understand what to repeat
7. **Think Systemically**: Consider how changes in one area affect others
8. **Be Forward-Looking**: Frame findings as learning opportunities for continuous improvement

---

## Execution Instructions

When performing this retrospective:

1. **Review the complete session transcript** if available
2. **Examine all commits** made during the session
3. **Calculate success metrics** accurately
4. **Identify patterns** across multiple occurrences, not isolated incidents
5. **Provide specific examples** to illustrate each point
6. **Connect findings** to show causal relationships
7. **Prioritize recommendations** by expected impact
8. **Format for readability** using tables, lists, and clear headers

The goal is to produce actionable intelligence that measurably improves the next development session.
