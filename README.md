# Tabelline - Multiplication Tables Game

A comprehensive specification for building an interactive multiplication tables learning game.

## Project Overview

"Tabelline" is an educational web-based game designed to help children learn multiplication tables through interactive gameplay, visual aids, and encouraging feedback. This document provides the specifications required to build the game from scratch.

## Core Requirements

### Functional Requirements

1. **Game Presentation**
   - Present multiplication questions (num1 × num2) to players
   - Display a visual grid of colored blocks representing the multiplication
   - Allow players to input answers via keyboard
   - Verify answers and provide immediate visual and audio feedback
   - Progress through levels of increasing difficulty
   - Implement a lives system (3 hearts)
   - End game when all lives are lost
   - Auto-reset game 2 seconds after game over

2. **Visualization Requirements**
   - Display multiplication as a grid of colored blocks (num1 columns × num2 rows)
   - Animate blocks to appear row by row with configurable timing
   - Color blocks based on the first operand (using a predefined color palette)
   - Provide clear visual feedback for correct/incorrect answers
   - Implement visual timer bar

3. **User Interaction Requirements**
   - Custom numeric input field supporting keyboard input
   - Auto-verification when correct answer is typed
   - Input locking mechanism to prevent multiple submissions
   - "Play" button to start the game
   - "Commuta" (swap) button to switch operands
   - "Reset" button to restart the game
   - Focus management that maintains input focus during gameplay
   - 15-second countdown timer for each question

4. **Feedback Requirements**
   - Voice feedback with encouraging phrases in Italian
   - Sound effects for correct and incorrect answers
   - Background music (starting only after user interaction)
   - Visual animations for correct/incorrect answers
   - Display "SÌ" (yes) for correct answers and "NO" for incorrect answers
   - Special praise for fast answers (before all rows appear)

### Non-Functional Requirements

1. **Visual Design**
   - Retro pixel art aesthetic
   - "Press Start 2P" font for text elements
   - Colorful, child-friendly interface
   - Responsive design for different screen sizes
   - Visual accessibility considerations (contrast, size)

2. **Performance**
   - Game must initialize quickly
   - Animations must run smoothly
   - Audio must play without delay
   - Input handling must be responsive

3. **Compatibility**
   - Must work on modern browsers (Chrome, Firefox, Safari, Edge)
   - Must work on desktop and mobile devices
   - Must handle touch and keyboard inputs

## Technical Specifications

### HTML Structure

- Main container div with game title
- Stats display area (level, lives)
- Play button to start the game
- Game area (hidden until play begins) containing:
  - Question display
  - Visual blocks container
  - Operation display (showing the equation)
  - Custom input field
  - Timer bar
  - Control buttons (verify, commuta, reset)
  - Lives display (3 hearts)
- Game over overlay
- Audio elements (hidden)

### CSS Requirements

- Responsive grid layout
- Animations for:
  - Correct answer (green flash)
  - Incorrect answer (shake animation)
  - Button flashing for auto-commute
  - Heart pulse for lives
  - Block appearance
- Styling for custom input field
- Game over overlay styling
- Timer bar styling
- Media queries for responsiveness

### JavaScript Functionality

1. **Core Game Logic**
   - `generaDomanda()`: Generate random multiplication questions based on level
   - `verificaRisposta()`: Verify user answers and provide feedback
   - `resetGame()`: Reset game state and create new question
   - `handleGameOver()`: Display game over screen and auto-reset
   - Level progression based on questions answered (level × domandePerLivello)

2. **Visual and Animation Logic**
   - `generaBlocchetti(n1, n2)`: Create visual block grid
   - `showRowByRow(n1, n2)`: Animate blocks appearing row by row
   - Visual feedback animations for correct/incorrect answers
   - Timer bar animation

3. **User Input Handling**
   - `handleUserInput(key)`: Process keyboard input
   - `updateCustomInput()`: Update the custom input display
   - Input focus management
   - Auto-verification for correct answers
   - Input locking during answer processing

4. **Special Features**
   - `commutaOperandi()`: Swap operands to teach commutative property
   - `startAutocommute()`: Auto-commute feature (swapping every 8 seconds)
   - `startTimer()`: 15-second countdown timer
   - `updateLives()`: Update the visual lives display

5. **Audio and Speech**
   - `playAudio(audioId)`: Play sound effects
   - `speakText(text, rate, callback)`: Text-to-speech functionality
   - `startMusicaWithInteraction()`: Start background music after user interaction

### Game Variables and Constants

1. **Game State Variables**
   - `lives`: Number of remaining lives (starting with 3)
   - `livello`: Current level (starting at 1, max 10)
   - `domandeFatte`: Questions answered in current level
   - `domandePerLivello`: Questions required per level
   - `isProcessingAnswer`: Boolean to prevent multiple inputs
   - `num1`, `num2`, `risultato`: Current question values

2. **Timing Parameters**
   - `autocommutaInterval`: 8000ms (8 seconds) between auto-commutes
   - `rowAppearDelay`: 1000ms (1 second) delay between rows appearing
   - `tempoRimanente`: 15 seconds per question

3. **Feedback Phrases**
   - `phrasesFast`: Array of phrases for fast correct answers
   - `phrasesSlow`: Array of phrases for correct answers
   - `phrasesWrong`: Array of phrases for incorrect answers

## Implementation Details

### Initialization Sequence
1. Wait for "Play" button click
2. Hide play button, show game area
3. Initialize lives and level
4. Start timer
5. Generate first question
6. Start auto-commute feature (if not in time challenge)

### Question Generation
1. Choose random numbers based on level (max value = min(level + 1, 10))
2. Calculate result
3. Display operation
4. Generate and animate colored blocks
5. Speak the question aloud
6. Start countdown timer

### Answer Verification Flow
1. Block further input immediately
2. Check if answer is correct
3. Apply visual feedback (green flash or shake)
4. Update lives if incorrect
5. Display "SÌ" or "NO" based on result
6. Play appropriate sound effect
7. Speak encouraging phrase or correction
8. Check for game over condition
9. Check for level advancement
10. Generate new question after a delay

### Time Challenge Implementation
- Always-on 15-second countdown timer
- Visual progress bar decreases as time passes
- When timer reaches zero:
  - Player loses a life
  - "Tempo scaduto!" message spoken
  - Same consequence as an incorrect answer
  - Check for game over condition

### Auto-commute Feature
- Every 8 seconds, automatically swap operands (num1 and num2)
- Update visual display and blocks
- Commute button flashes during auto-commute
- Manual commutation resets the auto-commute timer
- Feature disabled when game starts as time challenge is always active

## Audio and Voice Requirements

### Sound Effects
- Correct answer sound (audioCorretto)
- Incorrect answer sound (audioSbagliato)
- Background music loop (musicaDiSottofondo)

### Voice Feedback
- Read aloud each question ("num1 ... per ... num2?")
- Speak encouraging phrases for correct answers
- Speak helpful corrections for incorrect answers
- Speak "Tempo scaduto!" (Time's up!) when timer expires

## Browser Requirements
- Must support Web Speech API
- Must support HTML5 Audio
- Must support ES6 JavaScript
- Must support CSS Grid and animations
- Must support CSS Variables

This specification provides all necessary details to rebuild the Tabelline game with identical functionality and appearance. 