# ♔ Chess Engine - Multi-Paradigm Integration Project

**A fully functional chess game demonstrating seamless integration of Logic, Functional, and Object-Oriented Programming paradigms.**

**Team Members:** Chandler Silk, Ryan Wood 

**Course:** CS 396 - Northern Arizona University

---

## 📋 Project Overview

This chess engine showcases how three distinct programming paradigms can work together to create a sophisticated application. Each language contributes its unique strengths:

- **Prolog (Logic Programming)** - Encodes chess rules declaratively, validates moves, and detects check/checkmate
- **C++ (Object-Oriented Programming)** - Manages game state, orchestrates components, and provides user interface
- **Scheme (Functional Programming)** - Implements AI decision-making using minimax algorithm with alpha-beta pruning

---

## 🎯 Key Features

✅ **Complete Chess Rule Implementation**
- All standard piece movements (pawn, rook, knight, bishop, queen, king)
- Legal move validation (prevents moving into check)
- Check and checkmate detection

✅ **Beautiful User Interface**
- Unicode chess piece symbols (♔ ♕ ♖ ♗ ♘ ♙)
- Professional box-drawing board display
- Clear move notation and status updates
- Intuitive command-line interface

✅ **Intelligent AI Opponent**
- Minimax algorithm with alpha-beta pruning
- Position evaluation (material, piece placement, king safety)
- Legal move generation via Prolog integration

✅ **Multi-Language Integration**
- Subprocess communication between C++, Prolog, and Scheme
- Unified board representation across all languages

---

## 🏗️ Architecture

### System Overview

```
┌─────────────────────────────────────────┐
│         C++ Game Engine                 │
│  • Main game loop                       │
│  • Board state management               │
│  • User input handling                  │
│  • Language orchestration               │
└─────────────────────────────────────────┘
         │                    │
         ▼                    ▼
┌──────────────┐      ┌──────────────┐
│   PROLOG     │      │   SCHEME     │
│              │      │              │
│ • Move rules │      │ • Minimax AI │
│ • Validation │◄─────┤ • Evaluation │
│ • Check/mate │      │ • Best move  │
└──────────────┘      └──────────────┘
```

### Data Flow

**Human Turn:**
1. User enters move (e.g., "e2 e4")
2. C++ parses input and validates format
3. C++ calls Prolog to verify move legality
4. If legal, C++ updates board state
5. C++ checks for check/checkmate via Prolog

**AI Turn:**
1. C++ requests best move from Scheme
2. C++ provides legal moves from Prolog to Scheme
3. Scheme evaluates positions using minimax
4. Scheme returns chosen move to C++
5. C++ validates and executes move

---

## 📁 Project Structure

```
chess-engine/
├── src/
│   ├── cpp/
│   │   ├── Board.h              # Board representation & display
│   │   ├── Board.cpp            # Board implementation
│   │   ├── Game.h               # Game loop logic
│   │   ├── Game.cpp             # Game implementation
│   │   ├── PrologInterface.h    # Prolog communication
│   │   ├── PrologInterface.cpp  # Subprocess to Prolog
│   │   ├── SchemeInterface.h    # Scheme communication
│   │   ├── SchemeInterface.cpp  # Subprocess to Scheme
│   │   └── main.cpp             # Entry point
│   │
│   ├── prolog/
│   │   ├── board_state.pl       # Board representation
│   │   ├── piece_moves.pl       # Movement rules
│   │   ├── move_execution.pl    # Board updates
│   │   └── check_detection.pl   # Check/checkmate logic
│   │
│   └── scheme/
│       └── ai.rkt               # Minimax AI implementation
│
├── README.md
└── chess_game                   # Compiled executable
```

---

## 🚀 Installation & Setup

### Prerequisites

- **C++ Compiler:** g++ with C++11 support or later
- **SWI-Prolog:** Version 9.0+ ([swi-prolog.org](https://www.swi-prolog.org))
- **Racket:** Latest version ([racket-lang.org](https://racket-lang.org))

### macOS Installation

```bash
# Install dependencies
brew install swi-prolog racket

# Clone repository
git clone https://github.com/yourusername/chess-engine.git
cd chess-engine

# Compile
cd src/cpp
g++ -std=c++11 Board.cpp PrologInterface.cpp SchemeInterface.cpp Game.cpp main.cpp -o chess_game

# Run
./chess_game
```

### Linux Installation

```bash
# Ubuntu/Debian
sudo apt-get update
sudo apt-get install swi-prolog racket g++

# Compile and run
cd src/cpp
g++ -std=c++11 Board.cpp PrologInterface.cpp SchemeInterface.cpp Game.cpp main.cpp -o chess_game
./chess_game
```

### Windows Installation

1. Download and install [SWI-Prolog](https://www.swi-prolog.org/download/stable)
2. Download and install [Racket](https://racket-lang.org/download/)
3. Install MinGW or Visual Studio for C++ compilation
4. Open terminal in `src/cpp` directory
5. Compile: `g++ -std=c++11 *.cpp -o chess_game.exe`
6. Run: `chess_game.exe`

---

## 🎮 How to Play

### Starting the Game

```bash
cd src/cpp
./chess_game
```

### Controls

Enter moves using algebraic notation:
- **Format:** `source destination` (e.g., `e2 e4`)
- **Alternative:** `sourcedestination` (e.g., `e2e4`)

**Examples:**
```
e2 e4    # Move pawn from e2 to e4
g1 f3    # Move knight from g1 to f3
b8 c6    # Move knight from b8 to c6
d1 h5    # Move queen from d1 to h5
```

- **Exit Program:** `quit` or `exit`

## 😁 Conclusion

We are happy to present this project for submission and welcome all feedback and questions. Please feel free to contact us with the information below and thank you for checking out the project!

## 📧 Contact

For questions or collaboration:
- **Ryan Wood** - [GitHub](https://github.com/ryanwood)
- **Project Repository** - [Chess Engine](https://github.com/yourusername/chess-engine)

---
