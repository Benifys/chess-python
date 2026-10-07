# Python Command-Line Chess Engine

A command-line chess engine built in Python using object-oriented programming. The project implements chess piece movement, legal move validation, board evaluation, and computer-generated moves through a text-based interface.

## Features

- Object-oriented implementation of chess pieces and board state
- Legal and pseudo-legal move generation
- Move validation and capture handling
- Check, checkmate, and stalemate detection
- Pawn promotion to queen, rook, bishop, or knight
- Move history and undo functionality
- Board position saving and loading
- Computer-generated moves
- Position evaluation based on material, piece positioning, mobility, and check status
- Adjustable engine search depth
- Hint system for suggested moves

## Technologies

- Python
- Object-Oriented Programming
- Command-Line Interface (CLI)

## Project Structure

```text
├── main.py       # Command-line interface and game controller
├── board.py      # Board state, move validation, and game rules
├── pieces.py     # Chess pieces and movement logic
├── eval.py       # Board position evaluation
├── movegen.py    # Move ordering
├── search.py     # Computer move search
├── io_utils.py   # Saving and loading positions/moves
└── tests.py      # Tests for core game functionality
```

## Running the Program

Make sure Python 3 is installed. Clone the repository and navigate to the project directory.

```bash
git clone https://github.com/benifys/chess-python.git
cd chess-python
```

Run the chess engine with:

```bash
python main.py
```

The program will display the chess board in the terminal and allow you to enter commands.

## Commands

| Command | Description |
|---|---|
| `move e2e4` | Make a move |
| `hint` | Suggest a move for the current player |
| `ai` | Let the engine make a move |
| `depth N` | Set the engine search depth |
| `side white` | Play as White |
| `side black` | Play as Black |
| `undo` | Undo the previous move |
| `new` | Start a new game |
| `save FILE` | Save the current board position |
| `load FILE` | Load a saved board position |
| `log FILE` | Save the move history |
| `board` | Display the current board |
| `auto N` | Let the engine play N plies |
| `help` | Display available commands |
| `quit` | Exit the program |

## Making Moves

Moves are entered using coordinate notation.

For example:

```text
move e2e4
```

moves the piece on `e2` to `e4`.

Moves can also be entered directly:

```text
e2e4
```

Pawn promotions use a fifth character to specify the promotion piece:

```text
e7e8q
```

The available promotion characters are:

- `q` - Queen
- `r` - Rook
- `b` - Bishop
- `n` - Knight

## Board Evaluation

The engine evaluates chess positions using several factors:

- Material value
- Piece-square positioning
- Legal move mobility
- Check status

Each piece is assigned a material value and a positional score based on its location on the board. Mobility and check status are also considered when producing the final evaluation.

## Computer Moves

The program includes a search system for selecting computer-generated moves. Legal moves are ordered using heuristics such as captures, promotions, and board positioning before positions are evaluated.

The search depth can be changed from the command line:

```text
depth 4
```

Increasing the depth allows the engine to examine positions further ahead but requires more computation.

The `hint` command can also be used to ask the engine for a suggested move:

```text
hint
```

## Saving and Loading

The current board position can be saved to a text file:

```text
save position.txt
```

A saved position can later be loaded with:

```text
load position.txt
```

Move history can also be saved:

```text
log moves.txt
```

## Testing

Run the included tests with:

```bash
python tests.py
```

The tests verify several core features, including:

- Correct legal move count from the starting position
- Making and undoing moves
- Rejection of illegal moves
- Saving and loading board positions

## Current Limitations

The project does not currently implement every special chess rule. Castling and en passant are not implemented.

## Future Improvements

- Add castling and en passant
- Improve board evaluation
- Expand automated testing
- Improve engine playing strength
- Add a graphical user interface

## Author

**Benjamin Ho**  
Electrical Engineering Student  
University of Massachusetts Amherst
