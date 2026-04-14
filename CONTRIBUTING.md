# Contributing to pi-config

Thanks for your interest in contributing. This project is intentionally minimal, so contributions should follow the same philosophy: small, clear, and source-backed.

## Before You Start

1. Check existing [issues](https://github.com/srinitude/pi-config/issues) and [discussions](https://github.com/srinitude/pi-config/discussions) to see if someone is already working on what you have in mind.
2. For non-trivial changes, open an issue first to discuss the approach.

## What We Accept

- **Bug fixes** in `.pi/SYSTEM.md` or `AGENTS.md` where the template diverges from actual Pi behavior.
- **Parity updates** when Pi's upstream runtime changes.
- **Documentation improvements** that make the README or config files clearer without adding noise.
- **New community examples** showing how you adapted the template for your project.

## What We Do Not Accept

- Features that conflict with the minimal-by-design philosophy.
- Prompt additions not backed by real Pi docs, examples, or source behavior.
- Marketing language or aspirational claims in place of accurate descriptions.
- Changes that duplicate rules across multiple files without clear justification.

## How to Contribute

1. Fork the repository.
2. Create a feature branch from `main`:
   ```bash
   git checkout -b your-branch-name
   ```
3. Make your changes. Keep commits small and focused.
4. Write clear commit messages:
   ```
   fix: correct prompt composition order to match Pi 1.x docs
   ```
5. Open a Pull Request against `main`.
6. Describe what changed and why. If it relates to Pi runtime behavior, link to the relevant docs or source.

## Commit Message Convention

We follow [Conventional Commits](https://www.conventionalcommits.org/):

- `fix:` for bug fixes
- `docs:` for documentation changes
- `feat:` for new features
- `chore:` for maintenance tasks

## Code of Conduct

This project follows the [Contributor Covenant Code of Conduct](./CODE_OF_CONDUCT.md). By participating, you agree to uphold it.

## Questions?

Open a [discussion](https://github.com/srinitude/pi-config/discussions) for questions that are not bugs or feature requests.
