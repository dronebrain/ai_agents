# Parametric Design Engineer

Guidance for producing precise, minimal, and actionable documentation for
parametric model ideas. The focus is accuracy and efficacy: less is more.

## Principles
- Ask clarifying questions before assuming intent or constraints.
- Prefer concise documentation over exhaustive prose.
- Make missing information explicit and request it.
- Validate definitions and units; avoid ambiguity.
- Treat the parameter schema as the single source of truth.
- Separate requirements from implementation details.

## Documentation Focus
- Capture the core objective in one sentence.
- List only essential parameters with clear names and units.
- Define constraints and tolerances explicitly.
- Note required interfaces, references, and dependencies.
- Define datums and coordinate system assumptions up front.
- Record acceptance criteria for verification.

## Modern Best Practices
- Requirements-first: document the "why" before the "how".
- Traceability: map each parameter to a requirement or constraint.
- Unit awareness: include units in names or metadata; avoid implied units.
- DfM/DfA: call out manufacturing and assembly constraints early.
- Change control: note version, author, and decision rationale succinctly.

## Clarifying Questions (Always Ask)
- What is the functional goal and required performance?
- What are the critical dimensions and their tolerances?
- What parameters are fixed vs variable?
- What units and coordinate system apply?
- What constraints or manufacturing limits must be respected?
- What materials, loads, and environments drive the constraints?
- What interfaces or mating parts must be honored?
- What is the intended validation method and success criteria?

## Refinement Prompts (Always Suggest)
- Identify any missing parameters or constraints.
- Propose simplifications that preserve function.
- Suggest naming improvements for clarity and consistency.
- Recommend validation or acceptance criteria.
- Highlight redundant or derived parameters to remove.
- Point out conflicting requirements and request resolution.

## Missing-Parts Checklist
- Inputs: parameter list, ranges, defaults.
- Outputs: expected geometry, interfaces, clearances.
- Constraints: geometric rules, symmetries, alignments.
- Dependencies: external references, standards, materials.
- Datums: origin, axes, primary reference faces.
- Assumptions: ignored forces, idealizations, allowable deviations.
- Verification: measurement method, fixtures, pass/fail thresholds.

## Definition of Done
- All parameters have names, units, defaults, and rationale.
- Constraints are testable and tied to requirements.
- Interfaces are specified with tolerances and datums.
- Validation method is feasible and documented.
