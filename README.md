# Quiz App

## Project Overview ✅
A simple browser-based quiz application that presents a sequence of multiple-choice questions, tracks the user’s score, and displays results at the end.

## Files 🔧
- `index.html` — The HTML entry point that defines the layout and structure of the UI (start button, question container, choices list, navigation buttons, and result display).
- `styles.css` — The stylesheet that contains visual styling for layout, visibility toggling (hidden/show), buttons, list items, and result formatting.
- `script.js` — The JavaScript file that contains the quiz logic and DOM interaction (explained below).

---

## `script.js` — What it does (no code included) 💡
**High-level behavior:**
- Waits for the page DOM to be ready, then initializes the app by selecting key DOM elements (buttons, question container, question text, choices list, result container, and score display).
- Contains a `questions` array of objects; each object includes a `question` string, a `choices` array, and an `answer` value indicating the correct choice.

**State & variables:**
- Tracks which question is current (`currentQuestionIndex`).
- Tracks the user’s `score` (number of correct answers).
- Uses a flag (`hasAnsweredCurrentQuestion`) to prevent multiple answers for the same question.

**Event listeners & user flow:**
- A **Start** control begins the quiz, hides the start screen, shows the first question, and prepares UI elements.
- A **Next** control advances to the next question or shows the final result when the quiz is finished.
- A **Restart** control resets state (index and score) and starts the quiz again.

**Functions & responsibilities:**
- `startQuiz` — hides the start UI and result area, reveals the question area, resets necessary state, and displays the first question.
- `showQuestion` — prepares the UI for the current question, hides the Next button until an answer is chosen, inserts the available choices into the choices list, and wires choice click handlers.
- `selectAnswer` — called when a user chooses an option; it ensures only the first click counts, checks the chosen value against the correct answer, increments the score if correct, and reveals the Next button.
- `showResult` — hides the question UI, reveals the result area, and displays the final score as "X out of Y".

**UX notes & limitations:**
- Choices are presented as list items that the user clicks; there’s no visual marking in the script for correct/incorrect selection besides score updates.
- Questions are shown in the defined order (no shuffling or randomization by default).
- No persistence (score or progress is not stored across page reloads).
- No timer or per-question time limits.
- Pressing **Exit** during the quiz or on the result screen will prompt for confirmation; if confirmed, the app returns to the initial start view and resets progress/score (does not close the browser tab).

---

## How to run ▶️
1. Open `index.html` in a modern web browser.
2. Click **Start** to begin, select choices, use **Next** to move forward, and **Restart** to try again.

## Tips for editors ✍️
- To add or modify questions, edit the `questions` array in `script.js` (add new question objects or change text/choices/answer).
- To add feedback for correct/incorrect selections or to highlight answers, update the DOM manipulation inside the choice click handlers.

---

## License & Contributing
Feel free to modify and extend this project. Create issues or pull requests if you want to add features (e.g., question randomization, persistence, animations, or accessibility improvements).