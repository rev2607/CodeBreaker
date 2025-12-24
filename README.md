# CodeBreaker

A Mastermind-style code-breaking game built with SwiftUI for iOS and macOS. Players attempt to guess a hidden four-peg color code by receiving feedback on exact and inexact matches after each attempt.

This project was developed to practice SwiftUI fundamentals, state management, and algorithm implementation. It demonstrates a complete game loop with interactive UI and visual feedback.

## Key Features

- Interactive peg selection by tapping to cycle through available colors
- Two-pass matching algorithm that correctly identifies exact and inexact matches
- Visual match indicators showing feedback for each attempt
- Scrollable history of previous attempts
- Animated transitions when submitting guesses
- Support for custom color palettes

## Architecture & Design

The app uses a simple SwiftUI architecture with value types for game logic. The `CodeBreaker` struct holds the game state, including the master code, current guess, and attempt history. The `Code` struct represents individual code sequences and handles the matching logic.

State flows from the `CodeBreaker` struct through `@State` in `CodeBreakerView`. When the user interacts with pegs or submits a guess, the view updates the game state, which triggers SwiftUI to re-render the affected views.

SwiftUI was chosen for its declarative syntax and built-in state management, which simplifies the UI code and makes the game logic easier to reason about. The framework's animation system also provides smooth transitions without additional complexity.

## Core Concepts Demonstrated

**SwiftUI:**
- `@State` property wrapper for local view state
- `ForEach` with index-based iteration
- `onTapGesture` for user interaction
- `withAnimation` for smooth state transitions
- Custom view composition with `MatchMarkers`
- `ScrollView` for managing content overflow


## Project Structure

```
CodeBreaker/
├── CodeBreakerApp.swift      # App entry point and scene configuration
├── CodeBreakerView.swift      # Main game view with UI layout and interactions
├── CodeBreaker .swift         # Game logic: CodeBreaker and Code structs
└── MatchMarkers.swift         # Custom view component for displaying match feedback
```

**CodeBreakerApp.swift** defines the app structure using the `@main` attribute and sets up the window group.

**CodeBreakerView.swift** contains the primary UI, including the master code display, current guess interface, attempt history, and the guess submission button. It handles user interactions and coordinates view updates.

**CodeBreaker .swift** implements the core game logic. The `CodeBreaker` struct manages game state, while the `Code` struct handles code generation, peg manipulation, and the matching algorithm.

**MatchMarkers.swift** is a reusable view component that visualizes match results using filled and outlined circles to represent exact and inexact matches.

## How to Run

1. Open `CodeBreaker.xcodeproj` in Xcode
2. Select a target device or simulator (iOS or macOS)
3. Build and run the project (⌘R)
