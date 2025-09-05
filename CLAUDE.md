# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a PyQt5-based Boggle game implementation written in Python 3.12+. The application features a complete Boggle game with board generation, word validation, and multiple difficulty levels.

## Architecture

### Core Components

- **main.py**: Entry point that initializes the PyQt5 application and launches the main menu
- **homepageWindow.py**: Main menu interface with game configuration options
- **boggleGame.py**: Core game logic and UI, includes TileButton class for interactive board tiles
- **boardGen.py**: Board generation using classic Boggle dice configurations (4x4 and 5x5 boards)
- **validation.py**: Word validation using Trie data structure for efficient dictionary lookups
- **wordFinder.py**: DFS algorithm to find all valid words in a generated board
- **configWindow.py**: Game configuration interface for settings
- **analyticsWindow.py**: Game analytics and statistics tracking

### Data Structure

- **data/enable1.txt**: Dictionary file containing valid English words (~172K words)
- **colourindex.txt**: UI color scheme definitions and theming guidelines
- **playground/**: Development and testing scripts for experimenting with features

### Key Design Patterns

- Modular component design with clear separation of concerns
- Trie data structure for O(L) word validation where L is word length
- DFS with pruning for efficient word discovery
- PyQt5 signal/slot pattern for UI interactions
- Custom TileButton class extending QPushButton for game board tiles

## Development Commands

### Running the Application
```bash
cd Boggle
python main.py
# or
python3 main.py
```

### Dependencies
The project requires PyQt5. Key installed packages:
- PyQt5 (5.15.10)
- PyQtWebEngine (5.15.6)
- Standard library modules: random, os, sys

### Virtual Environment
A virtual environment is set up in `Boggle/.venv/` with Python 3.13.

## File Structure Notes

- No formal requirements.txt file exists - dependencies are managed through the virtual environment
- No test suite is currently implemented
- The playground directory contains experimental scripts for development
- Color theming is centrally defined in colourindex.txt with specific hex codes for different UI states
- Board generation uses authentic Boggle dice configurations for realistic gameplay

## Development Tips

- UI styling is handled through PyQt5 stylesheets with colors referenced from colourindex.txt
- Word validation leverages a Trie for performance - modifications should maintain this efficiency
- Board generation uses weighted dice rolling for difficulty adjustment
- The codebase follows object-oriented patterns with clear class responsibilities