
# DARKBOURNE: THE ECLIPSE INITIATIVE

## Project Overview

**Project:** DarkBourne Guild Recruitment Terminal

**Course:** ACS-3320 Web Design & Advanced CSS

**Repository:** microinteractions

**Due Date:** Thursday, November 19, 2026

**Technologies:** HTML5, CSS3

**JavaScript:** Not used

---

# Microinteraction 1: Recruitment Button

**Element:** `.recruit-button`

**Job:** FEEDBACK

**Purpose:** Communicates the current interaction state of the recruitment button through color, movement, shadows, and opacity.

### State Matrix

| State | Appearance | Behavior |
|---|---|---|
| Default | Purple background with light-purple border | Displays the primary recruitment action. |
| Hover | Lighter purple background and brighter glow | Indicates that the button is interactive. |
| Focus-visible | Cyan outline with additional glow | Makes keyboard focus clearly visible. |
| Active | Darker purple background | Button moves down 3px when pressed. |
| Disabled | Muted gray-purple background with reduced opacity | Communicates that the action is unavailable. |

### Motion Tokens

- Fast duration: `150ms`
- Base duration: `250ms`
- Easing: `cubic-bezier(0.2, 0.8, 0.2, 1)`

### Reduced-Motion Behavior

Button movement is removed while color, border, shadow, and opacity feedback remain.

---

# Microinteraction 2: DarkBourne Guild Card

**Element:** `.guild-card`

**Job:** ORIENTATION

**Purpose:** Guides visitors toward the recruitment section by animating the guild emblem and arrow when the card is hovered or keyboard-focused.

### State Matrix

| State | Parent Card | Guild Emblem | Arrow |
|---|---|---|---|
| Default | Standard surface and border | Normal size | Slightly reduced opacity |
| Hover | Lifts 5px with brighter border and shadow | Scales to 1.04 | Moves right 7px and becomes fully visible |
| Keyboard Focus | Cyan border and enhanced shadow | Scales to 1.04 | Moves right 7px and becomes fully visible |
| Reduced Motion | No lifting movement | No scaling | No horizontal movement; opacity feedback remains |

### CSS Techniques

- `.guild-card:hover .arrow`
- `.guild-card:hover .guild-emblem`
- `.guild-card:has(.card-link:focus-visible)`
- `.guild-card:has(.card-link:focus-visible) .arrow`

### Motion Tokens

- Base duration: `250ms`
- Easing: `cubic-bezier(0.2, 0.8, 0.2, 1)`

### Reduced-Motion Behavior

Card lifting, emblem scaling, and arrow movement are removed. Border, shadow, and opacity feedback remain.

---

# Microinteraction 3: Eclipse Synchronization Indicator

**Element:** `.eclipse-loader`

**Job:** ATTENTION

**Purpose:** Draws attention to the active synchronization process and communicates that the DarkBourne recruitment terminal is connecting with the Infinite Realms.

### Animation Details

- Animation type: Continuous looping animation
- Animation duration: `1800ms`
- Rotation easing: `linear`
- Glow easing: `ease-in-out`
- Pause control: Not required because the animation loops every 1.8 seconds.

### Animation Keyframe Matrix

| Keyframe | Rotation | Opacity | Visual Behavior |
|---|---:|---:|---|
| 0% | 0deg | 0.65 | Ring begins its orbit with a subdued glow. |
| 50% | 180deg | 1.0 | Ring reaches halfway through its rotation and maximum brightness. |
| 100% | 360deg | 0.65 | Ring completes its orbit and returns to its subdued glow. |

### Animation Techniques

- `@keyframes eclipse-spin`
- `@keyframes eclipse-glow`
- Multiple animations applied to one element.
- CSS custom properties for duration and easing.

### Reduced-Motion Replacement

| Keyframe | Rotation | Opacity | Visual Behavior |
|---|---|---:|---|
| 0% | None | 0.55 | Indicator begins with a subtle fade. |
| 50% | None | 1.0 | Indicator reaches full brightness. |
| 100% | None | 0.55 | Indicator fades back to its starting appearance. |

**Reduced-motion behavior:** Continuous rotation is removed and replaced with a gentle opacity animation lasting 2.4 seconds.

---

# Motion Design Tokens

| Token | Value | Purpose |
|---|---|---|
| `--duration-fast` | `150ms` | Quick interaction feedback |
| `--duration-base` | `250ms` | Standard transitions |
| `--duration-slow` | `600ms` | Longer transitions |
| `--duration-orbit` | `1800ms` | Eclipse animation |
| `--ease-out` | `cubic-bezier(0.2, 0.8, 0.2, 1)` | Smooth interaction movement |
| `--ease-linear` | `linear` | Continuous rotation |
| `--ease-gentle` | `ease-in-out` | Gradual opacity changes |

---

# Accessibility

- All interactive elements have visible `:focus-visible` styling.
- The recruitment form uses associated labels.
- The disabled recruitment button uses the native `disabled` attribute.
- The decorative eclipse ring uses `aria-hidden="true"`.
- The synchronization message uses `role="status"`.
- Reduced-motion preferences are supported through `prefers-reduced-motion`.
- Reduced-motion replacements preserve visual feedback instead of simply removing animations.

---

# Responsive Design

The layout adapts to smaller screens through CSS media queries.

- Navigation links wrap on smaller screens.
- Guild card content changes to a vertical layout.
- Recruitment form padding decreases on mobile.
- Hero typography scales with the viewport.
- Buttons remain accessible and usable on smaller screens.

---

# Final Completion Checklist

- [x] Microinteraction 1: Interactive control
- [x] Microinteraction 2: Parent/sibling trigger
- [x] Microinteraction 3: Looping animation
- [x] State matrix for interactive control
- [x] State matrix for parent/sibling trigger
- [x] Animation keyframe matrix
- [x] CSS comments identifying each element's job
- [x] Motion tokens used throughout
- [x] Visible keyboard focus states
- [x] Reduced-motion replacements
- [x] Responsive layout
- [x] HTML and CSS only
- [ ] Final browser testing
- [ ] GitHub commit and push
- [ ] GitHub Pages deployment
