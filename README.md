# Chess Arena

## Summary

Chess Arena is a production-ready, static web application that provides a polished and responsive environment for playing chess against a powerful, onboard computer opponent. The application is designed to run smoothly on modern browsers without relying on remote engines or cloud calls. It features a genuine search algorithm, a comprehensive set of user interface features, and a high degree of polish to deliver a professional-grade chess experience.

## Setup

1.  **Clone the repository:**
    
```bash
    git clone https://github.com/your-username/chess-arena.git
    cd chess-arena
    ```


2.  **Install dependencies:**
    This project has no external dependencies. All necessary code is included in the repository.

3.  **Run the application:**
    Open the `index.html` file in your web browser to start the application.

## Usage

### Gameplay

*   **Moving Pieces:** Drag and drop pieces to their desired squares, or click a piece to highlight its legal moves and then click the destination square. The board supports mouse, touch, and keyboard input.
*   **Timers:** Choose between increment and countdown timers to manage game time.
*   **Game Controls:** Use the controls to undo/redo moves, resign the game, or offer a draw.
*   **Game Information:** The move list displays all moves in Standard Algebraic Notation (SAN). The score sheet tracks captured pieces and material advantage.

### Features

*   **PGN/FEN Import-Export:** Import games from PGN or FEN strings, and export your games for analysis in other tools.
*   **Themes:** Customize the appearance of the board and pieces with classic, high-contrast, and dark mode themes.
*   **Opening Book Hints:** Receive hints from a built-in opening book to improve your opening play.
*   **Post-Game Review:** Analyze your games with move-by-move commentary, an advantage chart, and options to share your game.

## Code Explanation

### Core Logic

The core chess logic, including move generation, validation, and game state management, is handled by a modified version of the `chess.js` library. This ensures strict adherence to all chess rules, including castling, en passant, and promotion.

### Rendering

The chessboard and pieces are rendered using a custom implementation inspired by `chessboard.js`, built with standard HTML, CSS, and JavaScript. The rendering is optimized for performance using `requestAnimationFrame` to ensure smooth animations and a responsive user interface.

### AI Opponent

The computer opponent is a JavaScript-based engine that runs in a Web Worker to prevent UI blocking. The AI's strength can be adjusted by changing its search depth. The core of the AI is a **minimax search algorithm with alpha-beta pruning**.

#### AI Architecture

1.  **Search Algorithm:** A depth-limited minimax search with alpha-beta pruning explores the game tree to find the best move.
2.  **Evaluation Heuristics:** The board position is evaluated using a combination of heuristics:
    *   **Material:** The total value of pieces on the board.
    *   **Piece-Square Tables:** Positional bonuses for pieces based on their location.
    *   **Mobility:** The number of legal moves available to each side.
    *   **King Safety:** Factors such as pawn shields and proximity of enemy pieces.
    *   **Pawn Structure:** The arrangement of pawns and their strengths/weaknesses.
3.  **Transposition Table:** A hash table is used to store previously evaluated positions, avoiding redundant calculations.

#### Tweaking Evaluation Weights

The AI's playing style can be modified by adjusting the weights of the evaluation heuristics. These weights are defined in `js/ai.js`. For example, to make the AI prioritize piece development, you can increase the weight of the piece-square table evaluation.


```javascript
// Example of evaluation weights in js/ai.js
const evaluationWeights = {
    material: 1.0,
    pieceSquareTables: 0.5,
    mobility: 0.1,
    kingSafety: 0.7,
    pawnStructure: 0.2
};
```


### Testing

The application includes a suite of tests to ensure correctness. To run the tests, open `tests.html` in your browser. The tests cover move generation, game state, and AI performance.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.