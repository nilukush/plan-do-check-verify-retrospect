# PLAN-DO-CHECK-VERIFY-RETROSPECT (PDCVR)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code](https://img.shields.io/badge/Claude-Code-orange)](https://claude.ai/code)
[![Framework](https://img.shields.io/badge/Framework-PDCVR-blue)](https://github.com/nileshkumar/gh/plan-do-check-verify-retrospect)

A comprehensive framework and toolkit for AI-assisted software development using continuous improvement cycles.

## Overview

This framework provides a structured methodology for development work with AI assistants like Claude Code. It extends the **Plan-Do-Check-Act (PDCA)** cycle with explicit **VERIFY** and **RETROSPECT** phases to ensure quality, continuous improvement, and enterprise-grade results.

## Framework Components

### 1. Prompts & Templates (`prompts-templates/`)

| Phase | File | Purpose |
|-------|------|---------|
| **PLAN** | `plan.md` | High-level analysis and detailed planning with TDD discipline |
| **DO** | `prompt-template-for-coding.md` | Unified template combining all phases |
| **CHECK** | `check.md` | Completeness check and closure verification (8 phases) |
| **VERIFY** | (integrated in check.md) | Build verification, testing validation, deployment readiness - uses `build-verification-agent` |
| **RETROSPECT (ACT)** | `retrospect.md` | Post-session analysis and improvement identification |

### 2. Specialized Subagents (`claude-code-subagents-for-coding/`)

25+ specialized AI agents for different development tasks:

- **Orchestration**: `orchestrator-ai-router`, `memory-ai-context-manager`
- **Architecture**: `software-architect-hld`, `system-analyzer`
- **Planning**: `product-manager-prd`, `user-story-creator`, `ui-ux-designer`
- **Execution**: `enterprise-coder-ai`, `executor-ai-agent`
- **Quality**: `qa-automation-engineer`, `quality-analyzer-scorer`, `build-verification-agent`
- **Infrastructure**: `devops-infra-deployer`, `git-repository-manager`
- **Documentation**: `documentation-generator`, `web-research-analyst`

## Development Workflow

```mermaid
graph LR
    A[PLAN] --> B[DO]
    B --> C[CHECK]
    C --> D[VERIFY]
    D --> E{Complete?}
    E -->|No| B
    E -->|Yes| F[RETROSPECT]
    F --> A
```

### PLAN Phase
- Business problem definition
- Mandatory codebase investigation
- Technical approach evaluation (2-3 options)
- Detailed implementation steps with TDD discipline

### DO Phase
- Execute following the plan with appropriate subagents
- Strict TDD: Red-Green-Refactor cycle
- Incremental changes with verification
- Maximum 3 attempts per step before human intervention

### CHECK Phase
- Goal alignment verification
- Technical quality checks (code quality, testing coverage)
- Regression and integration validation
- Documentation and knowledge transfer review

### VERIFY Phase
- Build & deployment verification
- Quality gates and standards compliance
- Risk assessment and rollback readiness
- Completeness score (minimum 40/50 = 80%)

### RETROSPECT (ACT) Phase
- **Note**: ACT and RETROSPECT are the same phase
- Critical moments analysis
- Waste and wrong path identification
- Success metrics calculation
- "The One Most Valuable Change" for next session

## Core Principles

- **TDD Discipline**: Tests first, then implementation
- **Enterprise-Grade**: No hardcoded values, multi-tenant aware
- **Process Safeguards**: Atomic steps, clear acceptance criteria
- **Quality Control**: Iterative review until consensus

## Usage with Claude Code

1. Read the appropriate prompt template before starting work
2. Follow the structured workflow (PLAN → DO → CHECK → VERIFY → RETROSPECT)
3. Use specialized subagents via the Task tool for complex tasks
4. Run completeness checks before creating PRs
5. Conduct retrospectives to capture learnings

See [CLAUDE.md](CLAUDE.md) for detailed guidance on using this framework with Claude Code.

## License

See [LICENSE](LICENSE) file.
