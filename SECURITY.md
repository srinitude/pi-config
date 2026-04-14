# Security Policy

## Reporting a Vulnerability

If you discover a security vulnerability in this project, please report it responsibly.

**Do not open a public issue.**

Instead, email **kiren@fantasymetals.com** with:

1. A description of the vulnerability.
2. Steps to reproduce.
3. Potential impact.

You will receive a response within 72 hours acknowledging the report. We will work with you to understand and address the issue before any public disclosure.

## Scope

This project is a configuration template consisting of Markdown files. Security concerns are most likely to involve:

- Prompt injection vectors in `.pi/SYSTEM.md` or `AGENTS.md`
- Unintended agent behavior caused by template instructions
- Information disclosure through overly permissive agent policies

## Supported Versions

| Version | Supported |
| ------- | --------- |
| main    | Yes       |
