# 🎮 Game Glitch Investigator

## Demo

The game is a number-guessing app built with Streamlit. Players select a difficulty (Easy/Normal/Hard), then guess a secret number within a limited number of attempts. The app gives directional hints and tracks score.

## Document Your Experience

### Bugs Found and Fixed
- Reversed hint messages in `check_guess` (said "Go HIGHER" when guess was too high)
- String/int type mismatch on even-numbered attempts causing wrong comparisons
- Hard difficulty had a smaller range than Normal (1-50 vs 1-100)
- Score formula double-penalized players and inconsistently handled wrong guesses
- Attempt counter started at 1 instead of 0
- New Game button didn't reset game status, score, or history
- UI displayed hardcoded range "1 to 100" instead of actual difficulty range

### AI Collaboration
I used Claude to help identify and understand each bug's root cause. The AI was helpful for tracing logic errors (like the swapped hints), but the original AI-generated code also contained the bugs in the first place — including a misleading `try/except` workaround that masked a deeper type-mismatch issue. I made the final call on each fix and verified through pytest and manual playtesting.

### Testing
6 pytest cases covering core game logic all pass. Manual testing confirmed the game runs correctly across all three difficulty levels.

- [ ] [If you choose to complete Challenge 4, insert a screenshot of your Enhanced Game UI here]
