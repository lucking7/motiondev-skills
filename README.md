# Motion MCP Skill

## Source

This skill is extracted from the official **Motion Studio MCP Server** (v5.2.0).

**Original Package**: `motion-studio-mcp`
**Registry**: https://api.motion.dev/registry.tgz
**Version**: Latest (extracted 2026-02-03)

## Contents

### Skill Definition

- `skill.md` - Main skill file with Motion animation library documentation, API reference, and best practices

### Reference Files

| File | Description | Source |
|------|-------------|--------|
| `references/docs-index.md` | Index of 102 documentation pages | Processed from MCP |
| `references/docs-metadata.json` | Full metadata for all docs | Processed from MCP |
| `references/complete-docs.md` | Complete documentation content | Processed from MCP |
| `references/all-docs-content.md` | All docs combined | Processed from MCP |
| `references/examples-list.md` | 330+ example index | Processed from MCP |
| `references/mcp-docs.mjs` | Original MCP docs source | `dist/es/resources/docs.mjs` |
| `references/mcp-examples.mjs` | Original MCP examples | `dist/es/manifest-examples.mjs` |
| `references/mcp-docs-manifest.mjs` | Original MCP docs manifest | `dist/es/manifest-docs.mjs` |

## Usage

This skill is automatically loaded when the agent uses the `motion` skill.

```
Load skill: motion
```

The skill provides:

1. **Quick Reference** - Common patterns for JS, React, and Vue
2. **API Reference** - All core APIs and hooks
3. **Transition Options** - Spring physics and easing configurations
4. **Common Patterns** - AnimatePresence, Layout, Scroll, Drag, SVG
5. **Performance Best Practices** - Bundle optimization, hardware acceleration
6. **Known Issues & Solutions** - Common pitfalls and fixes

## Updating

To update from the latest Motion Studio MCP:

```bash
# Download latest package
npm pack https://api.motion.dev/registry.tgz?package=motion-studio-mcp&version=latest

# Extract and copy files
tar -xzf motion-studio-mcp-*.tgz
cp package/dist/es/resources/docs.mjs references/mcp-docs.mjs
cp package/dist/es/manifest-examples.mjs references/mcp-examples.mjs
cp package/dist/es/manifest-docs.mjs references/mcp-docs-manifest.mjs

# Clean up
rm -rf package motion-studio-mcp-*.tgz
```

## License

Motion is licensed under the Motion License.
See: https://github.com/motiondivision/motion/blob/main/LICENSE.md
