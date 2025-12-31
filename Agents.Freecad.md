# FreeCAD Parametric Module Practices

Guidance for writing FreeCAD 1.0 parametric modules in Python with an
emphasis on clarity, stability, and maintainable parametric models.

## Principles
- Keep models simple: prefer fewer features with clear intent.
- Use verbose, descriptive parameter names; avoid ambiguous abbreviations.
- Separate data (parameters) from geometry construction.
- Make models deterministic and easy to rebuild.
- Break models into discrete parts when possible for clarity and reuse.

## Parameter Management (Spreadsheet First)
- Always use a `Spreadsheet::Sheet` for user-facing parameters when possible.
- Define spreadsheet aliases with verbose names and use them in expressions.
- Link feature dimensions to spreadsheet aliases, not hard-coded numbers.
- Keep units explicit in spreadsheet cells (e.g., mm, deg, cm) where supported.
- Set each parameter cell with an explicit unit default (e.g., `=4 in`).
- Document parameter intent in spreadsheet comments for quick audits.

## Spreadsheet Pitfalls
- Prefer `sheet.set("A1", "=...")` for formulas; `setExpression()` can fail with missing properties.
- Use valid alias names (letters/underscores); invalid aliases raise errors.
- `setComment()` is not always available; fall back to a comment column when needed.

## Properties and Naming
- Use long, readable variable and alias names (e.g., `wall_thickness_mm`).
- Name document objects consistently (e.g., `Body_Main`, `Sketch_Profile`).
- Add custom properties on top-level module objects when parameters are not
  in the spreadsheet (use appropriate `App::Property*` types).
- Group properties and set tooltips to improve discoverability.

## Modeling Patterns
- Prefer `PartDesign::Body` with Sketcher-driven features for solids.
- Drive sketches with constraints linked to spreadsheet aliases.
- Use datum planes/axes for stable references instead of edge/face picks.
- Keep cross-body references to a minimum; use ShapeBinders intentionally.
- Defer fillets/chamfers until late in the feature tree to reduce failures.

## Document and Recompute Discipline
- Accept a `doc` parameter; do not rely solely on `App.ActiveDocument`.
- Batch updates inside a transaction and recompute once at the end.
- Avoid repeated recomputes while building feature chains.
- Check for name collisions before adding objects with fixed names.

## GUI vs Headless Use
- Keep core generation logic in `App` and avoid `Gui` dependencies.
- Isolate view or selection logic behind optional GUI-only helpers.
- Ensure modules can run under `FreeCADCmd` for automation.
- Apply view changes only in assembly scripts and guard with `if App.GuiUp`.

## Robustness and Debuggability
- Validate shapes when debugging complex operations.
- Prefer clear error messages over silent fallbacks.
- Keep boolean operations minimal and isolated if required.
- Expect module caching; remove/hide obsolete objects or rebuild a fresh document after topology changes.

## API Usage Conventions
- Use `import FreeCAD as App` and explicit module imports (`Part`, `Sketcher`,
  `PartDesign`) rather than wildcard imports.
- Use `App.Vector`, `App.Rotation`, and `App.Placement` for transforms.
- Prefer `obj.Label` for user-facing text and `obj.Name` for stable references.

## Version and Compatibility
- Target FreeCAD 1.0 APIs; avoid deprecated or legacy behaviors.
- When unsure about API changes, check the Python console warnings and
  current FreeCAD 1.0 docs before coding around them.
