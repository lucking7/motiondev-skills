# Motion Examples Index

Curated examples from Motion Studio MCP. For full code, use the search script or visit motion.dev/examples.

## Basics

| Example | APIs | Description |
|---------|------|-------------|
| Basic animation | `animate` | Easing and duration options |
| Spring | `animate` | Spring animation basics |
| Rotate | `animate` | Rotation animation |
| Stagger | `animate`, `stagger` | Staggered list animations |
| Physical stagger | `animate` | Distance-based stagger delays |
| Bounce easing | `animate` | Custom easing functions |
| Color interpolation | `animate` | Linear RGB color blending |
| Parallax | `animate`, `scroll` | Scroll-based parallax effect |
| Scroll fade | `animate`, `scroll` | Fade in/out on scroll |
| Scroll pinning | `animate`, `scroll` | Horizontal scroll with sticky |
| Scroll-triggered | `animate`, `inView` | Viewport-triggered animations |
| Layered sections | CSS | Sticky scroll sections |

## Gestures

| Example | APIs | Description |
|---------|------|-------------|
| Hover | `animate`, `hover` | Hover state animations |
| Press | `animate`, `press` | Press/tap animations |
| Gestures | `animate`, `press`, `hover` | Combined gesture handling |

## Layout & Transitions

| Example | APIs | Description |
|---------|------|-------------|
| Lightbox | `press`, `animateView`, `spring` | Shared element lightbox |
| Shared view animation | `press`, `animateView`, `spring` | View Transitions API |
| Page wipe | `press`, `animateView`, `spring` | Full-page wipe transition |
| iOS App Store | `animateView` | Card-to-modal layout |

## Dialog & Modal

| Example | APIs | Description |
|---------|------|-------------|
| Modal dialog | `animate`, `hover`, `press` | HTML dialog with animations |
| Family-style dialog | `animate`, `hover`, `press`, `spring`, `animateView` | Animated confirmation |
| Accordion | `animate`, `press` | Expandable accordion |

## Buttons & Badges

| Example | APIs | Description |
|---------|------|-------------|
| Hold to confirm | `animate`, `motionValue`, `mapValue`, `styleEffect`, `press` | Long-press button |
| Multi state badge | `animate`, `motionValue`, `transform`, `press` | State machine badge |
| Material Design Ripple | `animate`, `hover` | Google-style ripple effect |

## Forms & Input

| Example | APIs | Description |
|---------|------|-------------|
| Characters remaining | `animate`, `transform` | Character counter |
| iOS slider | `animate`, `mix`, `motionValue`, `mapValue`, `transformValue`, `styleEffect` | iOS-style slider |
| Image reveal slider | `animate`, `motionValue`, `mapValue`, `styleEffect` | Before/after slider |

## Loading & Progress

| Example | APIs | Description |
|---------|------|-------------|
| Circle spinner | `animate` | Rotating spinner |
| Jumping dots | `animate`, `stagger` | Bouncing dots |
| Pulse dots | `animate`, `stagger` | Pulsing dots |
| Ripple | `animate`, `stagger` | Ripple effect |
| Progress bar | `animate`, `transform` | Animated progress |
| Fill text | `animate`, `transform` | Text fill loading |
| Infinite path drawing | `animate`, `motionValue` | SVG path animation |
| Loading overlay | `animate`, `transform` | Page loading overlay |

## Scroll Animations

| Example | APIs | Description |
|---------|------|-------------|
| Scroll highlight | `inView` | Skill showcase scroll |
| Scroll velocity | `scroll` | Velocity-based effects |

## Notifications

| Example | APIs | Description |
|---------|------|-------------|
| Notifications list | `animate`, `press` | Animated list CRUD |
| Notifications stack | `animate`, `press` | iOS-style stack |

## Text Animations

| Example | APIs | Description |
|---------|------|-------------|
| Split Text | `animate`, `stagger`, `splitText` | Word-by-word reveal |
| Split Text: Wavy | `animate`, `stagger`, `hover`, `splitText` | Wavy text effect |
| Split Text: Scatter | `animate`, `hover`, `splitText` | Pointer scatter effect |
| Reveal text | `animate`, `hover` | Hover text reveal |

## SVG

| Example | APIs | Description |
|---------|------|-------------|
| SVG loading spinner | `animate`, `stagger` | Segmented spinner |
| SVG path morphing | `animate` | Shape morphing with Flubber |

## Experimental

| Example | APIs | Description |
|---------|------|-------------|
| Conic gradient pointer | `motionValue` | Pointer-following gradient |
| Spring follow cursor | `animate`, `styleEffect` | Cursor-following spring |
| Tilt card | `animate` | 3D tilt on hover |
| Three.js | `animate` | Three.js integration |

## React-Specific

| Example | Description |
|---------|-------------|
| AnimatePresence list | Enter/exit list animations |
| Layout animations | FLIP layout transitions |
| Shared layout | Cross-component morphing |
| Drag to reorder | Sortable list |
| Carousel | Image carousel |
| Tabs | Tab switching |
| Tooltip | Animated tooltips |
| Dropdown menu | Menu animations |

## Vue-Specific

| Example | Description |
|---------|-------------|
| AnimatePresence | Vue exit animations |
| Layout animations | Vue layout transitions |
| Drag constraints | Bounded dragging |
| Scroll progress | Progress bar on scroll |

## Integration Examples

| Integration | Description |
|-------------|-------------|
| Radix UI | Animated Radix components |
| Base UI | MUI Base integration |
| Tailwind CSS | Tailwind + Motion |
| Next.js App Router | RSC integration |
| Three.js | 3D animations |

## Finding Examples

Use the search script to find examples by keyword:

```bash
./scripts/search-examples.sh "drag"
./scripts/search-examples.sh "scroll"
./scripts/search-examples.sh "modal"
```

Or visit: https://motion.dev/examples
