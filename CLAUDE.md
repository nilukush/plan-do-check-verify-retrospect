# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This repository contains the **PLAN-DO-CHECK-VERIFY-RETROSPECT (PDCVR)** framework - a comprehensive methodology and toolkit for AI-assisted software development. It extends the traditional Plan-Do-Check-Act (PDCA) cycle with explicit **VERIFY** and **RETROSPECT** phases to ensure quality, continuous improvement, and enterprise-grade results.

## Framework Structure

### Core Framework (PLAN-DO-CHECK-VERIFY-RETROSPECT)

Located in `prompts-templates/`:

- **`plan.md`** - Analysis and planning phase with strict TDD discipline. Two-part structure:
  - Part 1: High-level analysis (business problem definition, codebase investigation, technical approach evaluation)
  - Part 2: Detailed planning with atomic implementation steps, acceptance criteria, and regression protection
  - **Critical**: No implementation without completed analysis and plan

- **`check.md`** - Completeness check and closure verification (8 phases):
  - Phase 1-2: Goal alignment and technical verification
  - Phase 3-4: Regression and integration validation
  - Phase 5-6: Documentation and quality gates
  - Phase 7-8: Cleanup and risk assessment
  - Minimum passing score: 40/50 (80%)

- **`verify.md`** - (Integrated within check.md phases 6-8):
  - Build & deployment verification
  - Quality gates and standards compliance
  - Risk assessment and rollback readiness

- **`retrospect.md`** - Post-development retrospective analysis:
  - Critical moments analysis, human intervention effectiveness
  - Waste and wrong path analysis, success metrics assessment
  - Prompt engineering and developer behavior recommendations
  - Identifies "The One Most Valuable Change" for next session

- **`prompt-template-for-coding.md`** - Main unified template combining all phases

### Specialized Subagents

Located in `claude-code-subagents-for-coding/`:

**Orchestration & Management:**
- `orchestrator-ai-router.md` - Master coordinator for routing requests across specialized agents
- `memory-ai-context-manager.md` - State persistence across sessions

**Analysis & Architecture:**
- `system-analyzer.md` - Deep codebase analysis
- `software-architect-hld.md` - High-level design, System Analysis, Test Analysis
- `debug-analyzer-expert.md` - Issue investigation and resolution

**Planning & Requirements:**
- `product-manager-prd.md` - PRD creation and refinement
- `user-story-creator.md` - User story development
- `ui-ux-designer.md` - UI/UX design creation

**Implementation & Execution:**
- `enterprise-coder-ai.md` - Production-grade code implementation
- `executor-ai-agent.md` - Command execution and infrastructure operations
- `file-creator-enterprise.md`, `file-copy-enterprise.md` - File operations
- `file-move-rename-expert.md`, `file-deep-analyzer.md` - Advanced file operations
- `file-pattern-searcher.md` - Pattern-based code searching

**Quality & Testing:**
- `qa-automation-engineer.md` - Test automation
- `quality-analyzer-scorer.md` - Quality assessment
- `build-verification-agent.md` - Build and compilation verification

**Infrastructure & Deployment:**
- `devops-infra-deployer.md` - DevOps and deployment
- `git-repository-manager.md` - Git operations

**Documentation & Communication:**
- `documentation-generator.md` - Documentation updates
- `web-research-analyst.md` - Internet research

**Validation:**
- `repo-structure-validator.md` - Repository structure validation

## Development Workflow

When using this framework for development work:

1. **PLAN Phase**: Use `prompts-templates/plan.md` for thorough analysis before implementation
   - Business problem definition
   - Mandatory codebase investigation
   - Technical approach evaluation with multiple options
   - Detailed implementation steps with TDD discipline

2. **DO Phase**: Execute following the plan with appropriate subagents
   - Use `orchestrator-ai-router` to coordinate multiple agents
   - Use specialized subagents for specific tasks
   - Follow strict TDD: Red-Green-Refactor cycle
   - Incremental changes with verification at each step

3. **CHECK Phase**: Use `prompts-templates/check.md` for completeness verification
   - Goal alignment verification
   - Technical quality checks (code quality, testing coverage)
   - Regression and integration validation
   - Documentation and knowledge transfer review

4. **VERIFY Phase**: Use phases 6-8 of `prompts-templates/check.md` and invoke `build-verification-agent` for deployment readiness
   - Build & deployment verification
   - Quality gates and standards compliance
   - Risk assessment and rollback readiness
   - Completeness score (minimum 40/50 = 80%)
   - **Note**: This is the SAME as CHECK but uses the build-verification agent to ensure everything compiles successfully

5. **RETROSPECT (ACT) Phase**: Use `prompts-templates/retrospect.md` after completion
   - **Note**: ACT and RETROSPECT are the same phase
   - Analyze critical moments and intervention effectiveness
   - Identify waste and wrong paths
   - Calculate success metrics (commit quality, TDD discipline rate)
   - Define "The One Most Valuable Change" for next session

## Core Principles

### TDD Discipline
- **MUST** write failing tests first before any production code
- Red-Green-Refactor cycle for all development
- Tests at appropriate levels: unit, integration, e2e
- High coverage target (80%+)

### Enterprise-Grade Standards
- No hardcoded values - use environment variables, configuration files, secrets management
- Multi-pod, multi-container, multi-service, multi-tenant awareness
- Backward compatibility preservation
- Proper error handling, logging, and monitoring

### Process Safeguards
- Maximum 3 implementation attempts per step before human intervention
- Atomic, independently testable steps
- Clear acceptance criteria for each step
- Regression test execution after changes
- Plan divergence protocol with re-planning

### Quality Control Loop
- Rate Review and Score Agent evaluates work after completion
- Debugger AI Agent investigates issues
- Analyzer AI Agent re-investigates when needed
- Multiple iterations until consensus achieved

## Key Constraints

- **NO implementation without analysis and plan**
- **NO code generation during analysis phase**
- **NO skipping test-first discipline**
- **NO proceeding without clear acceptance criteria**
- **NO more than 3 attempts without human intervention**

## Subagent Usage

Use the Task tool to invoke specialized subagents based on task requirements:

```
Task(
  subagent_type="software-architect-hld",
  description="Create HLD document",
  prompt="[detailed requirements]"
)
```

Available subagent types are the filenames in `claude-code-subagents-for-coding/` without the `.md` extension (e.g., `orchestrator-ai-router`, `executor-ai-agent`, `system-analyzer`).

## Integration with Claude Code

This framework can be used directly with Claude Code by:
1. Reading the appropriate prompt template before starting work
2. Following the structured workflow (PLAN → DO → CHECK → RETROSPECT)
3. Using specialized subagents via the Task tool for complex tasks
4. Running completeness checks before creating PRs
5. Conducting retrospectives after completion to capture learnings
