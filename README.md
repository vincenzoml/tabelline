# Tabelline - Multiplication Tables Game

An interactive game to help children learn multiplication tables with colorful visual representation and game elements.

## Game Description

"Tabelline" is an educational game designed to make learning multiplication tables fun and engaging. The game presents multiplication questions and visualizes them with colorful blocks arranged in a grid, helping children understand the concept of multiplication as repeated addition.

## Features

- Interactive multiplication questions appropriate to player level
- Visual representation of multiplication using colorful blocks that appear row by row
- Progressive difficulty levels (1-10)
- Lives system (3 hearts) instead of points
- Sound effects for correct and incorrect answers
- Voice feedback with encouraging phrases in Italian
- Background music (starts only after user interaction)
- Time challenge mode with countdown timer
- Auto-commute feature that automatically swaps operands every 8 seconds
- Visual feedback for answers (green flash for correct, shake animation for incorrect)
- Game over and level advancement mechanics
- Automatic game reset 2 seconds after game over
- Retro pixel art styling with "Press Start 2P" font
- Responsive design for different screen sizes

## Game Mechanics

### Lives System
- Players start with 3 lives (displayed as hearts)
- Incorrect answers or timeouts result in losing one life
- Game ends when all lives are lost

### Scoring and Levels
- Each level requires more correct answers to advance (level × domandePerLivello)
- Maximum level is 10
- Difficulty increases with each level (larger numbers in multiplication)
- Players receive verbal encouragement for correct answers
- Fast answers (before all rows appear) receive special praise

### Auto-commute Feature
- Every 8 seconds, the operands automatically swap (e.g., 3×4 becomes 4×3)
- The commute button flashes when auto-commute is active
- Manual commutation resets the auto-commute timer
- Auto-commute is disabled during timed challenges

### Time Challenge
- Optional timer that counts down from 15 seconds
- Losing a life when time expires
- Visual progress bar showing remaining time

## User Interaction Features

- Custom input field with improved focus management
- Input locking after answering to prevent accidental double submissions
- Visual fade effect when input is temporarily disabled
- Automatic verification when correct answer is typed
- Input field clears immediately after answer submission
- Game only starts when player clicks "Play" button
- Game resets automatically 2 seconds after game over

## Implementation Notes

### Visual Representation
- Multiplication shown as a grid of colored blocks
- Blocks appear row by row to visualize multiplication as repeated addition
- Color of blocks based on the first operand

### User Experience Improvements
- Input field temporarily disables with fade effect after answer submission
- Answer verification triggers automatically when correct answer is typed
- Focus maintained on input field throughout gameplay
- Clear visual and audio feedback for all interactions

### Technical Details
- Built with HTML, CSS, and vanilla JavaScript
- No external libraries needed
- Uses CSS animations and transitions for visual feedback
- Uses Web Speech API for voice narration
- Uses HTML5 audio for sound effects and music
- Grid-based visualization of multiplication
- Uses modern ES6 JavaScript features

## How to Play

1. Click the "Play" button to start the game
2. Answer the multiplication questions by typing the result in the input field
3. Click "Verify Answer" or press Enter to submit
4. Try to advance through all the levels
5. Toggle the timed challenge option for an extra challenge
6. Use the "Commuta" button to swap the order of numbers
7. Game automatically resets after Game Over

## Audio Credits

The game uses 8-bit style sound effects for a retro arcade feel:

- Sound effects: CC0 licensed 8-bit sounds
- Background music: CC0 licensed 8-bit music loop

## Browser Compatibility

The game works on all modern browsers that support:
- ES6 JavaScript
- CSS Grid and modern animations
- HTML5 Audio
- Web Speech API
- CSS Variables

## License

This game is free to use for educational purposes. 