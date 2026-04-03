# AI Agent Guide: Page Design Editor

This editor supports two importable JSON formats:

1. Native Fabric payload (`canvas` key) exported by `Save JSON`.
2. AI-friendly payload (`elements` array) for direct LLM generation.

## AI JSON Contract

Use:

- `spec`: `page-design-ai-v1`
- `version`: `1`
- `pageSize`: `a3|a4|a5|a6|b4|b5|letter|legal|tabloid|executive|statement|folio`
- `orientation`: `portrait|landscape`
- `backgroundColor`: color string (prefer hex)
- `elements`: list of drawable objects

Supported element `kind` values:

- `text`
- `rect`
- `circle`
- `line`
- `image`

Reference schema: `ai-project-schema-v1.json`  
Starter template: `ai-project-template.json`

## Coordinates and Units

- Coordinates are in editor pixels (canvas is 96 DPI base).
- `x`/`y` are top-left positions for most elements.
- `line` uses `x1,y1,x2,y2` as local points, with optional `left,top`.

## Recommended Prompt For LLMs

Generate strict JSON only (no markdown) for `page-design-ai-v1`.  
Use finite numeric values and valid `pageSize`/`orientation`.  
Prefer hex colors and include only supported element kinds.

