# QWERTY Tempered - Specification

## Project Overview
- **Project Name**: QWERTY Tempered
- **Type**: Web-based equal-tempered synthesizer
- **Core Functionality**: A polyphonic synthesizer with 26 alphabetic keys spanning exactly one octave (equal tempered), three oscillators with individual mix/detune, lowpass filter, arpeggiator, octave shift modifiers, sustain pedal, accent, and noise
- **Target Users**: Musicians and experimenters who want to play across an octave using the full keyboard

## UI/UX Specification

### Layout Structure
- **Container**: Full viewport, centered content
- **Sections**:
  1. Header: Title
  2. Controls: Base frequency, volume
  3. Arpeggiator: Toggle, direction, octave, rate
  4. Keyboard: QWERTY layout with modifiers and sustain
  5. Oscillator controls: Three oscillators (OSC1, OSC2, OSC3) with waveform, volume, detune
  6. Filter: Cutoff frequency, resonance
  7. Envelope controls: ADSR
  8. Active notes display
  9. Controls help text

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
- Modifier row: [,] [SPACE SUSTAIN] [.]

## Functionality Specification

### Core Features
1. **26-Key Keyboard**: All alphabetic keys (Z to P) span exactly one octave
2. **Equal Temperament**: All notes equally spaced (25 equal divisions per octave)
3. **Three Oscillators**: Three independent oscillators with waveform selection
4. **Mix Control**: Individual volume for each oscillator (OSC1, OSC2, OSC3)
5. **Detune**: Individual detune control for each oscillator (0-50 cents)
6. **Filter**: Lowpass filter with cutoff (100Hz-10kHz) and resonance (0-20)
7. **Arpeggiator**: Toggle on/off, direction (up/down/updown/random), octave range (0/+1/-1/±1), rate (50-500ms)
8. **Octave Shift**: Hold comma (,) for -1 octave, period (.) for +1 octave
9. **Sustain Pedal**: Hold spacebar to sustain notes
10. **Accent**: Hold SHIFT for accent (louder attack)
11. **Noise**: Press ENTER for white noise
12. **Sound Engine**: Web Audio API with ADSR envelope
13. **Oscillator Types**: Sine, Triangle, Sawtooth, Square

### Keyboard Controls
- A-Z: Play notes (Z = lowest, P = highest)
- `.` (period): Shift +1 octave for new notes
- `,` (comma): Shift -1 octave for new notes
- `Space`: Hold for sustain
- `Shift`: Hold for accent
- `Enter`: Toggle noise
- `/`: Toggle arpeggiator

### User Interactions
- Click or press key to play
- Use mouse sliders for ADSR, filter, oscillator mix/detune
- Select oscillator types for each oscillator
- Adjust arpeggiator settings

### Edge Cases
- Audio context requires user click to start
- Modifier keys only affect NEW notes, not already playing ones

## Acceptance Criteria
1. ✓ Z and P are exactly one octave apart
2. ✓ All 26 notes equally spaced
3. ✓ Three oscillators work independently
4. ✓ Individual mix sliders for each oscillator
5. ✓ Detune controls work for each oscillator
6. ✓ Lowpass filter shapes sound
7. ✓ Arpeggiator cycles through held notes
8. ✓ Octave shift works correctly
9. ✓ Sustain pedal works
10. ✓ Accent adds volume boost
11. ✓ Noise plays white noise
12. ✓ ADSR envelope shapes sound