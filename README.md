# ♔ SFML Chess Game ♚

A fully-featured chess game implementation in C++ using the SFML (Simple and Fast Multimedia Library) graphics framework. This project demonstrates advanced C++ programming concepts including object-oriented design, file I/O, game state management, and real-time graphics rendering.

![Chess Game](https://img.shields.io/badge/Language-C++-blue.svg)
![SFML](https://img.shields.io/badge/Library-SFML%202.6.2-green.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

---

## 📋 Table of Contents

- [Features](#-features)
- [Project Structure](#-project-structure)
- [Prerequisites](#-prerequisites)
- [Installation](#-installation)
  - [Windows](#windows)
  - [Linux](#linux)
  - [macOS](#macos)
- [Compilation & Running](#-compilation--running)
- [How to Play](#-how-to-play)
- [Architecture Overview](#-architecture-overview)
- [Module Documentation](#-module-documentation)
- [Game Logic](#-game-logic)
- [File Formats](#-file-formats)
- [Customization](#-customization)
- [Troubleshooting](#-troubleshooting)
- [Future Enhancements](#-future-enhancements)
- [Contributing](#-contributing)
- [License](#-license)

---

## ✨ Features

### Core Chess Mechanics
- ✅ **Complete Chess Rules Implementation**
  - All standard piece movements (Pawn, Rook, Knight, Bishop, Queen, King)
  - Pawn special moves (double-step from starting position, diagonal captures)
  - Path validation for sliding pieces (Rook, Bishop, Queen)
  - Check detection and validation
  - Checkmate and stalemate detection
  - Legal move verification (cannot put own king in check)

### User Interface
- 🎨 **Beautiful Graphical Interface**
  - Custom chess piece sprites
  - Board texture rendering
  - Visual square highlighting for piece selection
  - Smooth hover effects on menu buttons
  - Color-coded end game screens

### Game Features
- 💾 **Save/Load System**
  - Save game state at any time (press 'S' or via pause menu)
  - Load previously saved games from main menu
  - Automatic game state persistence
  
- 📊 **Statistics Tracking**
  - Win counter for both White and Black
  - Persistent high scores across sessions
  - Statistics display in main menu

- ⚙️ **Settings & Customization**
  - Sound toggle (on/off)
  - Theme selection (default/alternate)
  - Persistent settings storage

### Menu System
- 📱 **Complete Menu Navigation**
  - Main Menu (Start, Load, Settings, High Scores, Exit)
  - Pause Menu (Resume, Save, Exit)
  - End Game Screen (Play Again, Main Menu)
  - Settings Screen (Sound, Theme)
  - High Scores Display

---

## 📁 Project Structure

```
chess_game/
│
├── Source Files (.cpp)
│   ├── main.cpp              # Main game loop and orchestration
│   ├── board.cpp             # Board state management
│   ├── moves.cpp             # Move validation logic
│   ├── checkmate.cpp         # Check/checkmate detection
│   ├── render.cpp            # Graphics rendering
│   ├── menu.cpp              # Menu system
│   ├── ending.cpp            # End game screen
│   ├── save.cpp              # Save/load functionality
│   ├── highscores.cpp        # Statistics tracking
│   └── settings.cpp          # User preferences
│
├── Header Files (.h)
│   ├── board.h               # Board declarations
│   ├── moves.h               # Move function declarations
│   ├── checkmate.h           # Check detection declarations
│   ├── render.h              # Rendering declarations
│   ├── menu.h                # Menu declarations
│   ├── ending.h              # End screen declarations
│   ├── save.h                # Save/load declarations
│   ├── highscores.h          # Statistics declarations
│   └── settings.h            # Settings declarations
│
├── Assets
│   ├── board.png             # Chess board texture
│   └── pieces/               # Chess piece sprites
│       ├── white_pawn.png
│       ├── white_rook.png
│       ├── white_knight.png
│       ├── white_bishop.png
│       ├── white_queen.png
│       ├── white_king.png
│       ├── black_pawn.png
│       ├── black_rook.png
│       ├── black_knight.png
│       ├── black_bishop.png
│       ├── black_queen.png
│       └── black_king.png
│
├── Data Files (Auto-generated)
│   ├── savegame.txt          # Saved game state
│   ├── highscores.dat        # Win statistics
│   └── settings.cfg          # User preferences
│
├── README.md                 # This file
└── chess_game.exe            # Compiled executable (after build)
```

### File Statistics

| File | Lines of Code | Purpose |
|------|---------------|---------|
| `main.cpp` | ~180 | Game loop, event handling, state management |
| `board.cpp` | ~40 | Board initialization and state |
| `moves.cpp` | ~150 | Piece-specific move validation |
| `checkmate.cpp` | ~250 | Advanced game state detection |
| `render.cpp` | ~120 | SFML graphics rendering |
| `menu.cpp` | ~280 | Menu UI and navigation |
| `ending.cpp` | ~100 | End game screen handling |
| `save.cpp` | ~50 | File I/O for game state |
| `highscores.cpp` | ~40 | Statistics management |
| `settings.cpp` | ~30 | Configuration handling |
| **Total** | **~1,240** | Complete chess implementation |

---

## 🔧 Prerequisites

### Required Software

1. **C++ Compiler**
   - **Windows:** MinGW-w64 (GCC) or MSVC
   - **Linux:** GCC or Clang
   - **macOS:** Clang (Xcode Command Line Tools)

2. **SFML 2.6.2** (Simple and Fast Multimedia Library)
   - Download from: https://www.sfml-dev.org/download.php
   - Required modules: Graphics, Window, System, Audio

3. **Build Tools**
   - Make (optional, for makefile builds)
   - CMake (optional, for cross-platform builds)

### System Requirements

- **OS:** Windows 7+, Linux (any modern distro), macOS 10.12+
- **RAM:** 256 MB minimum
- **Disk Space:** 50 MB (including assets)
- **Display:** 800x800 minimum resolution

---

## 📥 Installation

### Windows

#### Step 1: Install MinGW-w64
```bash
# Download from: https://www.mingw-w64.org/
# Or use chocolatey:
choco install mingw
```

#### Step 2: Install SFML
1. Download SFML 2.6.2 for MinGW from https://www.sfml-dev.org/download/sfml/2.6.2/
2. Extract to `C:/SFML-2.6.2/` (or any preferred location)
3. Add SFML bin directory to PATH:
   ```
   C:/SFML-2.6.2/bin
   ```

#### Step 3: Clone/Download Project
```bash
git clone https://github.com/SENODROOM/CHESS-GAME-SFML-CPP.git
cd sfml-chess-game
```

#### Step 4: Create Assets Directory
Ensure your `assets/pieces/` folder contains all required PNG files.

---

### Linux

#### Step 1: Install SFML
**Ubuntu/Debian:**
```bash
sudo apt-get update
sudo apt-get install libsfml-dev
```

**Fedora:**
```bash
sudo dnf install SFML-devel
```

**Arch Linux:**
```bash
sudo pacman -S sfml
```

#### Step 2: Install Build Tools
```bash
sudo apt-get install build-essential g++
```

#### Step 3: Clone Project
```bash
git clone https://github.com/yourusername/sfml-chess-game.git
cd sfml-chess-game
```

---

### macOS

#### Step 1: Install Xcode Command Line Tools
```bash
xcode-select --install
```

#### Step 2: Install SFML via Homebrew
```bash
brew install sfml
```

#### Step 3: Clone Project
```bash
git clone https://github.com/yourusername/sfml-chess-game.git
cd sfml-chess-game
```

---

## 🚀 Compilation & Running

### Windows (MinGW)

```bash
# Single command compilation
g++ main.cpp board.cpp moves.cpp render.cpp menu.cpp checkmate.cpp save.cpp highscores.cpp settings.cpp ending.cpp -o chess_game \
 -I"C:/SFML-2.6.2/include" \
 -L"C:/SFML-2.6.2/lib" \
 -lsfml-graphics -lsfml-window -lsfml-system -lsfml-audio

# Run the game
./chess_game
```

**Note:** Adjust the SFML path (`C:/SFML-2.6.2/`) to match your installation directory.

**Important:** Copy SFML DLLs to the same directory as `chess_game.exe`:
```
sfml-graphics-2.dll
sfml-window-2.dll
sfml-system-2.dll
sfml-audio-2.dll
```

### Linux

```bash
# Compilation
g++ main.cpp board.cpp moves.cpp render.cpp menu.cpp checkmate.cpp save.cpp highscores.cpp settings.cpp ending.cpp -o chess_game \
 -lsfml-graphics -lsfml-window -lsfml-system -lsfml-audio

# Run the game
./chess_game
```

### macOS

```bash
# Compilation
g++ main.cpp board.cpp moves.cpp render.cpp menu.cpp checkmate.cpp save.cpp highscores.cpp settings.cpp ending.cpp -o chess_game \
 -I/usr/local/include \
 -L/usr/local/lib \
 -lsfml-graphics -lsfml-window -lsfml-system -lsfml-audio

# Run the game
./chess_game
```

### Using a Makefile (All Platforms)

Create a `Makefile`:

```makefile
# Compiler
CXX = g++

# Compiler flags
CXXFLAGS = -std=c++17 -Wall -Wextra

# SFML flags (adjust paths for your system)
SFML_INCLUDE = -I/path/to/SFML/include
SFML_LIB = -L/path/to/SFML/lib
SFML_LINKS = -lsfml-graphics -lsfml-window -lsfml-system -lsfml-audio

# Source files
SOURCES = main.cpp board.cpp moves.cpp render.cpp menu.cpp checkmate.cpp save.cpp highscores.cpp settings.cpp ending.cpp

# Output executable
TARGET = chess_game

# Build rule
$(TARGET): $(SOURCES)
    $(CXX) $(CXXFLAGS) $(SFML_INCLUDE) $(SOURCES) -o $(TARGET) $(SFML_LIB) $(SFML_LINKS)

# Clean rule
clean:
    rm -f $(TARGET)

# Run rule
run: $(TARGET)
    ./$(TARGET)
```

Then compile and run:
```bash
make
make run
```

---

## 🎮 How to Play

### Starting the Game

1. **Launch** the executable (`chess_game` or `chess_game.exe`)
2. **Main Menu** appears with the following options:
   - **Start New Game** - Begin a fresh chess match
   - **Load Game** - Resume from saved state
   - **Settings** - Configure sound and theme
   - **High Scores** - View win statistics
   - **Exit** - Close the application

### During Gameplay

#### Making Moves
1. **Click** on a piece you want to move (must be your turn)
2. The selected square will be **highlighted in yellow**
3. **Click** on the destination square
4. If the move is legal, the piece moves and turn switches
5. If illegal, the selection is cleared

#### Game Controls

| Key | Action |
|-----|--------|
| **Mouse Click** | Select piece / Make move |
| **P** | Open pause menu |
| **S** | Quick save game |
| **ESC** | Return to main menu |

#### Pause Menu (Press 'P')
- **Resume** - Continue playing
- **Save Game** - Save current state to file
- **Exit to Main Menu** - Abandon game and return to menu

### Winning the Game

The game automatically detects:
- ✅ **Checkmate** - King is in check with no legal moves
- ✅ **Stalemate** - No legal moves available but king not in check (draw)

When the game ends:
- Win is recorded in statistics
- End screen displays with options to **Play Again** or **Exit to Main Menu**

---

## 🏗️ Architecture Overview

### Program Flow

```
┌─────────────────┐
│  Program Start  │
└────────┬────────┘
         │
         ▼
┌─────────────────────────┐
│  Load Settings & Scores │
└────────┬────────────────┘
         │
         ▼
┌─────────────────┐
│   Main Menu     │◄──────────┐
└────────┬────────┘           │
         │                    │
         ▼                    │
┌─────────────────┐           │
│   Game Loop     │           │
│ (Event & Render)│           │
└────────┬────────┘           │
         │                    │
         ▼                    │
┌─────────────────┐           │
│ Move Processing │           │
└────────┬────────┘           │
         │                    │
         ▼                    │
┌─────────────────────┐       │
│ Check/Checkmate Det │       │
└────────┬────────────┘       │
         │                    │
         ▼                    │
┌─────────────────┐           │
│  End Game Screen│───────────┘
└─────────────────┘
```

### Data Flow

```cpp
// Global State (board.cpp)
char board[8][8];  // Chess board
char turn;         // 'w' or 'b'
int whiteWins;     // White victories
int blackWins;     // Black victories

// Main Loop (main.cpp)
while (window.isOpen() && inGame) {
    // 1. Handle Events
    processMouseClick();
    processKeyboard();
    
    // 2. Validate Move
    if (isMoveValid(from, to)) {
        // 3. Check for Check
        if (!isKingInCheck(currentPlayer)) {
            applyMove();
            
            // 4. Check for Checkmate
            if (isCheckmate(opponent)) {
                recordWin();
                showEndScreen();
            }
        }
    }
    
    // 5. Render
    drawBoard();
    drawPieces();
    display();
}
```

### Module Dependencies

```
main.cpp
  ├── board.cpp (data)
  ├── moves.cpp (validation)
  │   └── board.cpp
  ├── checkmate.cpp (game state)
  │   ├── board.cpp
  │   └── moves.cpp
  ├── render.cpp (graphics)
  │   └── board.cpp
  ├── menu.cpp (UI)
  │   └── settings.cpp
  ├── ending.cpp (UI)
  ├── save.cpp (persistence)
  │   └── board.cpp
  ├── highscores.cpp (statistics)
  │   └── board.cpp
  └── settings.cpp (config)
```

---

## 📚 Module Documentation

### 1. board.cpp / board.h
**Purpose:** Core data management

**Global Variables:**
```cpp
extern char board[8][8];  // 8x8 chess board
extern char turn;         // Current turn: 'w' or 'b'
extern int whiteWins;     // White win counter
extern int blackWins;     // Black win counter
```

**Functions:**
- `void initializeBoard()` - Sets up initial chess position
- `void printBoardConsole()` - Debug: prints board to console

**Board Representation:**
- **Uppercase** = White pieces (P, R, N, B, Q, K)
- **Lowercase** = Black pieces (p, r, n, b, q, k)
- **Space ' '** = Empty square
- **Row 0** = Black's back rank (top)
- **Row 7** = White's back rank (bottom)

---

### 2. moves.cpp / moves.h
**Purpose:** Move validation for all chess pieces

**Key Functions:**

```cpp
bool isMoveValid(int sr, int sc, int dr, int dc)
```
Master validation function that:
1. Checks board bounds
2. Verifies piece ownership (turn)
3. Prevents capturing own pieces
4. Delegates to piece-specific validators

**Piece-Specific Validators:**

```cpp
bool isPawnMove(int sr, int sc, int dr, int dc)
```
- Forward 1 square (or 2 from start)
- Diagonal captures only
- Different logic for white/black

```cpp
bool isRookMove(int sr, int sc, int dr, int dc)
```
- Horizontal or vertical lines
- Path must be clear

```cpp
bool isKnightMove(int sr, int sc, int dr, int dc)
```
- L-shape: 2 squares + 1 square perpendicular
- Can jump over pieces

```cpp
bool isBishopMove(int sr, int sc, int dr, int dc)
```
- Diagonal lines only
- Path must be clear

```cpp
bool isQueenMove(int sr, int sc, int dr, int dc)
```
- Combination of rook + bishop
- Any straight or diagonal line

```cpp
bool isKingMove(int sr, int sc, int dr, int dc)
```
- One square in any direction

**Helper Functions:**
```cpp
bool isInside(int r, int c)           // Bounds checking
bool isWhitePiece(char ch)            // Piece color detection
bool isBlackPiece(char ch)            // Piece color detection
bool isSameColor(char a, char b)      // Color comparison
bool isPathClear(int sr, int sc, int dr, int dc)  // Obstacle detection
```

---

### 3. checkmate.cpp / checkmate.h
**Purpose:** Advanced game state detection

**Core Functions:**

```cpp
bool isSquareAttacked(int r, int c, char attackerColor)
```
Determines if a square is under attack by checking:
1. Pawn attacks (diagonal)
2. Knight attacks (L-shapes)
3. Rook/Queen attacks (straight lines)
4. Bishop/Queen attacks (diagonals)
5. King adjacency

```cpp
bool findKing(char side, int *kr, int *kc)
```
Locates the king for a given side on the board.

```cpp
bool isKingInCheck(char side)
```
Returns true if the specified side's king is currently attacked.

```cpp
bool hasAnyLegalMove(char side)
```
**Critical function** that:
1. Iterates through all pieces of the side
2. Tries every possible destination
3. Simulates each move
4. Checks if king is still in check
5. Returns true if ANY legal move exists

```cpp
bool isCheckmate(char side)
```
Returns `isKingInCheck(side) && !hasAnyLegalMove(side)`

```cpp
bool isStalemate(char side)
```
Returns `!isKingInCheck(side) && !hasAnyLegalMove(side)`

```cpp
int getLegalKingMoves(char side, int out[16])
```
Returns array of legal king moves (for UI hints).

---

### 4. render.cpp / render.h
**Purpose:** SFML graphics rendering

**Functions:**

```cpp
void loadTextures()
```
- Loads all 12 piece sprites (6 white, 6 black)
- Loads board background texture
- Called once at startup

```cpp
void drawBoardAndPieces(sf::RenderWindow &window)
```
Main rendering function:
1. Draws board background (or colored squares if no texture)
2. Iterates through board array
3. Draws each piece sprite at calculated position
4. Scales sprites to fit squares

```cpp
void drawHighlight(sf::RenderWindow &window, int r, int c)
```
Draws semi-transparent yellow rectangle on selected square.

```cpp
std::pair<int,int> windowToBoard(sf::RenderWindow &window, sf::Vector2i mousePos)
```
Converts pixel coordinates to board indices (0-7).

**Texture Mapping:**
```cpp
static const char* pieceFiles[12] = {
    "assets/pieces/white_pawn.png",    // index 0
    "assets/pieces/white_rook.png",    // index 1
    "assets/pieces/white_knight.png",  // index 2
    "assets/pieces/white_bishop.png",  // index 3
    "assets/pieces/white_queen.png",   // index 4
    "assets/pieces/white_king.png",    // index 5
    "assets/pieces/black_pawn.png",    // index 6
    // ... etc
};
```

---

### 5. menu.cpp / menu.h
**Purpose:** Menu system and UI navigation

**Enumerations:**
```cpp
enum MenuResult {
    MENU_NONE,       // No action
    MENU_START,      // Start new game
    MENU_LOAD,       // Load saved game
    MENU_SETTINGS,   // Open settings
    MENU_HIGHSCORES, // Show statistics
    MENU_EXIT        // Exit application
};
```

**Functions:**

```cpp
MenuResult mainMenu(sf::RenderWindow &window)
```
Displays main menu with buttons:
- Start New Game
- Load Game
- Settings
- High Scores
- Exit

Features hover effects and click detection.

```cpp
MenuResult pauseMenu(sf::RenderWindow &window)
```
Displays pause menu (accessed via 'P' key):
- Resume
- Save Game
- Exit to Main Menu

```cpp
MenuResult showSettings(sf::RenderWindow &window)
```
Settings screen with toggleable options:
- Sound (on/off)
- Theme (default/alternate)

---

### 6. ending.cpp / ending.h
**Purpose:** End game screen display

**Enumerations:**
```cpp
enum GameResult {
    WHITE_WINS,   // White won by checkmate
    BLACK_WINS,   // Black won by checkmate
    DRAW,         // Draw (not fully implemented)
    STALEMATE     // Stalemate condition
};
```

**Functions:**
```cpp
bool showEndingScreen(sf::RenderWindow &window, GameResult result)
```
- Displays game result with styled text
- Shows "Play Again" and "Exit to Main Menu" buttons
- Returns `true` if player wants to play again
- Returns `false` if returning to menu

---

### 7. save.cpp / save.h
**Purpose:** Game state persistence

**Functions:**

```cpp
void saveGameToFile(const char* filename)
```
Saves to file:
1. 8 lines of 8 characters (board state)
2. Current turn ('w' or 'b')
3. White wins count
4. Black wins count

```cpp
bool loadGameFromFile(const char* filename)
```
Reads from file and restores:
- Complete board state
- Current turn
- Win statistics

Returns `false` if file doesn't exist or is corrupt.

---

### 8. highscores.cpp / highscores.h
**Purpose:** Win statistics tracking

**Functions:**

```cpp
void loadHighscores(const char* filename)
```
Loads win counters from file (or initializes to 0).

```cpp
void saveHighscores(const char* filename)
```
Writes current win statistics to file.

```cpp
void recordWin(char winner)
```
Increments the appropriate win counter ('w' or 'b').

---

### 9. settings.cpp / settings.h
**Purpose:** User preferences management

**Global Variables:**
```cpp
extern int soundOn;  // 0 = off, 1 = on
extern int theme;    // 0 = default, 1 = alternate
```

**Functions:**

```cpp
void loadSettings(const char* filename)
```
Loads settings from file (or uses defaults).

```cpp
void saveSettings(const char* filename)
```
Writes current settings to file.

---

## 🧠 Game Logic

### Move Validation Process

```
User clicks destination square
        │
        ▼
┌─────────────────────┐
│  isMoveValid()      │
│  - Check bounds     │
│  - Check turn       │
│  - Check same color │
└──────────┬──────────┘
           │
           ▼
┌──────────────────────┐
│ Piece-specific logic │
│ (isPawnMove, etc.)   │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Simulate move        │
│ (temporary)          │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ isKingInCheck()?     │
└──────────┬───────────┘
           │
     ┌─────┴─────┐
     │           │
    YES         NO
     │           │
  Undo move   Accept move
  (illegal)   Toggle turn
```

### Checkmate Detection Algorithm

```cpp
bool isCheckmate(char side) {
    if (!isKingInCheck(side)) return false;
    
    // Try all possible moves
    for (each piece of 'side') {
        for (each destination square) {
            if (isLegalMove(piece, destination)) {
                // Simulate
                makeMove();
                bool stillInCheck = isKingInCheck(side);
                undoMove();
                
                if (!stillInCheck) {
                    return false;  // Found escape!
                }
            }
        }
    }
    
    return true;  // No escape = checkmate
}
```

**Time Complexity:** O(n × m) where n = number of pieces, m = possible destinations
**Space Complexity:** O(1) - uses board array in-place

---

## 📄 File Formats

### savegame.txt
```
rnbqkbnr
pppppppp
        
        
        
        
PPPPPPPP
RNBQKBNR
w
0
0
```
- Lines 1-8: Board state (8 characters each)
- Line 9: Current turn ('w' or 'b')
- Line 10: White wins
- Line 11: Black wins

### highscores.dat
```
5
3
```
- Line 1: White wins
- Line 2: Black wins

### settings.cfg
```
1
0
```
- Line 1: Sound (0 = off, 1 = on)
- Line 2: Theme (0 = default, 1 = alternate)

---

## 🎨 Customization

### Changing Piece Sprites

Replace PNG files in `assets/pieces/` directory. Ensure:
- Images are 100x100 pixels (recommended)
- File names match exactly
- Transparent background

### Modifying Board Colors

In `render.cpp`, modify the color values:
```cpp
// Light squares
rect.setFillColor(sf::Color(235, 235, 208));

// Dark squares
rect.setFillColor(sf::Color(119, 149, 86));
```

### Adding Sound Effects

1. Include sound files in assets
2. Load in `main.cpp` or `menu.cpp`
3. Play on events (move, capture, check, etc.)

Example:
```cpp
sf::SoundBuffer buffer;
buffer.loadFromFile("assets/sounds/move.wav");
sf::Sound sound;
sound.setBuffer(buffer);
sound.play();
```

---

## 🐛 Troubleshooting

### Common Issues

#### "Failed to load font"
**Problem:** Arial font not found

**Solution (Windows):**
```cpp
// In menu.cpp, change font path to:
font.loadFromFile("C:/Windows/Fonts/arial.ttf");
```

**Solution (Linux):**
```cpp
font.loadFromFile("/usr/share/fonts/truetype/liberation/LiberationSans-Regular.ttf");
```

#### "Failed to load textures"
**Problem:** Assets folder missing or incorrect path

**Solution:**
1. Ensure `assets/pieces/` directory exists
2. Verify all 12 PNG files are present
3. Check file names match exactly (case-sensitive on Linux)

#### "Undefined reference to sf::..."
**Problem:** SFML not linked properly

**Solution:**
- Ensure `-lsfml-graphics -lsfml-window -lsfml-system -lsfml-audio` flags are present
- Check SFML library path with `-L` flag
- On Windows, verify DLLs are in same directory as executable

#### Window doesn't open
**Problem:** Missing SFML DLLs (Windows only)

**Solution:**
Copy these DLLs from `SFML-2.6.2/bin/` to your executable directory:
- sfml-graphics-2.dll
- sfml-window-2.dll
- sfml-system-2.dll
- sfml-audio-2.dll

#### Pieces don't display
**Problem:** Texture loading failed

**Solution:**
1. Check console for error messages
2. Verify assets directory structure
3. Ensure textures are valid PNG format

---

## 🚀 Future Enhancements

### Planned Features
- [ ] **En Passant** - Special pawn capture
- [ ] **Castling** - King-Rook special move
- [ ] **Pawn Promotion** - Queen promotion on reaching opposite end
- [ ] **Move History** - Display past moves with algebraic notation
- [ ] **Undo/Redo** - Take back moves
- [ ] **AI Opponent** - Single player vs computer (Minimax algorithm)
- [ ] **Timer** - Chess clock for timed games
- [ ] **Online Multiplayer** - Network play
- [ ] **3D Board** - OpenGL rendering option
- [ ] **Sound Effects** - Move, capture, check sounds
- [ ] **Themes** - Multiple board and piece themes
- [ ] **PGN Export** - Save games in standard format
- [ ] **Opening Book** - Display opening names
- [ ] **Hint System** - Suggest legal moves

### Contribution Ideas
- Improve UI/UX design
- Add animations for piece movement
- Implement chess engine for AI
- Create tutorial/help system
- Add accessibility features
- Optimize checkmate detection algorithm
- Cross-platform testing and fixes

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

### Reporting Bugs
1. Check if the issue already exists
2. Create a detailed bug report with:
   - Steps to reproduce
   - Expected vs actual behavior
   - System information (OS, compiler, SFML version)
   - Screenshots if applicable

### Submitting Changes
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)