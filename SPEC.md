# QWERTY Tempered - Specification

## Project Overview
- **Project Name**: QWERTY Tempered
- **Type**: Web-based equal-tempered synthesizer
- **Core Functionality**: A polyphonic synthesizer with 26 alphabetic keys spanning exactly one octave (equal tempered), with octave shift modifiers and sustain pedal
- **Target Users**: Musicians and experimenters who want to play across an octave using the full keyboard

## UI/UX Specification

### Layout Structure
- **Container**: Full viewport, centered content
- **Sections**:
  1. Header: Title
  2. Controls: Base frequency and volume
  3. Octave display (shows shift status)
  4. Keyboard: QWERTY layout with modifiers and sustain
  5. Envelope controls: ADSR + oscillator type
  6. Active notes display

### Visual Design

**Color Palette**
- Background: `#0a0a0f`
- Surface: `#14141f`
- Primary accent: `#ff6b35` (warm orange)
- Secondary accent: `#00d4aa` (cyan-teal)
- Tertiary: `#a855f7` (purple)
- Text primary: `#e8e8e8`
- Text muted: `#6b7280`
- Key white: `#2a2a3a`
- Key black: `#1a1a24`
- Border: `#2a2a3a`

**Typography**
- Font family: "JetBrains Mono"

**Visual Effects**
- Glow on active keys
- Grid pattern background

### Keyboard Layout
- Top row: Q W E R T Y U I O P
- Middle row: A S D F G H J K L
- Bottom row: Z X C V B N M
- Modifier row: [▲] [SPACE SUSTAIN] [▼]

## Functionality Specification

### Core Features
1. **26-Key Keyboard**: All alphabetic keys (Z to P) span exactly one octave
2. **Equal Temperament**: All notes equally spaced (25 equal divisions per octave)
3. **Octave Shift**: Hold comma (,) for -1 octave, period (.) for +1 octave
4. **Sustain Pedal**: Hold spacebar to sustain notes
5. **Sound Engine**: Web Audio API with ADSR envelope
6. **Oscillator Types**: Sine, Triangle, Sawtooth, Square

### Keyboard Controls
- A-Z: Play notes (Z = lowest, P = highest)
- `.` (period): Shift +1 octave for new notes
- `,` (comma): Shift -1 octave for new notes
- `Space`: Hold for sustain

### User Interactions
- Click or press key to play
- Use mouse sliders for ADSR envelope
- Select oscillator type

### Edge Cases
- Audio context requires user click to start
- Modifier keys only affect NEW notes, not already playing ones

## Acceptance Criteria
1. ✓ Z and P are exactly one octave apart
2. ✓ All 26 notes equally spaced
3. ✓ Octave shift works correctly
4. ✓ Sustain pedal works
5. ✓ ADSR envelope shapes sound