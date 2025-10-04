# Web Chess Arena vs. Computer

## Summary
Web Chess Arena is a sophisticated, client-side web application that offers a compelling chess-playing experience against a formidable AI opponent. Developed using HTML, CSS, and JavaScript, this project integrates `chess.js` for robust game logic and move validation, `chessboard.js` for an interactive and visually appealing chessboard interface, and `three.js` for stunning 3D animations. The AI engine is powered by the minimax algorithm with alpha-beta pruning, ensuring a challenging and engaging game.

## Setup
To get the application running locally, follow these simple steps:

1. **Clone the repository:**
   
```bash
   git clone https://github.com/23f3001304/Web-Chess-Arena-vs-Computer.git
   cd Web-Chess-Arena-vs-Computer
   ```


2. **Run the application:**
   Since this is a static web application, no complex build process is needed. Simply open the `index.html` file in a modern web browser.

### Troubleshooting
The application may encounter errors related to Subresource Integrity (SRI) checks if the externally hosted libraries (`three.js`, `chessboard.js`, etc.) are updated on their respective CDNs. If you see errors in the browser console about failed integrity checks, you can resolve them by removing the `integrity` and `crossorigin` attributes from the `<link>` and `<script>` tags in `index.html`.

## Usage
- **Making a Move**: To make a move, click on the piece you wish to move, and then click on the target square. Legal moves will be highlighted for your convenience.
- **AI Opponent**: The AI will automatically make its move after you have played.
- **Game State**: The game state, including the current position and move history, is displayed for your reference.

## Code Explanation
The application's architecture is designed to be modular and easy to understand:

- `index.html`: Defines the structure of the web page, including the chessboard container and UI elements. It also links to all necessary external libraries and stylesheets.
- `style.css`: Contains all the styling rules for the application, ensuring a responsive and visually appealing layout.
- `main.js`: The heart of the application, this script is responsible for:
  - Initializing the chessboard using `chessboard.js`.
  - Managing the game state with `chess.js`.
  - Implementing the AI's logic, featuring the minimax algorithm with alpha-beta pruning.
  - Handling user interactions and updating the UI.

The AI's decision-making process is guided by several advanced heuristics, including:
- **Alpha-Beta Pruning**: A sophisticated optimization of the minimax algorithm that significantly speeds up the search for the best move.
- **Piece-Square Tables**: These tables provide a positional evaluation for each piece, encouraging the AI to place its pieces on strategically advantageous squares.
- **Advanced Evaluation Heuristics**: The AI's evaluation function considers various factors such as material balance, pawn structure, and king safety to make well-informed decisions, drawing inspiration from established chess engine design principles.

## License
This project is licensed under the MIT License. See the `LICENSE` file for more details.