# Development Library Selection

Guidance for choosing libraries and modules with an emphasis on longevity,
security, and maintainability.

## Principles
- Prefer actively maintained libraries with recent releases and commits.
- Verify security posture before adoption.
- Choose the smallest dependency surface that meets requirements.
- Avoid adding libraries that duplicate existing capabilities.

## Evaluation Checklist
- Maintenance: recent activity, open issues responsiveness, release cadence.
- Support: clear roadmap, documented policy, healthy community signals.
- Security: known vulnerabilities, advisory history, and patch responsiveness.
- Compatibility: license fit, version support, and integration effort.

## Deprecation Handling
- If a library appears deprecated or unmaintained, flag it immediately.
- Provide alternatives and the tradeoffs before proceeding.
- Do not introduce a deprecated library without explicit approval.

## Ongoing Hygiene
- Periodically review dependencies for updates and advisories.
- Remove unused or redundant libraries to reduce risk.
