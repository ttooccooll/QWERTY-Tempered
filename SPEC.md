# Microtonal Synthesizer - Specification

## Project Overview
- **Project Name**: Micron
- **Type**: Web-based microtonal synthesizer
- **Core Functionality**: A polyphonic synthesizer that supports arbitrary divisions of the octave (2-TET to 128-TET), with real-time scale editing and a unique visual interface
- **Target Users**: Microtonal music composers, experimental musicians, music theory enthusiasts

## UI/UX Specification

### Layout Structure
- **Container**: Full viewport, centered content
- **Sections**:
  1. Header: Title and brief controls row
  2. Main Panel: Keyboard and scale visualization
  3. Controls Panel: Sound parameters and scale settings

### Responsive Breakpoints
- Desktop: Full keyboard (≥1024px)
- Tablet: Slightly condensed (768-1023px)
- Mobile: Stacked layout, smaller keys (<768px)

### Visual Design

**Color Palette**
- Background: `#0a0a0f` (near black with blue tint)
- Surface: `#14141f` (dark purple-black)
- Primary accent: `#ff6b35` (warm orange)
- Secondary accent: `#00d4aa` (cyan-teal)
- Tertiary: `#a855f7` (purple)
- Text primary: `#e8e8e8`
- Text muted: `#6b7280`
- Key white: `#2a2a3a`
- Key black: `#1a1a24`
- Active note: `#ff6b35` (orange glow)
- Scale highlight: `#00d4aa`

**Typography**
- Font family: "JetBrains Mono" (monospace aesthetic)
- Title: 28px, weight 700
- Labels: 12px, uppercase, letter-spacing 2px
- Values: 14px, weight 500

**Spacing System**
- Base unit: 8px
- Panel padding: 24px
- Element gap: 16px
- Border radius: 4px (sharp, technical feel)

**Visual Effects**
- Subtle glow on active elements (box-shadow with accent color)
- Faint grid pattern on background
- Smooth transitions (150ms ease-out)
- Piano keys with subtle gradient

### Components

**1. Scale Selector**
- Dropdown or number input for divisions per octave (2-128)
- Preset scales dropdown (12-TET, 24-TET, 31-TET, 53-TET, Just Intonation ratios)
- Visual scale degree markers on keyboard

**2. Piano Keyboard**
- 2+ octaves of playable keys
- Keys highlight when scale degrees are present
- Click/touch to play
- Computer keyboard mapping (QWERTY)

**3. Parameter Controls**
- Oscillator type: sine, square, sawtooth, triangle
- ADSR envelope controls (Attack, Decay, Sustain, Release)
- Detune control (cents)
- Master volume

**4. Scale Visualization**
- Horizontal bar showing all notes in the octave
- Interactive - click to toggle note inclusion in scale
- Shows frequency ratios or cent values

**5. Active Notes Display**
- Shows currently playing notes with frequency/cent values

## Functionality Specification

### Core Features
1. **Microtonal Scale Generation**
   - Calculate frequencies for any n-TET scale
   - Support Just Intonation via ratio input
   - Real-time scale switching

2. **Sound Engine**
   - Web Audio API oscillators
   - Polyphonic (up to 8 voices)
   - Envelope shaping
   - Smooth note transitions

3. **Keyboard Interaction**
   - Mouse/touch click to play
   - Keyboard mapping with visual feedback
   - Sustain functionality (hold spacebar)

4. **Scale Editing**
   - Toggle individual notes in scale
   - Custom ratio entry for Just Intonation
   - Save/load custom scales (localStorage)

### User Interactions
- Click key → trigger note with attack envelope
- Release key → trigger release envelope
- Change scale → recalculate all frequencies
- Adjust parameters → update in real-time

### Edge Cases
- Handle audio context autoplay restrictions (user gesture to start)
- Prevent audio clicking on rapid note changes
- Handle browser tab visibility (suspend/resume)

## Acceptance Criteria
1. ✓ Synthesizer produces sound on key press
2. ✓ Different scales produce different tunings (audible difference between 12-TET and 53-TET)
3. ✓ ADSR envelope shapes the sound noticeably
4. ✓ At least 4 different scale presets work correctly
5. ✓ Keyboard mapping allows playing from computer keyboard
6. ✓ UI is responsive and works on different screen sizes
7. ✓ No audio clicks or artifacts during normal use