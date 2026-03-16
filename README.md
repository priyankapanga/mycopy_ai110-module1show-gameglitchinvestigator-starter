# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable.

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: _"How do I keep a variable from resetting in Streamlit when I click a button?"_
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

- [ ] Describe the game's purpose.
      The purpose is to be an entertaining game where the user tries to guess the secret number in a limited number of tries/attempts
- [ ] Detail which bugs you found.
      -Difficulty level and number range mismatch
      -The hints were misleading, it asked the user to go higher if there guess was higher than the secret number
      -Problems with changing secret number and restting the number of attempts
- [ ] Explain what fixes you applied.
      I fixed the difficulty-level mismatch. The normal range is now 1-50 and the hard range is 1-100. This range is also reflected in the prompt to the user/player. I also fixed the misleading hints, displaying the correct ones based on whether the user guessed higher or lower!

## 📸 Demo

- [ ] ![Demo screenshot](demo.png)


## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, insert a screenshot of your Enhanced Game UI here]
