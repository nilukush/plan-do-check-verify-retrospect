# Contributing to PLAN-DO-CHECK-VERIFY-RETROSPECT

Thank you for your interest in contributing to the PDCVR framework! This document provides guidelines and instructions for contributing.

## How to Contribute

### Reporting Issues

If you find a bug, have a suggestion, or want to ask a question, please [open an issue](../../issues).

When reporting issues, please include:
- Clear description of the problem
- Steps to reproduce (if applicable)
- Expected behavior vs actual behavior
- Environment details (OS, tool versions, etc.)
- Any relevant screenshots or error messages

### Pull Requests

1. **Fork the repository** and create your branch from `master`
2. **Make your changes** following the framework principles
3. **Test thoroughly** - ensure your changes work as intended
4. **Commit your changes** with clear, descriptive messages
5. **Push to your fork** and submit a pull request

### Development Setup

This repository contains prompts, templates, and agent configurations - no build process required. Simply:

```bash
git clone https://github.com/nileshkumar/gh/plan-do-check-verify-retrospect.git
cd plan-do-check-verify-retrospect
```

### Contribution Guidelines

#### Prompt and Template Improvements

When contributing to prompts or templates:
- **Follow the PDCVR framework** structure
- **Maintain TDD emphasis** - test-first discipline is core to this framework
- **Be explicit** - clear, unambiguous instructions work best with AI
- **Include examples** - show what good vs bad looks like
- **Document changes** - explain why you made specific modifications

#### Subagent Configurations

When contributing new or improved subagents:
- **Use the existing format** - YAML frontmatter with name, description, model
- **Focus on enterprise-grade** - production-ready, no hardcoded values
- **Include usage examples** - show when and how to use the agent
- **Test thoroughly** - verify the agent works as intended

#### Documentation

When improving documentation:
- **Keep it concise** - focus on what developers need to know
- **Use clear language** - avoid jargon where possible
- **Include examples** - practical examples are most helpful
- **Maintain consistency** - follow existing style and structure

## Framework Principles

All contributions should align with these core principles:

1. **TDD Discipline** - Tests before implementation
2. **Enterprise-Grade** - Production-ready quality standards
3. **Process Safeguards** - Clear acceptance criteria and checkpoints
4. **Quality Control** - Iterative review and refinement

## Code of Conduct

- Be respectful and constructive
- Focus on what is best for the community
- Show empathy towards other community members

## License

By contributing, you agree that your contributions will be licensed under the [MIT License](LICENSE).

## Getting Help

- Open an issue for bugs or feature requests
- Check existing documentation first
- Be patient - this is a community project

Thank you for contributing to making AI-assisted coding better for everyone!
