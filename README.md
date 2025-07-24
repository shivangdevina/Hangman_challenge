# 🧠 Hangman API Solver — Strategy Submission

This project implements an automated strategy to solve Hangman puzzles using an official API. The core logic is written in Python and is designed to intelligently guess letters using frequency analysis and pattern filtering, running at scale over 1,000 games.

---

## 📁 Files Included

- `hangman_api_user (2).ipynb` – Complete implementation of the Hangman bot.
- `README.md` – Overview of the project structure, components, and strategy.

---

## ⚙️ 1. Initialization & Setup

- Imports libraries: `requests`, `random`, `string`, and others.
- Initializes API endpoint using a given access token and session key.
- Communicates with the API through standard `GET` and `POST` requests.

---

## 🎮 2. Game Start & API Integration

- Begins each game via the `/start_game` endpoint.
- Extracts response metadata:
  - `game_id`
  - `word_length`
  - `max_wrong_guesses`
- These are used to initialize and control the main guessing loop.

---

## 📖 3. Dictionary & Word Filtering

- A base dictionary of English words is used.
- At every step, the list is filtered based on:
  - Known letters in correct positions (e.g., `h__lo`)
  - Letters already guessed (to avoid repetition)
- This narrows the guess space dynamically as the game progresses.

---

## 🔤 4. Letter Guessing Strategy

- Guesses are made using frequency analysis on the filtered word list.
- Initially prioritizes high-frequency letters (e.g., `e`, `a`, `r`, etc.).
- Frequency recalculates as the word space narrows after each guess.

---

## 📡 5. API Request Handling

- Each guess is sent via the `/guess_letter` endpoint.
- API response includes:
  - Guess result (correct/incorrect)
  - Updated word state
  - Remaining attempts
- Automatically detects game end (win/loss) and proceeds to the next game.

---

## 🔁 6. Game Loop (1,000 Games)

- The notebook is set to run 1,000 games in succession.
- Tracks:
  - Game results
  - Guessed words
  - Total wins and losses

---

## 🛡️ 7. Error Handling

- Implements basic error checks for:
  - API timeouts
  - Malformed or invalid responses
- Gracefully skips or retries problematic sessions.

---

## ✨ 8. Optional Features

- Tracks total wins/losses for statistical analysis.
- Verbose vs silent logging modes (user-configurable).
- Easy toggle between random and frequency-based guessing modes.

---

## 💡 Strategy Summary

The bot combines:

- **Dictionary filtering** using the known letter positions and previous guesses.
- **Frequency-based analysis** to choose the next most probable letter.

This hybrid approach allows for significantly better performance than random guessing, especially across large sample sizes (like 1,000 games).

---

## 📬 Submission Instructions

Once the notebook has run through all 1,000 games, please reply to the assignment mail with:

1. The attached `hangman_api_user (2).ipynb` notebook  
2. This `README.md` file explaining the approach

Good luck! 🎯
