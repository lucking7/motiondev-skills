# Motion Skills

Motion animation library skills for Claude/AI agents.

## Installation

```bash
npx skills add lucking7/motiondev-skills@motion
```

## Structure

```
skills/
├── SKILL.md           # Main skill file
├── reference/         # API documentation
│   ├── react.md
│   ├── javascript.md
│   ├── vue.md
│   ├── examples.md    # 336 examples index
│   └── examples.json  # Examples metadata
└── scripts/
    ├── get-example.sh
    └── search-examples.sh
```

## Usage

Once installed, use the skill when building animations with Motion (Framer Motion):

- React animations with `motion.div`, `AnimatePresence`
- Gestures: drag, hover, tap, scroll
- Layout animations and spring physics
- SVG animations

## License

MIT
