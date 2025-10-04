# Web Chess Arena

## Summary

Web Chess Arena is a static web application that allows users to play chess against a computer opponent directly in their browser. This project is built with HTML, CSS, and JavaScript, and it leverages the powerful `chess.js` library for game logic and `chessboard.js` for rendering the board. The application is designed to be simple, intuitive, and responsive, providing a seamless chess-playing experience without the need for a backend server.

## Setup

To run this application locally, follow these steps:

1.  **Clone the repository:**
    
```bash
    git clone https://github.com/23f3001304/Web-Chess-Arena-vs-Computer.git
    cd Web-Chess-Arena-vs-Computer
    ```


2.  **No dependencies to install:**
    This project uses client-side libraries that are included via a Content Delivery Network (CDN), so there are no additional installation steps required.

3.  **Open the application:**
    Open the `index.html` file in your preferred web browser.

    *Note on the piece image loading issue:* The original HTML snippet had an incomplete URL for the chessboard stylesheet, which caused the piece images not to load. This has been corrected in the code to use the complete and correct CDN link for `chessboard-js`.

## Usage

*   **Playing the Game:** To move a piece, you can either drag and drop it to a valid square or click on the piece to see its legal moves and then click on the destination square.
*   **Game Controls:** The interface includes controls to start a new game, undo moves, and analyze the game.
*   **AI Opponent:** The computer opponent will automatically make its move after you have played your turn. The AI's strength is determined by a minimax search algorithm with alpha-beta pruning.

## Code Explanation

The application is structured into three main parts: HTML for the structure, CSS for styling, and JavaScript for the game's logic and interactivity.

*   **`index.html`**: This file contains the basic structure of the web page, including the chessboard container and user interface elements. It also includes the necessary CDN links for the `chess.js` and `chessboard.js` libraries.
*   **`style.css`**: This file provides the styling for the application, ensuring a clean and responsive layout.
*   **`main.js`**: This is the core JavaScript file that handles the game's logic. It initializes the chessboard using `chessboard.js` and manages the game state with `chess.js`. It also implements the AI opponent's logic, which is based on the minimax algorithm to calculate the best move.

The application relies on the following key libraries:

*   **`chess.js`**: A powerful JavaScript library for chess move generation, validation, and game state management.
*   **`chessboard.js`**: A flexible library for rendering an interactive and customizable chessboard.

The AI's intelligence is derived from several evaluation heuristics, including:

*   **Alpha-Beta Pruning**: An optimization technique for the minimax algorithm that reduces the number of nodes evaluated in the search tree.
*   **Piece-Square Tables**: These tables assign scores to each piece based on its position on the board, encouraging strategic placement.
*   **Evaluation Heuristics**: The AI considers material advantage, piece mobility, king safety, and pawn structure to evaluate board positions, as described in chess programming research.

## License

This project is licensed under the **MIT License**. You can find the full license text in the `LICENSE` file in the repository.