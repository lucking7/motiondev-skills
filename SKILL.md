---
name: motion
description: Use when building React animations with Motion (Framer Motion) - gestures (drag, hover, tap), scroll effects, spring physics, layout animations, SVG. Bundle: 2.3 KB (mini) to 34 KB (full). Troubleshoot: AnimatePresence exit, list performance, Tailwind conflicts, Next.js "use client".
---

# Motion Animation Library

## Overview

Motion (package: `motion`, formerly `framer-motion`) is the industry-standard animation library for JavaScript, React, and Vue. This skill is extracted from the official **Motion Studio MCP v5.2.0**, containing the complete documentation and 330+ production-ready examples.

**Source**: Official Motion Studio MCP Server
**Version**: 12.29.x (Latest Stable)
**Documentation**: 102 pages across JS, React, and Vue platforms
**Examples**: 330+ production-ready code examples

---

## When to Use

**Use when:**
- Building drag-and-drop interactions
- Creating scroll-triggered animations or parallax effects
- Implementing modals, carousels, or accordions with enter/exit animations
- Adding hover/tap feedback to interactive elements
- Animating shared elements between routes (layout animations)
- Working with spring physics or complex easing

**Don't use when:**
- Simple CSS transitions suffice (opacity, basic transforms)
- Bundle size is critical and animations are minimal (consider CSS)
- Server-side rendering without client hydration

---

## Installation

```bash
# React / JavaScript
npm install motion

# Vue
npm install motion-v

# Or with pnpm
pnpm add motion
```

---

## Quick Reference

### JavaScript (Vanilla)

```javascript
import { animate, scroll, inView, stagger } from "motion"

// Basic animation
animate("#box", { x: 100, opacity: 1 })

// With options
animate("li", { opacity: 0 }, { duration: 0.5, delay: stagger(0.1) })

// Spring animation
animate(element, { scale: 1.2 }, { type: "spring", stiffness: 300 })

// Scroll-linked
scroll(animate("#progress", { scaleX: [0, 1] }))

// Viewport detection
inView(".card", ({ target }) => {
  animate(target, { opacity: 1 })
})
```

### React

```tsx
import { motion, AnimatePresence, useScroll, useTransform } from "motion/react"

// Basic motion component
<motion.div
  initial={{ opacity: 0, y: 20 }}
  animate={{ opacity: 1, y: 0 }}
  exit={{ opacity: 0 }}
  transition={{ type: "spring" }}
/>

// Gestures
<motion.button
  whileHover={{ scale: 1.1 }}
  whileTap={{ scale: 0.95 }}
  drag="x"
  dragConstraints={{ left: 0, right: 100 }}
/>

// Layout animations
<motion.div layout layoutId="shared-element" />

// Scroll animations
const { scrollYProgress } = useScroll()
const y = useTransform(scrollYProgress, [0, 1], [0, -300])
```

### Vue

```vue
<script setup>
import { motion } from "motion-v"
</script>

<template>
  <motion.div
    :initial="{ opacity: 0 }"
    :animate="{ opacity: 1 }"
    :exit="{ opacity: 0 }"
    :whileHover="{ scale: 1.1 }"
  />
</template>
```

---

## API Reference

### Core Animation APIs

| API | Platform | Description |
|-----|----------|-------------|
| `animate()` | JS/React/Vue | Main animation function (2.3kb mini / 18kb hybrid) |
| `scroll()` | JS | Scroll-linked animations |
| `inView()` | JS | Viewport intersection detection |
| `hover()` | JS | Hover gesture detection |
| `press()` | JS | Press/tap gesture detection |
| `stagger()` | All | Stagger timing for multiple elements |

### React-Specific

| Component/Hook | Description |
|----------------|-------------|
| `motion.div` | Motion-enhanced HTML/SVG elements |
| `AnimatePresence` | Exit animation coordinator |
| `LayoutGroup` | Coordinate layout animations |
| `LazyMotion` | Bundle size optimization |
| `MotionConfig` | Global configuration |
| `useMotionValue()` | Reactive animation values |
| `useTransform()` | Derived motion values |
| `useSpring()` | Spring-animated values |
| `useScroll()` | Scroll progress tracking |
| `useAnimate()` | Imperative animation control |
| `useInView()` | Viewport detection hook |

### Motion Values

```javascript
import { motionValue, useMotionValue, useTransform, useSpring } from "motion/react"

// Create motion value
const x = useMotionValue(0)

// Transform to another value
const opacity = useTransform(x, [-100, 0, 100], [0, 1, 0])

// Spring-animated value
const springX = useSpring(x, { stiffness: 300, damping: 30 })

// Use in component
<motion.div style={{ x, opacity }} />
```

---

## Transition Options

### Duration-Based (Tween)

```javascript
{
  duration: 0.5,
  ease: "easeInOut", // or [0.4, 0, 0.2, 1]
  delay: 0.2,
  repeat: Infinity,
  repeatType: "reverse" // "loop" | "mirror"
}
```

### Physics-Based (Spring)

```javascript
{
  type: "spring",
  stiffness: 300,    // Higher = snappier
  damping: 30,       // Higher = less bounce
  mass: 1,           // Higher = more momentum
  bounce: 0.25,      // 0-1, alternative to stiffness/damping
  visualDuration: 0.5 // Visual duration target
}
```

### Easing Functions

- `"linear"`, `"easeIn"`, `"easeOut"`, `"easeInOut"`
- `"circIn"`, `"circOut"`, `"circInOut"`
- `"backIn"`, `"backOut"`, `"backInOut"`
- `"anticipate"`
- Custom: `[0.4, 0, 0.2, 1]` (cubic bezier)

---

## Common Patterns

### 1. AnimatePresence (Exit Animations)

```tsx
import { AnimatePresence, motion } from "motion/react"

// CRITICAL: AnimatePresence must stay mounted
<AnimatePresence>
  {isVisible && (
    <motion.div
      key="modal"  // Required unique key
      initial={{ opacity: 0 }}
      animate={{ opacity: 1 }}
      exit={{ opacity: 0 }}
    />
  )}
</AnimatePresence>
```

### 2. Layout Animations

```tsx
<motion.div layout>
  {isExpanded ? <FullContent /> : <Summary />}
</motion.div>

// Shared element transitions
<motion.div layoutId="card-123" />
```

### 3. Scroll Animations

```tsx
// Viewport-triggered
<motion.div
  initial={{ opacity: 0, y: 50 }}
  whileInView={{ opacity: 1, y: 0 }}
  viewport={{ once: true, margin: "-100px" }}
/>

// Scroll-linked
const { scrollYProgress } = useScroll()
const y = useTransform(scrollYProgress, [0, 1], [0, -300])
<motion.div style={{ y }} />
```

### 4. Drag Gestures

```tsx
<motion.div
  drag="x"
  dragConstraints={{ left: 0, right: 300 }}
  dragElastic={0.2}
  dragMomentum={true}
  dragSnapToOrigin
/>
```

### 5. SVG Line Drawing

```tsx
<motion.path
  initial={{ pathLength: 0 }}
  animate={{ pathLength: 1 }}
  transition={{ duration: 2, ease: "easeInOut" }}
/>
```

---

## Performance Best Practices

### 1. Bundle Size Optimization

```tsx
// Full bundle: ~34 KB
import { motion } from "motion/react"

// Optimized: ~4.6 KB
import { LazyMotion, domAnimation, m } from "motion/react"

<LazyMotion features={domAnimation}>
  <m.div animate={{ x: 100 }} />
</LazyMotion>

// Minimal: 2.3 KB
import { useAnimate } from "motion/react"
```

### 2. Hardware Acceleration

```tsx
<motion.div
  style={{ willChange: "transform" }}
  animate={{ x: 100, rotate: 45 }}
/>
```

### 3. Avoid Tailwind Transition Conflicts

```tsx
// WRONG - causes stuttering
<motion.div className="transition-all" animate={{ x: 100 }} />

// CORRECT
<motion.div animate={{ x: 100 }} />
```

### 4. Large Lists - Use Virtualization

```bash
pnpm add react-window
# or react-virtuoso, @tanstack/react-virtual
```

---

## Next.js Integration

### App Router (RSC)

```tsx
// components/motion-client.tsx
"use client"
import * as motion from "motion/react-client"
export { motion }

// app/page.tsx (Server Component)
import { motion } from "@/components/motion-client"
```

### Direct Client Component

```tsx
"use client"
import { motion } from "motion/react"

export function AnimatedCard() {
  return <motion.div animate={{ opacity: 1 }} />
}
```

---

## Accessibility

```tsx
import { MotionConfig } from "motion/react"

// Respect user's reduced motion preference
<MotionConfig reducedMotion="user">
  <App />
</MotionConfig>

// Options: "user" | "always" | "never"
```

---

## Known Issues & Solutions

### AnimatePresence Exit Not Working

**Problem**: Exit animations don't play
**Solution**: AnimatePresence must stay mounted, children need unique keys

```tsx
// WRONG
{isVisible && <AnimatePresence><motion.div /></AnimatePresence>}

// CORRECT
<AnimatePresence>
  {isVisible && <motion.div key="unique" />}
</AnimatePresence>
```

### Scrollable Container Layout Issues

**Solution**: Add `layoutScroll` prop

```tsx
<motion.div layoutScroll style={{ overflow: "auto" }}>
  <motion.div layout />
</motion.div>
```

### Fixed Position Layout Issues

**Solution**: Add `layoutRoot` prop

```tsx
<motion.div layoutRoot style={{ position: "fixed" }}>
  <motion.div layout />
</motion.div>
```

---

## Documentation Index

See `references/docs-index.md` for complete list of 102 documentation pages.

### Platform Coverage

| Platform | Docs | Topics |
|----------|------|--------|
| JavaScript | 33 | animate, scroll, inView, motionValue, effects |
| React | 42 | components, hooks, gestures, layout, scroll |
| Vue | 27 | directives, components, composables |

---

## Examples Index

The Motion Studio MCP includes **330+ production-ready examples** covering:

- **Basics**: Animations, springs, easings, stagger
- **Gestures**: Drag, hover, tap, pan
- **Layout**: FLIP animations, shared elements
- **Scroll**: Parallax, progress bars, reveal effects
- **Components**: Accordions, carousels, modals, tooltips
- **Integration**: Base UI, Radix, Tailwind, Three.js

### Example Categories

- Dialog & Modal
- Layout & Grid
- Forms & Input
- Navigation
- Cards & Lists
- Loading & Progress
- SVG & Path
- 3D & WebGL
- Experimental

---

## Related Resources

- **Official Docs**: https://motion.dev/docs
- **Examples Gallery**: https://motion.dev/examples
- **GitHub**: https://github.com/motiondivision/motion
- **npm**: https://www.npmjs.com/package/motion

---

## Motion Studio MCP

For enhanced AI integration, install the official Motion Studio MCP:

```json
{
  "mcpServers": {
    "motion": {
      "command": "npx",
      "args": ["-y", "https://api.motion.dev/registry.tgz?package=motion-studio-mcp&version=latest"]
    }
  }
}
```

Features:
- Full documentation search
- 330+ example code queries
- CSS spring generation
- Curve visualization

---

**Skill Version**: 1.0.0
**Source**: Motion Studio MCP v5.2.0
**Last Updated**: 2026-02-03
