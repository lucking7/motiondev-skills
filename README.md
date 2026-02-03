# Motion Dev Skills

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Motion](https://img.shields.io/badge/Motion-v5.2.0-purple.svg)](https://motion.dev)

AI agent skill for the **Motion** animation library (formerly Framer Motion). Provides comprehensive documentation, 336 code examples, and best practices for building fluid animations in React, Vue, and vanilla JavaScript.

## Installation

### Claude Code / OpenCode

```bash
# Clone to your skills directory
git clone https://github.com/lucking7/motiondev-skills.git ~/skills/motiondev-skills
```

Then reference in your agent configuration or load via skill command.

## Directory Structure

```
motiondev-skills/
├── SKILL.md              # Main skill definition (YAML frontmatter + content)
├── reference/
│   ├── examples.json     # 336 examples with metadata (116KB)
│   ├── examples.md       # Examples index for quick lookup
│   ├── javascript.md     # Vanilla JS patterns
│   ├── react.md          # React hooks & components
│   └── vue.md            # Vue 3 composition API
└── scripts/
    ├── get-example.sh    # Fetch full example code on-demand
    └── search-examples.sh # Search examples by keyword
```

## Usage

### Loading the Skill

```
Load skill: motion
```

### Key Capabilities

| Feature | Description |
|---------|-------------|
| **Quick Reference** | Common patterns for JS, React, Vue |
| **API Documentation** | All core APIs, hooks, and components |
| **336 Examples** | Searchable index with on-demand fetching |
| **Spring Physics** | Transition options and easing configs |
| **Best Practices** | Performance optimization, common pitfalls |

### Fetching Examples

```bash
# Search examples
./scripts/search-examples.sh "drag"

# Get full example code
./scripts/get-example.sh scroll-triggered-animations
```

## Data Source

Extracted from the official **Motion Studio MCP Server** (v5.2.0):
- Package: `motion-studio-mcp`
- Registry: https://api.motion.dev

## License

This skill package is MIT licensed.

Motion library is licensed under the [Motion License](https://github.com/motiondivision/motion/blob/main/LICENSE.md).
