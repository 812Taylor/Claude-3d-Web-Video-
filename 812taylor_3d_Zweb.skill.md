# Skill: Lusion-Inspired Immersive Creative Studio Web Experience

## Purpose

Use this skill when building a premium creative-studio, portfolio, agency, product, fashion, automotive, technology, or experimental website that should feel like an interactive digital experience rather than a conventional document.

The target quality bar is the current Lusion homepage experience: restrained UI, oversized typography, editorial layout, cinematic media, realtime or pseudo-realtime 3D, strong visual transitions, interactive cursor behavior, motion-led storytelling, and carefully controlled color changes.

This skill is an implementation and art-direction specification. It explains the design language and interaction principles to reproduce, but it must NOT copy Lusion's logo, proprietary assets, project imagery, source code, or exact branding. Create an original visual identity using the same class of techniques.

---

## 1. Core Creative Principle

The website must be designed as an **immersive sequence**, not as a stack of independent sections.

Treat these systems as one connected experience:

- typography
- layout
- scroll position
- pointer movement
- 3D or cinematic media
- color fields
- image/video transitions
- hover states
- navigation
- audio feedback
- page transitions
- responsive behavior

The key principle is:

> Motion is content, not decoration.

A normal corporate site can be described as:

`content + decorative animation`

This experience should instead behave like:

`content + motion + spatial media + interaction + atmosphere`

Every major animation must have a reason: introducing a brand idea, changing a scene, revealing work, directing attention, providing feedback, or creating a memorable moment.

---

# 2. Reference Analysis: Current Lusion Homepage

The currently observed Lusion homepage combines a clean white editorial framework with dark and highly cinematic media moments. Its information architecture is simple, while the visual presentation is intentionally ambitious.

The live page currently communicates:

- a short studio positioning statement
- a clear "Let's Talk" action
- a compact "Menu" control
- a large hero visual
- a featured work section
- a large red reel / video moment
- a project gallery
- an oversized positioning statement
- a dark cinematic immersive section featuring a human/astronaut-like 3D subject
- a final CTA
- address/social/contact details
- newsletter signup

The public page currently describes the studio as creating "3D visual storytelling and interactive web experiences" and explicitly combines design, motion, 3D, and development. The page also exposes a Labs/R&D destination and a project portfolio with WebGL/3D-oriented work. See the live structure at https://lusion.co/.

The project archive confirms that Lusion's portfolio spans Web Design, Web Development, 3D Design, WebGL, animation, AR, WebXR, API design, illustration, motion graphics, and related interactive work. This skill therefore treats the site as a hybrid of editorial portfolio, motion-design reel, and realtime interactive experience rather than a conventional agency template.

---

# 3. Overall Visual DNA

The visual language should feel:

- contemporary
- experimental
- editorial
- premium
- technically advanced
- spacious
- slightly playful
- cinematic
- tactile
- confident
- intentionally unconventional

Avoid generic "creative agency" clichés such as:

- excessive gradients everywhere
- glassmorphism as the primary identity
- dozens of floating pills
- huge neon glow around every object
- generic 3D blobs
- stock corporate imagery
- overuse of rounded cards
- excessive shadow-heavy UI
- too many colors in the interface itself

The spectacle should come from the media and motion, not from adding UI chrome.

---

# 4. Color System

The reference experience is primarily based on a **neutral editorial shell** with full-screen or large-area color scenes.

### Base UI

Use a mostly white page background for editorial content.

- Primary background: pure or near-white
- Primary text: near-black / black
- Secondary UI: soft gray / lavender-gray
- Button text: white or black depending on button surface

### Accent behavior

Do not force one accent color across every section. Instead, allow major scenes to own their own palette.

Reference-style scenes include:

- bright red / vermilion reel section
- deep black cinematic scenes
- cyan / aqua line graphics
- intense blue 3D material scenes
- red / magenta / blue cinematic environments
- white monochrome 3D subjects

The important principle is **palette segmentation**:

`white editorial -> saturated media -> white editorial -> black cinematic -> white/neutral ending`

A scene can temporarily become visually dominant, while the surrounding UI remains restrained.

Do not animate every color independently. Color transitions should be tied to scene changes, scroll milestones, media playback, or deliberate interaction states.

---

# 5. Grid and Layout System

Use a strong editorial grid.

Recommended baseline:

- 12-column desktop grid
- generous outer margins
- consistent horizontal gutters
- large vertical rhythm
- asymmetrical image and text placements
- occasional full-bleed media
- text blocks that deliberately occupy only a portion of the viewport

The current reference repeatedly uses a strong left edge for branding and navigation while large headlines and visual media occupy broad areas of the page.

The interface should feel precisely aligned even when the motion makes it look chaotic.

Use layout constraints behind the scenes, then allow animation to temporarily violate visual expectations.

---

# 6. Header / Top Navigation

The header should remain extremely simple.

### Typical structure

Left:

`BRAND`

Right:

`LET'S TALK` + `MENU`

The current Lusion page presents the brand name as a simple wordmark and uses compact pill-like actions for contact and menu. There is also a visible Labs destination in the wider information architecture.

### Button style

The reference uses compact rounded/pill controls rather than large rectangular navigation bars.

Recommended behavior:

- high contrast
- subtle hover expansion or color inversion
- slightly animated text or dot indicator
- smooth pointer transition
- no excessive shadow
- fixed/sticky positioning when useful

### Menu button

Use an understated control such as:

`MENU  ••`

or another original compact symbol.

On hover:

- slightly expand the pill
- shift icon position
- change contrast
- play a quiet micro sound when audio is enabled

On click:

- transition into a full-screen navigation layer
- animate menu items in sequence
- preserve the brand's visual calm
- allow the page underneath to remain visible or become a controlled color field

The menu should feel like an extension of the motion system, not a conventional hamburger drawer.

---

# 7. Hero Section

The hero should establish the entire creative identity within a few seconds.

A strong pattern is:

1. small brand label
2. large positioning statement
3. large cinematic or realtime 3D media frame
4. small scroll instruction

Example structure:

`We create [large concise positioning statement]`

followed by a very large visual stage.

### Hero media

The reference starts with a large, rounded-corner dark media area containing clusters of glossy 3D forms in white, cobalt/royal blue, and black. The objects overlap, intersect, and create depth.

Important qualities:

- reflective materials
- soft studio lighting
- hard specular highlights
- dark world/background
- dense composition
- shallow-to-medium depth of field feeling
- multiple objects with different rotations
- controlled motion rather than random motion

Do not use a static hero image unless performance constraints require it. Prefer:

- WebGL/Three.js scene
- video texture
- rendered sequence
- procedural composition
- hybrid video + 3D

### Hero framing

Use a large but clearly bounded media container inside the editorial page. The rounded rectangle should feel like an artwork window rather than a generic card.

---

# 8. Hero 3D Direction

The reference style benefits from simple geometry with sophisticated rendering.

Use forms such as:

- tubes
- capsules
- cylinders
- rounded boxes
- mechanical connectors
- toy-like industrial primitives
- abstract modular forms

Combine several material families:

- glossy white
- glossy black
- saturated blue
- occasional transparent/glassy material

### Lighting

Use several soft sources rather than flat ambient lighting:

- broad key light
- soft fill
- rim light
- reflection environment
- subtle contact shadow / AO

The object cluster should read as physical material, not as flat vector art.

### Animation

Use layered motion:

- slow global rotation
- tiny object drift
- independent local rotations
- subtle camera parallax
- slight depth offsets
- restrained deformation where appropriate

Avoid every object moving at the same speed.

---

# 9. Scroll Experience

Scrolling should control a visual timeline.

Do not simply reveal static sections.

Recommended architecture:

```text
scroll progress
      |
      +--> typography transforms
      +--> camera motion
      +--> object motion
      +--> media playback / frame position
      +--> color transition
      +--> background transition
      +--> opacity / blur
      +--> section choreography
```

### Scroll characteristics

Use:

- smooth interpolation
- inertial/lerped progress
- section-based timelines
- scrubbed media
- pinning for major cinematic scenes
- carefully staged entrances/exits

Avoid constant snapping.

The experience should feel physically continuous.

### Useful techniques

Recommended implementation options:

- GSAP ScrollTrigger
- Lenis or another smooth-scroll layer
- requestAnimationFrame state interpolation
- CSS scroll timelines where appropriate
- Three.js camera/scene updates driven by normalized progress

Keep all major scene transitions synchronized to a common progress model.

---

# 10. Typography as a Graphic Object

Typography is one of the main visual materials.

Use a modern grotesk / neo-grotesk / contemporary sans-serif with highly controlled weight and spacing.

The reference relies on very large black type against white space and very large white type against black scenes.

### Rules

- prefer one primary type family
- use few weights
- prioritize scale over typographic ornament
- avoid excessive italics
- keep line heights intentionally tight for display headlines
- allow oversized headings to extend beyond the viewport when compositionally justified

### Motion techniques

Animate text using:

- position
- clip-path
- opacity
- letter-spacing
- line splitting
- mask reveals
- controlled vertical translation
- subtle scale

Avoid cartoonish bounce easing.

The motion should feel editorial and expensive.

### Oversized headline section

Build a giant statement section where the headline can occupy most of the viewport.

Example:

`WHERE CREATIVE IDEAS BECOME IMMERSIVE EXPERIENCES`

Add a large freeform cyan/aqua line behind or around the typography to create a hand-drawn / gestural counterpoint to the clean type.

This line can be:

- SVG path
- canvas stroke
- WebGL ribbon
- procedural curve

Animate path progress or subtly morph the curve as the user scrolls.

---

# 11. Featured Work System

The work section should operate as a portfolio, not as a generic card grid.

Each project tile can contain:

- project name
- category metadata
- media artwork
- arrow / navigation cue
- optional hover state

Example metadata:

`concept • web • design • development • 3D • animation`

Keep metadata visually small.

The artwork should dominate.

### Project hover

On hover:

- slightly scale media
- shift crop
- add motion to the image/video
- reveal arrow or title movement
- optionally alter cursor treatment

Do not overdo hover transforms. The media should remain the hero.

### Card geometry

Rounded corners can be used sparingly for large media frames, especially near the top of the page. Not every tile needs the same card treatment.

Allow some project items to feel like independent editorial compositions.

---

# 12. Project Media Treatment

Use mixed media.

The current project collection demonstrates that the studio's work can contain:

- realtime 3D
- motion graphics
- photography/video
- WebGL scenes
- illustrated assets
- experimental interactions

Therefore the site should not impose one visual template on every project.

Instead, unify projects through:

- typography
- spacing
- labels
- interaction behavior
- transition language

Let each project retain its own visual world.

---

# 13. Reel / Video Section

Create at least one major full-width or large-area video/reel moment.

The reference uses an extremely saturated red field with project media cards and a prominent "PLAY REEL" action.

### Reel composition

Recommended structure:

- solid saturated background
- 2–4 media previews
- large centered play label
- circular play icon or equivalent symbol
- subtle index/metadata
- strong contrast

### Interaction

On hover:

- media previews shift slightly
- play icon responds to the cursor
- title can enlarge or track pointer

On click:

- open an immersive overlay or dedicated media mode
- hide unnecessary UI
- display a clear mute/close control
- use a cinematic transition rather than a browser-default video appearance

---

# 14. Editorial / About Section

After the portfolio spectacle, introduce a calmer editorial zone.

Use a giant headline such as:

`WHERE CREATIVE IDEAS BECOME IMMERSIVE EXPERIENCES`

Then divide the supporting copy from a media object.

Recommended layout:

- oversized headline on the left/top
- large media object below or beside it
- paragraph column on the opposite side
- accent line / graphic element weaving through the composition

The contrast is essential:

`large visual statement -> quiet explanation`

This lets the page breathe before the next cinematic sequence.

---

# 15. Accent Line / Procedural Stroke

The reference includes a thick cyan/aqua stroke traveling behind and around editorial content.

Treat it as a graphic system, not a random decoration.

Implementation options:

### SVG

Use a path with `stroke-dasharray` / `stroke-dashoffset` and animate progress.

### Canvas

Store a list of control points and interpolate them.

### WebGL

Use a line geometry with procedural noise and depth.

### Motion

The line can:

- draw itself into view
- travel across the page during scroll
- bend around content
- fade before transitions
- subtly wobble when the pointer moves

Keep the stroke thickness consistent and bold.

---

# 16. Cinematic Immersive Section

One of the strongest transitions is from the white editorial world into a nearly black full-screen environment.

The reference places large white uppercase typography over a dark cinematic scene with a white suited astronaut-like subject.

The subject becomes a spatial anchor behind the text.

### Goal

The section should feel like entering another world.

Transition using:

- background color interpolation
- typography color inversion
- camera movement
- fade/blur
- large-scale media reveal
- slight scale acceleration

Do not abruptly switch the page from white to black. Use a cinematic transition whenever possible.

---

# 17. Cinematic 3D Scene

Use one hero character/object and a deep environment.

Possible original subjects:

- astronaut-inspired character
- robot
- sculptural human figure
- vehicle
- object from your brand world

### Environment

Build a dark tunnel, room, void, or spatial corridor with:

- glossy black surfaces
- reflective structures
- emissive practical lights
- volumetric haze where performance allows
- subtle chromatic aberration
- depth-of-field feeling
- fine particles

The camera should move through or toward the environment as the user scrolls.

---

# 18. High-Energy Tunnel / Warp Sequence

The reference video analysis shows a dark tunnel populated by multicolored lights, streaks, blur, and a central organic/human form. It creates the sensation of moving rapidly through a spatial corridor.

Recreate the **effect class**, not the exact artwork.

Use:

- instanced light bars
- emissive rectangles
- motion blur or radial blur
- depth-based streaks
- camera dolly
- subtle chromatic separation
- bloom
- particles

The scene should accelerate and decelerate with scroll progress.

Use the center of the composition as the visual destination.

---

# 19. Red / Magenta Energy Tunnel

Another scene type in the reference uses red/pink and cool blue highlights around a dense geometric tunnel or rotating volumetric structure.

This can be implemented with:

- instanced tubes
- line segments
- ribbons
- fractured geometry
- particle fields
- nested torus-like structures
- animated emissive materials

Create depth by layering:

`foreground geometry -> midground structure -> bright core -> background particles`

Use nonuniform rotation to prevent mechanical symmetry.

---

# 20. Blue Liquid / Distortion Scene

The reference sequence also includes a high-saturation blue environment with a white figure and highly distorted/liquid-looking surfaces.

This is best treated as a **material and post-processing scene**, not as ordinary CSS.

Possible techniques:

- refractive/transparent shader
- displacement map
- screen-space distortion
- noise-based vertex displacement
- fluid-like texture
- refraction or fake refraction
- bloom
- depth of field

The point is to create the impression that the subject is inside or surrounded by a living material.

---

# 21. White Hero / Figure Ending

After the intense cinematic sequence, move back toward a clean white scene with the 3D subject isolated against white.

This provides visual decompression.

Use:

- white background
- soft contact shadow
- centered subject
- subtle movement
- minimal typography

This reset is important. Do not maintain maximum visual intensity for the whole page.

---

# 22. Navigation and UX Minimalism

The UI should remain visually small even when the media becomes huge.

Primary actions:

- Menu
- Let's Talk / Contact
- Play
- Mute
- Close
- Project navigation
- Newsletter

Avoid unnecessary controls.

### Cursor

Use the native cursor by default unless an alternate cursor materially improves the experience.

When using a custom cursor:

- make it small
- use it only during interactive media moments
- preserve obvious click affordance
- disable it on touch devices
- respect reduced-motion and accessibility settings

Never let the custom cursor obscure important text.

---

# 23. Microinteractions

Every interactive surface should have a subtle response.

Examples:

### CTA button

Hover:
- translate icon a few pixels
- interpolate background/text contrast
- optionally expand by 2–5%

### Menu

Hover:
- tiny dot movement
- text tracking change
- slight scale

### Project item

Hover:
- media movement
- arrow reveal
- title shift

### Scroll indicator

Animate gently while waiting for user input.

### Newsletter input

Focus:
- minimal border/color transition
- visible keyboard focus ring

Microinteractions should reinforce physicality.

---

# 24. Audio / Sound Design

Treat audio as an optional immersive layer, never as a requirement for understanding the site.

The reference architecture exposes PLAY/MUTE-style controls and is suitable for sound-linked experiences.

### Audio layers

Potential layers:

- ambient bed
- scene transition swell
- hover tick/click
- 3D object impact
- media start/stop sound
- navigation sound
- subtle spatial texture

### Rules

- never autoplay loud audio unexpectedly
- default to muted where browser policy or UX requires it
- make mute state obvious
- keep interaction sounds quiet
- avoid continuous audio fatigue
- fade audio between scenes

### Spatial audio

For advanced experiences, use Web Audio API or Three.js positional audio.

Map sound to scene coordinates so moving through the space changes perceived intensity.

A useful pattern is:

`camera/object distance -> gain`

and

`object interaction -> short transient sound`

### Music

Prefer a restrained electronic/ambient/experimental soundtrack.

The music should support pacing rather than compete with content.

Do not use generic corporate background music.

---

# 25. Sound State Architecture

Maintain a global audio state:

```js
const audioState = {
  enabled: false,
  masterVolume: 0.8,
  sceneVolume: 1.0,
  effectsVolume: 0.65,
};
```

Every scene should be able to register:

- ambient track
- transition track
- effects
- spatial emitters

Use crossfades rather than hard cuts.

---

# 26. Performance Engineering

Immersive websites fail when visual ambition is not matched by engineering.

Treat performance as part of design from day one.

### Targets

Aim for:

- responsive interaction on desktop
- stable animation timing
- graceful degradation on weak GPUs
- minimal main-thread blocking
- optimized assets

### Techniques

Use where appropriate:

- WebGL / WebGPU when justified
- Three.js
- instancing
- geometry batching
- texture compression
- mipmaps
- adaptive pixel ratio
- lazy loading
- preloading only critical hero assets
- level of detail
- object pooling
- frustum culling
- post-processing only when visually justified
- Web Workers for expensive non-render tasks
- OffscreenCanvas where it genuinely improves architecture

A public Lusion technical demo also demonstrates the importance of synchronizing DOM scrolling and WebGL visuals, while Lusion projects demonstrate procedural GPU-friendly approaches and real-time 3D/WebXR work.

Do not add advanced techniques merely to sound technical. Measure first.

---

# 27. Three.js Architecture

Recommended structure:

```text
src/
  app/
    layout
    page
  components/
    Header
    Menu
    Hero
    ProjectGrid
    ReelSection
    EditorialSection
    ImmersiveSection
    Footer
  three/
    SceneManager
    CameraController
    Renderer
    AssetLoader
    MaterialFactory
    PostFX
    InteractionManager
    AnimationTimeline
  scenes/
    HeroScene
    TunnelScene
    EnergyScene
    LiquidScene
  audio/
    AudioManager
    SceneAudio
```

The exact framework may be React/Next.js, Vue/Nuxt, or another modern setup. Choose the framework already used by the project. The architecture is more important than the brand of framework.

---

# 28. Shared Scene Manager

Do not create a new renderer for every section.

Prefer one shared renderer/canvas and switch or blend scene states.

Conceptually:

```js
sceneManager.setScene('hero');
sceneManager.transitionTo('tunnel', {
  duration: 1.8,
  ease: 'power3.inOut',
});
```

This reduces expensive setup/teardown and makes transitions much more cohesive.

---

# 29. DOM + WebGL Synchronization

DOM content and WebGL should be synchronized to one normalized progress value.

Example:

```js
const progress = clamp(scrollProgress, 0, 1);

headline.setProgress(progress);
heroScene.setProgress(progress);
background.setProgress(progress);
videoController.setProgress(progress);
```

For pinned cinematic sections, map a local section progress to the scene:

```js
const local = mapRange(sectionStart, sectionEnd, scrollY);
scene.setProgress(local);
```

This makes text, camera, and media feel choreographed instead of independently animated.

---

# 30. Camera Motion

Camera movement is one of the main sources of perceived quality.

Use:

- dolly forward/backward
- orbital movement
- subtle x/y drift
- controlled focal-length changes
- target interpolation
- depth transitions

Avoid constant camera spinning.

The camera should have a narrative purpose:

- reveal
- approach
- escape
- descend
- orbit
- focus

Use damped interpolation rather than direct pointer-to-camera mapping.

---

# 31. Pointer Interaction

Pointer data can control:

- camera offset
- object rotation
- shader parameters
- distortion
- parallax
- particle attraction
- hover state
- sound intensity

Normalize pointer coordinates:

```js
const x = (pointerX / viewportWidth) * 2 - 1;
const y = (pointerY / viewportHeight) * 2 - 1;
```

Then damp:

```js
currentX += (targetX - currentX) * 0.08;
currentY += (targetY - currentY) * 0.08;
```

This creates a soft physical response rather than a robotic one.

---

# 32. Motion Principles

Use easing deliberately.

Preferred families:

- `power2.inOut`
- `power3.inOut`
- `expo.out` for controlled impact
- smooth spring-like interpolation
- custom curves for cinematic events

Avoid default linear movement for primary animations.

Do not use bounce easing for sophisticated editorial transitions unless the concept explicitly calls for playful physics.

---

# 33. Blur, Bloom, and Optical Effects

Use optical effects sparingly.

Useful effects include:

- bloom
- depth of field
- motion blur
- chromatic aberration
- film grain
- vignette
- radial blur
- screen-space distortion

These should support depth and atmosphere.

Bad use:

`add every post-processing effect to every scene`

Good use:

`increase bloom for an energy scene, reduce it for editorial scenes, remove it for clean white sections`

---

# 34. Media Loading

Hero assets must be prioritized.

Recommended strategy:

1. render a clean shell immediately
2. preload critical hero poster/texture
3. display low-resolution placeholder if necessary
4. load high-resolution asset
5. initialize heavy 3D scene after first meaningful paint when possible
6. stream secondary project media lazily

Never block the entire page on an experimental 3D scene.

---

# 35. Reduced Motion / Accessibility

Create a real reduced-motion mode.

When `prefers-reduced-motion: reduce` is active:

- remove camera rushes
- disable rapid scale changes
- reduce parallax
- reduce particle counts
- replace long scroll-controlled animations with short fades
- avoid automatic media motion where unnecessary
- keep content and navigation fully usable

All buttons and inputs need accessible names.

Text must remain readable independent of the cinematic background.

Keyboard navigation must work for:

- menu
- contact
- reel
- project links
- newsletter
- mute/play

---

# 36. Mobile Art Direction

Do not simply scale the desktop page down.

Create an intentional mobile composition.

On mobile:

- reduce object count
- reduce render resolution/pixel ratio
- simplify post effects
- shorten cinematic sections
- adjust typography scale
- move text away from important 3D subjects
- convert complex pointer interactions to touch gestures
- avoid hover-dependent functionality

Possible touch mapping:

- one finger drag = camera/object movement
- tap = select
- swipe = navigate
- pinch = zoom when meaningful

But never require gestures to understand the page.

---

# 37. Footer

The footer should act as the final scene, not as an information dump.

Recommended composition:

- large closing statement
- contact CTA
- address
- email
- social links
- newsletter
- legal links
- small copyright/build credit

The reference uses a restrained contact/newsletter architecture after the cinematic content.

A dark footer can provide a final dramatic contrast, but white is also acceptable if it fits the original identity.

---

# 38. Newsletter UI

Keep the newsletter form minimal.

Example:

`Subscribe to our newsletter`

`[ Your email                         -> ]`

Use a simple underline or soft field treatment.

Do not turn the footer into a SaaS signup dashboard.

On focus:

- show clear focus state
- animate arrow subtly
- validate input accessibly

---

# 39. Page-Level Story Arc

Use this general sequence as a blueprint:

```text
SCENE 01
Clean white hero
Large positioning statement
3D object cluster

SCENE 02
Featured work
Mixed media
Hover-driven interaction

SCENE 03
Saturated reel section
Large PLAY interaction

SCENE 04
Editorial statement
Oversized type
Aqua procedural stroke

SCENE 05
Calm text + device/media object

SCENE 06
White -> black transition
Immersive 3D character
Large white statement

SCENE 07
High-energy tunnel
Multicolor lights
Camera acceleration

SCENE 08
Geometric energy core
Red / magenta / cool blue

SCENE 09
Blue liquid/distortion world

SCENE 10
Minimal white character scene

SCENE 11
Closing CTA

SCENE 12
Footer/contact/newsletter
```

This is a narrative template, not a requirement to reproduce the exact current site.

---

# 40. Transition Language

The transition system is more important than individual effects.

Every scene should use one or more of:

- color dissolve
- camera movement
- typography migration
- scale transformation
- media morph
- blur bridge
- masked reveal
- shared object continuity

The best transitions preserve at least one visual element from the previous scene and transform it into something in the next scene.

Example:

`cyan stroke -> curved tunnel light`

or

`white 3D figure -> same figure inside black environment`

This creates continuity.

---

# 41. Reusable Scene Presets

Build reusable scene primitives.

### GlossyClusterScene

For hero abstract objects.

### EditorialStrokeScene

For animated line graphics.

### CinematicTunnelScene

For speed and depth.

### EnergyCoreScene

For glowing geometric complexity.

### LiquidDistortionScene

For fluid/refractive effects.

### CharacterVoidScene

For isolated 3D subject storytelling.

### MediaCarouselScene

For interactive project previews.

---

# 42. Visual Hierarchy Rules

At any moment, the user should know the intended focal point.

Use the hierarchy:

```text
1. hero object / cinematic subject
2. primary headline
3. primary action
4. supporting text
5. navigation / metadata
```

Never make the navigation visually louder than the experience.

Do not allow decorative particles to overpower the CTA or headline.

---

# 43. Interaction Priority

Not everything needs interaction.

Prioritize:

1. scroll
2. project hover/click
3. menu
4. primary CTA
5. sound/media controls
6. optional experimental interactions

A page can feel extremely interactive even when only a few elements actually respond.

---

# 44. What Makes the Reference Feel Premium

Reproduce these qualities:

- extremely clean base typography
- controlled whitespace
- excellent asset quality
- sophisticated lighting
- material realism
- intentional transitions
- restrained UI
- scene-level color changes
- smooth interpolation
- custom motion timing
- visual contrast between calm and intense moments
- strong art direction
- excellent image cropping
- strong performance

Do not confuse complexity with quality.

A single perfect 3D object with exceptional lighting is better than twenty mediocre objects.

---

# 45. Anti-Patterns

Never build the following:

- random floating 3D blobs without narrative purpose
- autoplay audio with no obvious mute control
- endless scroll with no rhythm
- a different animation style in every section
- giant text over unreadable backgrounds
- heavy post-processing on every scene
- custom cursor everywhere
- hover-only critical navigation
- 3D that takes several seconds to become usable
- a loading screen that exists purely to hide slow engineering
- generic stock imagery mixed with unrelated futuristic effects

---

# 46. Quality Bar for 3D Assets

Every important 3D asset should have:

- clean topology or efficient geometry
- optimized materials
- believable scale
- coherent lighting
- intentional composition
- clear silhouette
- controlled animation

When realism is desired:

- use PBR materials
- use high-quality environment reflections
- use contact shadows
- use subtle roughness variation
- use realistic falloff

When stylization is desired:

- simplify geometry deliberately
- use bold material separation
- exaggerate silhouettes
- keep lighting coherent

---

# 47. Asset Pipeline

Recommended pipeline:

```text
Concept / Art Direction
        ↓
3D modeling / sculpting
        ↓
UV + materials
        ↓
Optimization
        ↓
GLB / texture export
        ↓
Three.js asset loader
        ↓
Scene composition
        ↓
Interaction
        ↓
Scroll timeline
        ↓
Performance tuning
```

Use Blender, Cinema 4D, Houdini, or another DCC depending on the project.

Do not ship source DCC assets to the browser.

---

# 48. Shader Direction

Custom shaders should be introduced when they materially improve the visual concept.

Useful shader effects:

- noise displacement
- iridescence
- Fresnel edges
- procedural stripes
- emissive pulse
- liquid distortion
- dissolve
- vertex wave
- holographic color shift
- depth-based fade

Keep shader complexity proportional to the device target.

---

# 49. Physics

Use real physics only when interaction benefits from it.

Good use cases:

- loose object clusters
- dragging
- collision reactions
- bouncing primitives
- physically believable particles

Possible libraries:

- Rapier
- Cannon-es
- Ammo.js

For dense scenes, prefer simplified colliders and selective simulation.

Do not simulate everything.

---

# 50. Procedural Systems

Procedural generation is useful for:

- particle positions
- light bars
- tunnels
- star fields
- line paths
- repeating structures
- dot/globe patterns
- object scatter

Seed procedural systems so the composition remains deterministic when that helps debugging and asset consistency.

---

# 51. Video and WebGL Hybrid Rendering

Not every cinematic needs full realtime rendering.

A strong production architecture can combine:

- realtime hero 3D
- prerecorded cinematic video
- WebGL post-processing on video
- DOM typography
- interactive overlays

This often provides a better quality/performance ratio than attempting to reproduce every film-quality frame in realtime.

Use realtime rendering for interactions that genuinely benefit from interaction.

---

# 52. Technical Loading Experience

Loading UI should be minimal.

Avoid percentage counters unless they communicate something meaningful.

Preferred states:

`loading -> ready`

with subtle visual progression.

If a scene is heavy, display a high-quality poster or lightweight fallback first.

Once the scene is ready, crossfade it into the experience.

---

# 53. SEO and Semantic HTML

Even an immersive site needs normal web fundamentals.

Use:

- real headings
- real links
- semantic buttons
- descriptive alt text
- metadata
- Open Graph images
- structured internal navigation
- crawlable project names

Do not make the entire page a canvas.

The canvas is the visual layer. HTML should carry the semantic layer.

---

# 54. Error and Device Fallbacks

If WebGL is unavailable or performance is poor:

- show a high-quality static image/video version
- preserve all content
- preserve navigation
- preserve project links
- preserve contact forms

The site should degrade from:

`full immersive`

to

`cinematic media`

to

`clean editorial site`

without becoming unusable.

---

# 55. Implementation Order

Build in this order:

1. content architecture
2. base typography/grid
3. header and CTA
4. hero media
5. hero 3D
6. scroll state system
7. project gallery
8. reel section
9. editorial statement
10. cinematic scene
11. secondary effects
12. audio
13. mobile art direction
14. performance optimization
15. accessibility
16. polish

Do not start by writing dozens of shader files before the information hierarchy is stable.

---

# 56. Acceptance Criteria

The finished website should satisfy all of the following:

### Visual

- feels like a single art-directed experience
- strong editorial typography
- very high-quality media
- restrained base UI
- dramatic scene changes
- cohesive color language

### Motion

- scrolling drives meaningful transitions
- no abrupt section jumps
- camera and typography feel synchronized
- interactions have soft physicality
- transitions use intentional easing

### 3D

- materials look intentional
- lighting is coherent
- objects have believable depth
- scenes are optimized
- 3D is integrated with content rather than added beside it

### Audio

- mute/play state is clear
- no unwanted loud autoplay
- scene transitions can have audio feedback
- ambience does not interfere with reading

### UX

- navigation is obvious
- contact action is always accessible
- keyboard access works
- mobile is intentionally designed
- reduced motion works

### Performance

- critical content appears quickly
- heavy scenes load progressively
- DPR is adaptive
- GPU load is monitored
- secondary media is lazy-loaded

---

# 57. Creative Direction Prompt for Claude

When asked to generate the site, Claude should think and work like a combined:

- creative director
- art director
- motion designer
- 3D technical artist
- interaction designer
- frontend engineer
- performance engineer

Claude must not interpret the request as "add some animations."

Instead, Claude must design a complete visual system first and then implement it.

The expected workflow is:

```text
BRAND IDEA
  ↓
ART DIRECTION
  ↓
PAGE STORYBOARD
  ↓
TYPOGRAPHY SYSTEM
  ↓
COLOR SYSTEM
  ↓
3D / MEDIA SYSTEM
  ↓
MOTION SYSTEM
  ↓
INTERACTION SYSTEM
  ↓
AUDIO SYSTEM
  ↓
TECHNICAL ARCHITECTURE
  ↓
PERFORMANCE
  ↓
ACCESSIBILITY
  ↓
FINAL POLISH
```

---

# 58. Claude Build Instructions

When implementing a website based on this skill:

1. Start with a complete page map before writing detailed code.
2. Explain the role of each major visual scene internally in the implementation plan.
3. Use a shared motion/progress state so DOM, media, and WebGL stay synchronized.
4. Build the visual shell before adding expensive effects.
5. Use genuine 3D or high-quality video where possible instead of fake CSS approximations.
6. Keep the navigation extremely small.
7. Make typography a major visual component.
8. Use large calm areas between intense cinematic sequences.
9. Give every major scene a distinct but compatible color and material identity.
10. Use progressive enhancement for heavy rendering.
11. Add reduced-motion and non-WebGL fallbacks.
12. Test desktop and mobile separately as art-directed experiences.
13. Keep interactions smooth and damped rather than abrupt.
14. Do not introduce effects simply because they are technically possible.
15. Prefer one extraordinary interaction to ten mediocre interactions.

---

# 59. Originality Requirement

This skill is **Lusion-inspired**, not a direction to clone Lusion.

Do NOT reproduce:

- the Lusion logo
- Lusion project images
- exact project names unless they are being referenced historically in an analysis
- their proprietary 3D assets
- their exact text
- their exact page source
- exact coordinates, timings, or animations
- exact color values solely for the purpose of duplication

Instead, create a new identity with:

- original brand typography
- original 3D assets
- original soundtrack
- original scene concepts
- original project content
- original animation choreography

Match the **quality, interaction philosophy, spatial storytelling, and technical ambition**, not the copyrighted expression.

---

# 60. Final Definition of Success

A successful result should feel less like:

> "a portfolio page with some WebGL"

and more like:

> "a digital world that happens to contain a portfolio."

The user should experience a deliberate rhythm:

`clarity -> curiosity -> interaction -> spectacle -> calm -> immersion -> release -> contact`

The final impression should be:

**premium, original, tactile, cinematic, technically sophisticated, and memorable.**

---

## Reference Sources Used for This Skill

- Lusion homepage: https://lusion.co/
- Lusion project archive: https://lusion.co/projects/
- Lusion WebGL Scroll Sync demo: https://webgl-scroll-sync.lusion.co/
- Lusion experimental/interactive work, including WebGL/WebXR/3D examples: https://labs.lusion.co/
- Lusion project pages documenting WebGL, 3D, WebXR and related production work.

These references are used to describe the visible design language and publicly documented technical direction. They are not evidence that every implementation detail of the current homepage uses a specific framework or library unless that implementation is publicly documented.
