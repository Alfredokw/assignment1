# Math Challenge Game

A browser-based arithmetic game built with HTML, CSS, and JavaScript. Players select two moving number bubbles and apply the highlighted operation to reach a target number before the timer runs out.

The game combines arithmetic practice with animated interaction, immediate answer feedback, sound effects, and a session results screen.

## Features

- **Four arithmetic operations:** addition, subtraction, multiplication, and division.
- **Randomized questions:** each question displays ten distinct numbers from 1 to 50.
- **Solvable targets:** the generator selects an integer target of at most 100 from a valid pair of displayed numbers.
- **Animated bubbles:** number bubbles drift around the play area, with collision checks and a breathing animation.
- **Configurable duration:** choose a session length from 1 to 999 minutes; the default is one minute.
- **Immediate feedback:** correct and incorrect answers are indicated using messages, colors, and sounds.
- **Results tracking:** view correct-answer and incorrect-attempt counts when the timer ends.
- **Audio:** background music and selection, success, and error sound effects.
- **Menu navigation:** start a session from the menu and return to it from the game or results screen.

## Technologies

| Technology | Purpose |
| --- | --- |
| HTML | Menu, game interface, audio elements, and results screen. |
| CSS | Layout, bubble styling, animations, and visual feedback. |
| JavaScript | Question generation, input handling, movement, timer, and scoring. |
| Browser APIs | DOM manipulation, audio playback, animation frames, and timers. |

The project runs entirely in the browser. It does not require a backend, database, package manager, or build step.

## Project Files

| File or directory | Purpose |
| --- | --- |
| `index.html` | Welcome menu and Start Game button. |
| `main_code.html` | Game interface and embedded CSS/JavaScript. |
| `Assets/images/cover2.png` | Menu cover image. |
| `Assets/images/background.jpg` | Game and ready-screen background. |
| `Assets/sounds/select.mp3` | Bubble selection sound. |
| `Assets/sounds/correct.mp3` | Correct-answer sound. |
| `Assets/sounds/incorrect.mp3` | Incorrect-answer sound. |
| `Assets/sounds/bgm.mp3` | Looping background music. |

**Filename setup:** if the downloaded HTML files are named `index(2).html` and `main_code(1).html`, rename them to **`index.html`** and **`main_code.html`**. The navigation links in the code expect these names.

Keep the `Assets` directory beside the HTML files and preserve the path capitalization. The image and audio files are referenced by the code and must be supplied separately if they are not included in your download.

## Getting Started

### Open directly

1. Place the HTML files and `Assets` directory in the same project folder.
2. Check the filenames described above.
3. Open `index.html` in a browser.
4. Click **Start Game ▶**.

### Run with a local server

If Python is installed, open a terminal in the project folder and run:

```bash
python3 -m http.server 8000
```

On Windows, you can use:

```powershell
python -m http.server 8000
```

Then open [http://localhost:8000/index.html](http://localhost:8000/index.html).

Python is only used here to serve the static files; the game itself runs in the browser.

## How to Play

1. Click **Start Game ▶** on the menu.
2. On the **Get ready!** screen, enter a duration in minutes.
3. Click **▶**, or press **Enter** while the duration field is focused.
4. Look at the target number beside 🎯 and the highlighted arithmetic operation.
5. Click two different number bubbles that produce the target.
6. Continue answering until the timer reaches zero.
7. Review your results and click **⬅ Back to Menu** to play again.

You can click the first selected bubble again to deselect it before choosing the second bubble. Selecting the second bubble checks the answer automatically.

### Arithmetic rules

| Operation | Rule | Example |
| --- | --- | --- |
| Addition | Add the selected numbers. | `12 + 8 = 20` |
| Subtraction | Use the absolute difference; selection order does not matter. | `abs(8 - 12) = 4` |
| Multiplication | Multiply the selected numbers. | `6 × 7 = 42` |
| Division | Divide the first selected number by the second; selection order matters. | `24 ÷ 6 = 4` |

The highlighted operation is selected by the game for each question. Players choose the numbers rather than changing the operation.

### Feedback and scoring

- A **correct answer** increases the correct-answer count and advances to a new question after a short transition.
- An **incorrect answer** increases the incorrect-attempt count. The selection resets after approximately two seconds, allowing another attempt at the same question.
- The countdown continues during feedback and transitions.
- When time expires, the results screen displays both counts and the background music pauses.

Scores apply to the current session and are not saved between visits.

## Customization

The CSS and JavaScript are embedded in `main_code.html`.

| Setting | Location in the code |
| --- | --- |
| Number range and bubble count | `generateUniqueNumbers()` |
| Target constraints and operation selection | `generateTarget()` |
| Arithmetic behavior | `operations` array |
| Session duration validation | `startGame()` and `gameTimeInput` |
| Bubble size, colors, and breathing animation | `.bubble` styles and `@keyframes breathe` |
| Movement speed and bounds | `moveBubbles()` |
| Feedback delays | `checkResult()`, `resetSelection()`, and `changeQuestion()` |
| Audio files and volume | Audio elements and volume assignments |
| Menu appearance | Styles in `index.html` |

## Current Limitations

- A mouse or touch interaction is required to select bubbles; keyboard-based bubble selection is not implemented.
- The layout uses fixed-size bubbles and viewport-based positions, so small screens may need layout adjustments.
- Audio playback depends on browser permissions and the availability of the referenced sound files.
- There is no pause control, persistent high-score storage, or difficulty selector.
- Questions and bubble movement use unseeded randomness.

## Troubleshooting

| Issue | Check |
| --- | --- |
| Start Game or Back to Menu opens a missing page | Use the exact filenames `index.html` and `main_code.html`. |
| Images do not appear | Check the `Assets/images/` paths and filenames. |
| Sounds do not play | Check the sound files, browser sound settings, and tab mute status. |
| Division answer is incorrect | Select the dividend first and the divisor second. |
| Duration is rejected | Enter a whole-number duration from 1 to 999 minutes. |

## Author

**Alfredo Lei**

