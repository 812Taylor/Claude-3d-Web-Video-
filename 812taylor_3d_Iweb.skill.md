---
name: immersive-web-experience
version: 1.0.0
description: Build premium, experimental, interactive websites inspired by high-end immersive digital agency experiences. Treat typography, 3D, cursor input, scroll, sound, physics, transitions, and UI as one unified real-time experience rather than separate website effects. 
---

# Immersive Web Experience Skill

## Purpose

Use this skill when building a high-end website that should feel closer to an interactive digital installation, product film, or real-time 3D experience than a conventional marketing website.

The goal is not to create a page that merely contains animations. The goal is to create a coherent interactive system in which:

- typography is part of the visual composition,
- 3D objects are part of the interface,
- cursor movement is a meaningful input,
- scroll controls visual progression,
- sound provides feedback and atmosphere,
- transitions connect sections into one continuous experience,
- physics and procedural motion create believable physical behavior,
- UI remains minimal so the visual system has room to dominate,
- performance is treated as a first-class feature.

The reference aesthetic is a premium immersive digital-agency experience: highly editorial, cinematic, minimal, tactile, experimental, and technically sophisticated.

Do NOT blindly copy another website's exact branding, proprietary assets, source code, layout measurements, text, artwork, or visual identity. Recreate the underlying interaction principles and level of craft while creating an original design system for the current project.

---

# 1. Core Creative Principle

The single most important rule is:

> Animation is not decoration. Movement is content.

A conventional website usually behaves like:

```text
CONTENT = text + images
ANIMATION = decoration
```

An immersive website should behave like:

```text
CONTENT = text + typography + 3D + movement + sound + interaction
```

Every major animated element should have a reason to exist.

Before implementing an effect, ask:

1. What does the user feel?
2. What information does the motion communicate?
3. What input controls it?
4. Does the effect belong to the site's visual language?
5. Can it be rendered smoothly on the target devices?

Avoid adding effects simply because they are technically impressive.

---

# 2. Experience Model

Build the site as a continuous experience rather than a collection of independent sections.

Think of the page as a timeline:

```text
INTRO
  ↓
HERO
  ↓
3D INTERACTION
  ↓
TYPOGRAPHIC TRANSITION
  ↓
GENERATIVE / PARTICLE SCENE
  ↓
SERVICES / CONTENT SYSTEM
  ↓
STATEMENT / STORY
  ↓
CONTACT
  ↓
FOOTER WORLD
```

Sections may exist in the DOM as independent components, but visually they should feel connected.

The user should frequently feel:

> “I am moving through one world.”

rather than:

> “I am scrolling through unrelated sections.”

---

# 3. Visual Identity System

Use a very small color palette.

A strong default is:

```text
BLACK   #000000
WHITE   #FFFFFF
ORANGE  #FE4100  (or a project-specific signature color)
```

The exact signature color may be changed for the project. What matters is restraint and consistency.

Do not introduce many secondary colors unless the concept specifically requires them.

Treat the signature color as a state and storytelling mechanism, not simply an accent.

Examples:

```text
BLACK  = depth / silence / technology / closing state
WHITE  = space / clarity / editorial pause
ACCENT = energy / interaction / transformation / emphasis
```

Color transitions should sometimes be animated, not switched instantly.

Example:

```text
accentScene
    ↓
accent → white
    ↓
whiteScene
```

Use color changes to signal the user that the experience has entered a new visual state.

---

# 4. Typography

Typography is one of the main visual engines.

Do not treat headlines as ordinary document text.

Use typography as a spatial object.

Desired characteristics:

- oversized headlines,
- high visual contrast,
- compact spacing where appropriate,
- strong line-height control,
- viewport-scale composition,
- intentional cropping,
- large negative space,
- animated position and scale,
- words or lines that can move independently when appropriate.

A headline may intentionally extend outside the viewport.

Example:

```text
        CREATING
NEW PHYSICAL AND
     VIRTUAL WORLDS
```

The exact words are project-specific. The compositional behavior is the important part.

### Typography animation rules

Prefer subtle but continuous transformations such as:

- translateX,
- translateY,
- translateZ,
- scale,
- skew,
- opacity,
- letter-spacing,
- line-spacing,
- clipping / reveal,
- masking,
- variable-font axis changes when supported.

Avoid unnecessary letter-by-letter animations on every heading. Reserve extreme text choreography for major moments.

Use typography to create rhythm:

```text
large / quiet
→
large / moving
→
small / informational
→
large / dramatic
```

---

# 5. Cursor as an Input Device

Desktop pointer interaction should be treated as part of the experience.

Do not assume the cursor exists only as a browser arrow.

Possible cursor-driven behaviors:

- subtle global parallax,
- 3D camera offset,
- object rotation,
- object displacement,
- deformation pressure,
- magnetic UI interactions,
- particle attraction / repulsion,
- drawing or scratching trails,
- hover sound triggers,
- soft spotlight / lighting response.

A useful normalized input model is:

```js
const pointer = {
  x: 0,      // normalized -1..1
  y: 0,
  targetX: 0,
  targetY: 0
};
```

Smooth it rather than binding the scene directly to raw pointer values.

Use interpolation such as:

```js
current += (target - current) * damping;
```

or a spring / critically damped system.

The pointer should feel physical rather than robotic.

---

# 6. Cursor Trail / Scratch Interaction

A sophisticated immersive page may allow the pointer to leave a visual trace.

Possible implementations:

- GPU particle trail,
- canvas trail,
- ribbon geometry,
- line segments,
- procedural spline,
- signed-distance-field style brush,
- WebGL texture feedback.

Conceptual pipeline:

```text
pointer movement
      ↓
input sampling
      ↓
velocity estimation
      ↓
trail generation
      ↓
GPU / canvas rendering
      ↓
fade / decay
```

The trail should have:

- smooth interpolation,
- inertia,
- gradual decay,
- optional pressure based on pointer velocity,
- good performance.

If the effect is a “scratch” interaction, make it feel like the user is physically affecting the surface of the experience.

---

# 7. 3D System

3D should never be an isolated hero decoration.

It should participate in the interaction model.

Use a realtime WebGL renderer, typically through Three.js or another suitable WebGL/WebGPU framework.

A typical scene should contain:

```text
Scene
├── Camera
├── Lights / environment
├── Hero objects
├── Interaction objects
├── Particles / trails
├── Transition objects
└── Performance / render controller
```

Keep the scene modular.

Create reusable systems for:

- loading,
- materials,
- animation,
- physics,
- pointer interaction,
- scene transitions,
- disposal.

---

# 8. 3D Object Language

Objects should have strong material identities.

Possible material families:

### Glass

Use:

- transmission where available,
- roughness control,
- environment reflections,
- refraction where justified,
- thickness / attenuation where supported.

### Glossy black

Use:

- low-to-medium roughness,
- controlled specular highlights,
- dramatic lighting,
- deep shadows.

### Metallic

Use:

- physically based metalness,
- environment lighting,
- controlled reflections.

### Faceted / crystalline

Use:

- deliberate topology,
- visible normal changes,
- strong highlight response,
- optional vertex displacement.

The visual goal is tactile materiality.

Users should be able to mentally classify an object as:

```text
heavy / soft / glass / metallic / fluid / crystalline
```

without needing a label.

---

# 9. 3D Deformation

Use deformation to make the scene feel alive.

Possible strategies:

- vertex shader displacement,
- morph targets,
- skeletal animation,
- procedural noise,
- spring-based transforms,
- physics-driven position / rotation,
- blend shapes.

Do not deform everything at once.

A strong interaction can be as simple as:

```text
cursor approaches
    ↓
object rotates
    ↓
object slightly compresses
    ↓
material highlight shifts
    ↓
sound plays
```

The combination of small responses can feel much more sophisticated than one large animation.

---

# 10. Fragmentation / Break Apart Effects

For major interaction moments, an object may split into smaller components.

Example progression:

```text
single object
    ↓
impact / cursor interaction
    ↓
object fractures
    ↓
fragments inherit velocity
    ↓
fragments spread
    ↓
fragments slow down
    ↓
fragments reform or disappear
```

This can be implemented using:

- instanced geometry,
- batched geometry,
- pre-fractured assets,
- GPU simulation,
- physics bodies,
- shader-based dissolve.

Do not simulate unnecessary high-resolution fragments on mobile.

---

# 11. Physics

When physical behavior adds meaningful realism, use a physics engine such as Rapier or an equivalent solution.

Physics is appropriate for:

- rigid-body motion,
- collisions,
- bouncing,
- falling fragments,
- interactive clusters,
- object piles,
- reactive footer scenes.

Physics is NOT required for every animation.

Use authored animation for deterministic cinematic sequences and physics for moments that genuinely benefit from physical unpredictability.

A useful hybrid model is:

```text
scroll controls macro state
          ↓
physics controls local motion
          ↓
cursor applies force
          ↓
visual system applies damping
```

This produces cinematic control without making the scene feel fake.

---

# 12. Scroll as a Timeline Controller

Scroll should control the experience, not merely reveal content.

Treat scroll progress as normalized state:

```js
progress = clamp(scrollPosition / scrollRange, 0, 1);
```

Then map ranges of progress to visual states.

For example:

```text
0.00–0.15   intro
0.15–0.35   hero object
0.35–0.50   typography transformation
0.50–0.65   generative scene
0.65–0.82   services
0.82–1.00   closing / footer
```

These ranges are examples only.

### Scroll should control

- camera position,
- camera rotation,
- object transforms,
- object visibility,
- material properties,
- text position,
- text opacity,
- clipping,
- background color,
- particle density,
- scene transitions,
- audio intensity where appropriate.

Do not tie every animation directly to raw scroll values. Use easing and state interpolation.

---

# 13. Smooth Scroll

If the project uses a smooth-scroll library, treat it as an input layer rather than an excuse to make every movement float endlessly.

The page should still feel responsive.

Avoid excessive inertial delay between user input and visible response.

The best motion often uses a combination of:

- smooth scroll,
- short easing,
- spring-like object behavior,
- direct pointer response.

---

# 14. Camera Choreography

The camera is often more important than moving the 3D model itself.

Use camera movement to create:

- approach,
- retreat,
- orbit,
- lateral drift,
- vertical reveal,
- perspective changes,
- macro-to-micro transitions.

Example:

```text
camera starts distant
      ↓
scroll forward
      ↓
camera approaches object
      ↓
object passes near camera
      ↓
camera exits into next visual state
```

Avoid constant camera motion.

Silence is necessary so dramatic moments have contrast.

---

# 15. Generative Line / Particle Scenes

A strong transition scene can use procedural lines, particles, rings, or flowing structures.

Potential sources:

- particle systems,
- parametric curves,
- Catmull-Rom splines,
- Fibonacci / polar distributions,
- noise fields,
- curl noise,
- spring systems,
- GPU simulation.

A useful visual language is:

```text
white background
+
thin accent-colored lines
+
slow orbital motion
+
subtle pointer influence
```

The result should feel like a digital organism, field, or abstract physical system rather than random decoration.

---

# 16. Layered Motion

Premium motion usually has multiple timescales.

Example:

```text
fast  = cursor response
medium = object motion
slow = camera / background drift
very slow = scene color transition
```

If everything moves at the same speed, the scene looks cheap.

Use temporal hierarchy.

---

# 17. UI Philosophy

Keep traditional UI minimal.

Typical controls may include:

```text
Navigation
Sound On / Off
Prev
Next
Service index
Contact CTA
Email input
```

Do not add large rounded cards, excessive shadows, generic dashboard components, or conventional design-system UI unless the project's purpose requires them.

The UI should support the experience rather than compete with it.

---

# 18. Navigation

Navigation can itself become an animated object.

A useful pattern is:

```text
compact navigation
      ↓
expands / transforms
      ↓
becomes a larger navigation state
      ↓
merges into footer / closing state
```

This is especially effective when the site is a single continuous experience.

Do not make navigation difficult to understand simply to be experimental.

The interaction can be unusual while the labels remain clear.

---

# 19. Services / Content Navigation

For a services area, prefer an editorial navigation system over a generic card grid.

Example:

```text
00   01   02   03

IDEATE
DEFINE OBJECTIVES
SHARE IDEAS
EXPLORE POSSIBILITIES
```

Each numbered item may update:

- title,
- supporting text,
- 3D scene,
- visual composition,
- background,
- sound.

The user should feel as if the content is changing the world, not merely replacing a card.

---

# 20. Prev / Next Controls

Use small, editorial controls where appropriate.

Good examples:

```text
Prev   Next
```

or:

```text
← Prev       Next →
```

The visual treatment should remain minimal.

The animation and context provide the sense of sophistication.

---

# 21. Sound Design

Sound is part of the interaction system.

Provide an explicit sound control such as:

```text
SOUND ON
SOUND OFF
```

Never autoplay intrusive audio without a clear user-controlled state.

Use layered audio:

### Ambient layer

Low-level background texture.

### Interaction layer

Small sounds tied to:

- hover,
- pointer contact,
- object motion,
- collisions,
- buttons,
- UI transitions.

### Transition layer

Distinct sonic moments for major section changes.

### Impact layer

Optional deeper sounds for major 3D events.

A useful conceptual rule is:

```text
not everything has sound
but important interactions should feel audible
```

Avoid a constant wall of sound.

A practical target is to let sound reinforce emotion and materiality without becoming tiring.

---

# 22. Sound and Visual Synchronization

Audio should be synchronized to state changes rather than arbitrary timers.

Example:

```js
onObjectImpact(() => {
  playSfx('impact');
});
```

not:

```js
setTimeout(() => playSfx('impact'), 1480);
```

Prefer event-driven synchronization.

Use audio sparingly, with volume envelopes and cooldowns to prevent repeated interactions from sounding broken.

---

# 23. Intro / Loading Experience

The intro should be minimal.

A typical pattern:

```text
black screen
    ↓
logo / wordmark
    ↓
short reveal
    ↓
world initializes
    ↓
experience starts
```

The intro should never become an unnecessary loading barrier.

If assets take time to initialize:

- preload essential assets,
- stream non-essential assets,
- show a clean loading state,
- keep the first interaction available as early as practical.

---

# 24. Hero Composition

A good immersive hero commonly contains:

```text
large typography
+
3D object
+
strong background state
+
subtle pointer response
+
clear narrative phrase
```

The object should have enough empty space around it to be readable.

The typography and object should sometimes overlap intentionally.

Do not simply place a 3D object in the center and put text above it like a conventional hero banner.

Compose the entire viewport as one poster / stage.

---

# 25. Transition Design

Transitions should be composed, not generic.

Avoid:

```text
fade out
fade in
```

for every section.

Prefer transformations such as:

```text
object leaves frame
→
text expands
→
background changes
→
new scene enters
```

or:

```text
headline moves sideways
→
world zooms through negative space
→
new color field appears
```

Each major transition should have an identity.

---

# 26. Continuous World Illusion

Use shared elements between sections.

Examples:

- the same camera system,
- the same accent color,
- a particle field continuing from one scene into another,
- a 3D object transformed rather than replaced,
- typography that travels between sections,
- sound that crossfades between states.

This is one of the strongest techniques for making the experience feel cohesive.

---

# 27. Footer as a Final Scene

Do not automatically treat the footer as a static legal-information area.

For an immersive site, the footer can be the final visual chapter.

Possible composition:

```text
black background
+
large wordmark / statement
+
3D objects
+
contact information
+
minimal navigation
```

The footer should feel like the end of the journey.

It may reuse the same physics and 3D infrastructure as the hero.

---

# 28. Performance Architecture

Performance is part of the creative direction.

A visually impressive page that runs at poor frame rates is not a successful immersive experience.

Design the rendering architecture early.

### Primary principles

- minimize draw calls,
- reuse geometry,
- reuse materials where possible,
- use instancing / batching for repeated objects,
- limit shader complexity,
- avoid unnecessary transparency,
- dispose unused GPU resources,
- load assets progressively,
- avoid blocking the main thread.

When many objects share geometry/material characteristics, consider batching or instancing.

A reference implementation in the immersive-web space has publicly documented use of Three.js/WebGL, Rapier physics, BatchedMesh, OffscreenCanvas, and WebWorkers to support demanding real-time scenes. Use similar architectural ideas when they are appropriate for the project; do not force every technique into every site.

---

# 29. Batched / Instanced Rendering

When there are many repeated meshes, prefer:

```text
1 mesh definition
+
many transforms
```

instead of:

```text
many independent mesh objects
```

Use:

- InstancedMesh,
- BatchedMesh where suitable,
- custom GPU buffers,
- merged geometry when appropriate.

Monitor:

- draw calls,
- GPU memory,
- CPU frame time,
- GPU frame time.

Do not optimize blindly. Measure first.

---

# 30. OffscreenCanvas and Web Workers

For sufficiently demanding rendering or simulation, consider moving suitable work away from the main UI thread.

Conceptually:

```text
MAIN THREAD
├── DOM
├── input
├── accessibility
└── application state

WEB WORKER
├── expensive calculations
├── rendering where architecture supports it
└── simulation / processing
```

Use this only when justified by real performance constraints and browser support.

Do not create a worker architecture simply for architectural prestige.

---

# 31. Asset Strategy

3D assets should be optimized before shipping.

Preferred formats typically include:

- GLB / glTF for 3D,
- compressed textures where appropriate,
- modern image formats for raster content.

Consider:

- mesh simplification,
- texture resolution,
- normal-map usage,
- baked lighting where acceptable,
- compression,
- lazy loading.

Keep a clear asset naming scheme:

```text
/models/
/textures/
/audio/
/shaders/
/fonts/
```

Do not load every asset on initial page load unless necessary.

---

# 32. Rendering Quality Modes

Implement quality adaptation where appropriate.

Example:

```text
HIGH
- full 3D detail
- high particle count
- full physics

MEDIUM
- reduced particles
- reduced physics bodies
- lower post-processing

LOW / MOBILE
- simplified geometry
- fewer particles
- reduced physics
- fewer real-time reflections
- selective 3D
```

The experience should preserve its identity even when technical complexity is reduced.

---

# 33. Responsive Art Direction

Do not simply shrink the desktop composition.

Desktop and mobile may need different choreography.

On mobile:

- reduce simultaneous 3D objects,
- change camera framing,
- simplify cursor-driven effects because touch has no cursor,
- replace hover interactions with touch / drag where meaningful,
- reduce physics complexity,
- simplify text overlap,
- shorten transitions when necessary.

Mobile should still feel like the same brand and world.

It should not feel like a fallback page.

---

# 34. Touch Interaction

For touch devices, translate pointer interactions into touch semantics.

Possible mappings:

```text
hover       → touch highlight
pointer drag → object manipulation
scroll      → timeline progression
long press  → optional deeper interaction
```

Avoid interactions that require hover-only behavior to understand the page.

---

# 35. Accessibility

Immersive does not mean inaccessible.

Always provide:

- semantic headings,
- keyboard navigation,
- visible focus states,
- accessible buttons,
- meaningful labels,
- text alternatives where needed,
- readable contrast,
- reduced-motion support.

Respect:

```css
@media (prefers-reduced-motion: reduce) {
  /* reduce or simplify non-essential motion */
}
```

Reduced-motion mode should not destroy the information architecture.

A user should still be able to understand and navigate the website.

For audio:

- never require sound to understand essential information,
- provide an obvious mute control,
- remember sound preference locally when appropriate.

---

# 36. Semantic / Non-WebGL Fallback

Critical text and navigation must remain in normal HTML whenever practical.

Do not make the entire website inaccessible behind a canvas.

The WebGL scene should enrich the experience, not replace the semantic document structure.

Recommended separation:

```text
HTML
= content + semantics + controls

WebGL
= visual experience
```

---

# 37. Technology Selection

Choose the technology according to the existing project.

A suitable modern architecture may include:

```text
Frontend framework
→ React / Next.js / Vue / Nuxt / Vite

Animation
→ GSAP or native requestAnimationFrame systems

3D
→ Three.js

Physics
→ Rapier or equivalent

Smooth scroll
→ optional dedicated library or custom interpolation

Audio
→ Web Audio API / Howler / equivalent
```

Do not add a dependency when native browser APIs are sufficient.

Do not use a library simply because it is fashionable.

---

# 38. Animation Architecture

Never scatter animation logic randomly across components.

Create a state-driven animation architecture.

Example:

```text
ExperienceState
├── section
├── scrollProgress
├── pointer
├── soundEnabled
├── qualityLevel
└── reducedMotion
```

Then derive visual state from it.

Example:

```js
sceneController.update({
  section,
  progress,
  pointer,
  quality,
});
```

This is easier to maintain than many unrelated event listeners.

---

# 39. Scene Controller

Use a scene controller or equivalent abstraction.

Example responsibilities:

```text
SceneController
├── setSection()
├── updateScroll()
├── updatePointer()
├── transitionTo()
├── setQuality()
├── pause()
├── resume()
└── dispose()
```

Scenes may expose:

```text
enter()
update()
exit()
dispose()
```

This makes complex multi-section experiences manageable.

---

# 40. Input Arbitration

Pointer, scroll, touch, physics, and scripted animation can all compete for control.

Define priorities.

Example:

```text
scripted cinematic state
    highest priority for macro motion

physics
    controls local movement

pointer
    applies forces / offsets

idle drift
    lowest priority
```

This prevents systems from fighting each other.

---

# 41. Motion Quality Rules

Use motion hierarchy.

### Primary motion
Large visual transition.

### Secondary motion
Object response.

### Tertiary motion
Particles, small UI movement, noise, micro-feedback.

Not every object needs to animate independently.

A good composition has intentional stillness.

---

# 42. Microinteractions

Small moments are critical to premium perception.

Examples:

- button hover shifts by a few pixels,
- underline stretches,
- small sound plays,
- menu text slides,
- pointer changes shape,
- 3D highlight reacts,
- background subtly shifts.

These should be:

- fast,
- smooth,
- consistent,
- restrained.

Avoid excessive bounce and generic UI animation presets.

---

# 43. Loading and Error Resilience

The site should still function if:

- WebGL is unavailable,
- an asset fails,
- audio is blocked,
- a browser has limited GPU capability,
- a model takes too long to load.

Provide sensible fallbacks.

For example:

```text
3D unavailable
→ semantic content remains
→ static / CSS visual fallback
```

Audio unavailable:

```text
audio disabled
→ interface still fully usable
```

---

# 44. Browser and Device Testing

Test at minimum on:

- current Chromium desktop,
- current Safari desktop,
- current Firefox desktop,
- current iOS Safari,
- current Android Chrome.

Pay particular attention to:

- WebGL context limits,
- Safari rendering differences,
- mobile memory pressure,
- touch behavior,
- audio policy,
- resizing / orientation,
- high-DPI displays.

---

# 45. Performance Budgets

Set explicit budgets before polishing.

Track at least:

```text
FPS / frame time
JS main-thread time
GPU memory
texture memory
number of draw calls
number of physics bodies
network transfer size
initial load time
```

Do not chase arbitrary FPS claims. Measure the actual target experience on representative hardware.

A smooth 60 FPS experience is a good target for capable desktop hardware, while mobile should use an intentional lower-complexity mode rather than simply struggling to maintain desktop complexity.

---

# 46. Debug Overlay

During development, implement a hidden debug mode showing:

```text
FPS
Frame Time
Draw Calls
Triangles
Objects
Physics Bodies
Current Section
Scroll Progress
Quality Mode
WebGL Renderer
```

Expose it only in development.

---

# 47. Content Strategy

Keep copy concise.

Immersive pages cannot carry the same text density as conventional corporate sites without losing visual impact.

Use:

- strong statements,
- short supporting paragraphs,
- clear labels,
- meaningful calls to action.

Large typography should carry the narrative.

Do not fill empty space simply because it exists.

---

# 48. Visual Rhythm

Structure the page with contrast.

Example:

```text
high motion
→
stillness
→
large type
→
3D interaction
→
white space
→
sound event
→
minimal UI
```

Constant intensity becomes visually exhausting.

The goal is controlled tension and release.

---

# 49. Design Tokens

Create centralized tokens for:

```text
colors
font sizes
spacing
transition durations
easing curves
border widths
z-index layers
quality levels
```

Example:

```js
const motion = {
  fast: 0.18,
  medium: 0.45,
  slow: 0.9,
};
```

The exact values are project-specific.

---

# 50. Easing Philosophy

Avoid using one easing curve everywhere.

Use different timing personalities:

```text
UI = fast / precise
3D = smooth / physical
camera = slow / cinematic
text = decisive / editorial
physics = natural / spring-like
```

This helps the experience feel layered.

---

# 51. What NOT to Build

Do not automatically turn the project into:

- a generic glassmorphism dashboard,
- a template-style agency site,
- a card grid with random hover effects,
- a page overloaded with gradients,
- a 3D model floating on top of normal HTML with no interaction,
- a collection of unrelated WebGL demos,
- a video background replacing actual interaction,
- constant parallax everywhere,
- giant animated text with no narrative purpose.

Avoid “effect soup.”

Every visual system must belong to the same world.

---

# 52. Implementation Order

Build in this order unless the project requires another sequence.

## Phase 1 — Information architecture

Define:

- sections,
- narrative,
- content,
- navigation,
- primary CTA.

## Phase 2 — Visual direction

Define:

- color system,
- typography,
- spacing,
- image / 3D language.

## Phase 3 — Static composition

Build the page without complex animation.

Confirm:

- hierarchy,
- responsiveness,
- copy placement,
- section order.

## Phase 4 — Motion system

Add:

- scroll choreography,
- typography animation,
- transitions.

## Phase 5 — 3D

Add:

- camera,
- models,
- materials,
- lighting.

## Phase 6 — Interaction

Add:

- pointer,
- touch,
- physics,
- deformation,
- particle response.

## Phase 7 — Audio

Add:

- sound state,
- interaction SFX,
- ambient layers,
- transitions.

## Phase 8 — Performance

Profile and simplify.

## Phase 9 — Accessibility

Implement keyboard, semantic structure, reduced motion, and fallbacks.

## Phase 10 — Polish

Tune spacing, timing, sound levels, lighting, and transitions.

---

# 53. Claude / AI Implementation Behavior

When using this skill to generate or modify code, Claude should behave like a senior creative technologist, not like a generic frontend code generator.

Before writing large amounts of code:

1. Inspect the existing repository.
2. Identify the framework and package manager.
3. Identify current routing and entry points.
4. Reuse existing dependencies when possible.
5. Check whether Three.js or another renderer is already installed.
6. Determine whether the project needs true WebGL, CSS-only motion, or both.
7. Preserve existing functionality unless explicitly asked to replace it.
8. Create a maintainable architecture before adding large animation code.

When asked to create an immersive experience from a visual reference:

- extract the visual principles,
- identify the interaction primitives,
- reproduce the feeling through original implementation,
- do not blindly reproduce copyrighted artwork or proprietary assets.

---

# 54. Code Quality Rules

Prefer:

- modular components,
- typed data where applicable,
- reusable animation controllers,
- reusable scene utilities,
- centralized constants,
- explicit cleanup,
- deterministic state transitions.

Avoid:

- one enormous component,
- duplicated event listeners,
- endless anonymous timers,
- animation logic hidden inside unrelated UI components,
- leaked WebGL resources,
- physics bodies that are never removed,
- audio nodes that accumulate forever.

Every major system must have a cleanup path.

---

# 55. Resource Disposal

When removing scenes or assets, clean up:

```text
geometry.dispose()
material.dispose()
texture.dispose()
renderer resources
physics bodies
listeners
animation handles
audio nodes
```

Use framework-specific cleanup mechanisms as appropriate.

Memory leaks are especially damaging on long immersive pages because users may keep the page open for a long time.

---

# 56. SEO

Immersive does not eliminate the need for SEO.

Ensure:

- proper title,
- meta description,
- semantic headings,
- crawlable text,
- canonical handling where needed,
- Open Graph metadata,
- structured data where relevant.

Do not hide critical text exclusively inside a canvas.

---

# 57. Analytics

Track meaningful interactions rather than every mouse movement.

Useful events may include:

```text
experience_loaded
sound_enabled
sound_disabled
service_changed
cta_clicked
contact_started
contact_completed
major_scene_reached
```

Do not continuously log high-frequency pointer data unless there is a specific research reason.

---

# 58. Acceptance Criteria

A successful implementation should satisfy most of the following:

### Visual

- Strong signature color system.
- Large editorial typography.
- Large negative space.
- Cohesive art direction.
- 3D scenes that feel intentional.

### Interaction

- Pointer affects the world in meaningful ways.
- Scroll controls progression.
- Transitions feel connected.
- Interactions have visual feedback.

### 3D

- Materials feel physical.
- Camera motion supports narrative.
- Physics is used selectively.
- Objects can respond or transform where justified.

### Audio

- Sound can be enabled / disabled.
- Major interactions can have audio feedback.
- Essential content never depends on sound.

### UI

- Navigation is minimal.
- Controls are understandable.
- Microinteractions are consistent.

### Performance

- No avoidable frame-rate spikes.
- No obvious memory leaks.
- Heavy scenes have quality fallbacks.
- Assets are loaded progressively where appropriate.

### Accessibility

- Keyboard navigation works.
- Reduced-motion users receive a simplified experience.
- Semantic content remains available.

### Responsive

- Mobile is art-directed rather than merely scaled down.
- Touch interaction is intentional.
- Complex effects degrade gracefully.

---

# 59. Final Quality Test

Before declaring the experience complete, review it as if it were being presented as a premium digital installation.

Ask:

1. Does the first 5–10 seconds immediately establish a visual world?
2. Does the page feel alive before the user understands every control?
3. Does scrolling feel like progressing through a story?
4. Does the cursor actually matter?
5. Do the 3D objects feel tactile?
6. Are sound and motion synchronized?
7. Does typography behave like part of the environment?
8. Are transitions more interesting than simple fades?
9. Is there enough stillness to make the dramatic moments powerful?
10. Does the footer feel like a final scene rather than a legal dump?
11. Does the site remain understandable without sound?
12. Does it remain usable with reduced motion?
13. Does the mobile version retain the creative identity?
14. Is the performance good enough on the real target devices?
15. Is every major effect justified?

If the answer to several questions is “no,” continue refining the system rather than adding more effects.

---

# 60. Reference Mental Model

The complete experience can be understood as seven connected systems:

```text
                 IMMERSIVE EXPERIENCE
                          │
       ┌──────────────────┼──────────────────┐
       │                  │                  │
    VISUAL              INPUT              AUDIO
       │                  │                  │
  ┌────┼────┐       ┌─────┼─────┐       ┌───┼───┐
  │    │    │       │     │     │       │   │   │
 TYPE  3D  COLOR   MOUSE SCROLL TOUCH  SFX MUSIC
  │    │    │       │     │
  └────┼────┘       └─────┼─────┘
       │                  │
       └──────────┬───────┘
                  ↓
             EXPERIENCE STATE
                  ↓
       ┌──────────┼──────────┐
       │          │          │
   CAMERA     PHYSICS    TRANSITIONS
       │          │          │
       └──────────┼──────────┘
                  ↓
             REAL-TIME WORLD
```

This mental model should guide implementation decisions.

---

# 61. Most Important Rule of All

Do not try to impress the user with the number of effects.

Impress the user with the quality of the relationships between effects.

A cursor movement that changes a 3D material, which triggers a physical response, which shifts typography, which changes the camera, and which produces a subtle sound is more powerful than ten unrelated animations.

The desired result is:

```text
minimal UI
+
strong typography
+
strong color system
+
real-time 3D
+
physical interaction
+
scroll choreography
+
subtle audio
+
performance engineering
+
excellent timing
=
immersive digital experience
```

Build the experience as one system.
take an example of this site: https://kodeimmersive.com 
