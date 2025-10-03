# Paint for Kids

![Paint Cover](paint_for_kids_cover.jpg)

A C++ educational drawing application designed specifically for children, featuring both drawing and interactive gaming modes. The application provides a simple, colorful interface that allows kids to create shapes and play educational games.

## 🎨 Project Overview

Paint for Kids is an interactive drawing and educational game application built using C++ and the CMU Graphics Library. The application features two main modes:

- **Draw Mode**: Create and manipulate geometric shapes
- **Play Mode**: Interactive games that help children learn about shapes and colors

## ✨ Features

### Drawing Features

- **Shape Drawing**: Rectangle, Square, Circle, Triangle, and Hexagon
- **Color Customization**: Change drawing and fill colors
- **Shape Manipulation**:
  - Select and move shapes
  - Resize shapes
  - Drag and drop functionality
- **Edit Operations**: Undo/Redo with 5-level history
- **File Operations**: Save and load drawings
- **Clear All**: Remove all shapes from canvas

### Play Mode Features

- **Pick by Shape**: Interactive game to identify and select specific shapes
- **Pick by Color**: Color-based shape identification game
- **Pick by Both**: Combined shape and color identification challenges
- **Audio Feedback**: Sound effects for user interactions (with mute option)

### Advanced Features

- **Recording System**: Record and replay drawing sessions (up to 20 operations)
- **Multiple Selection Modes**: Various ways to select and interact with shapes
- **Hidden Shape Games**: Educational hide-and-seek games with shapes
- **Audio Support**: Background sounds and feedback (can be muted)

## 🏗️ Architecture

### Core Components

#### Application Manager (`ApplicationManager.cpp/.h`)

- Central coordinator managing all application components
- Handles figure management (up to 200 figures)
- Manages user actions and interface updates
- Coordinates between drawing and playing modes

#### GUI System (`GUI/`)

- **Input Handler**: Processes mouse clicks and keyboard input
- **Output Manager**: Handles drawing operations and UI rendering
- **UI Information**: Defines interface layouts and menu items

#### Figure System (`Figures/`)

- **CFigure**: Abstract base class for all shapes
- **Concrete Shapes**: CRectangle, CSquare, CCircle, CTriangle, CHexagon
- Each shape supports: drawing, selection, movement, resizing, save/load

#### Action System (`Actions/`)

- Command pattern implementation for all user operations
- **Drawing Actions**: AddRectAction, AddCircAction, etc.
- **Edit Actions**: UndoAction, RedoAction, DeleteAction, etc.
- **File Actions**: SaveAction, LoadAction
- **Game Actions**: PickByFig, PickByFillClr, PickByBoth

### Design Patterns Used

- **Command Pattern**: All user actions implemented as Action classes
- **Factory Pattern**: Action creation based on user input
- **Observer Pattern**: Interface updates triggered by model changes
- **Polymorphism**: Shape hierarchy with virtual functions

## 🚀 Getting Started

### Prerequisites

- **Operating System**: Windows (uses Windows-specific graphics)
- **Compiler**: Microsoft Visual Studio (C++)
- **Graphics Library**: CMU Graphics Library (included)
- **Additional Libraries**: Windows API, DirectX/GDI

### Building the Project

1. **Open in Visual Studio**:

   ```
   Open PT-Project.sln in Microsoft Visual Studio
   ```

2. **Build Configuration**:

   - Ensure Windows SDK is installed
   - Set build configuration to Release or Debug
   - Build solution (Ctrl+Shift+B)

3. **Required Files**:
   - Ensure `images/` folder contains UI graphics
   - Ensure `Sounds/` folder contains audio files
   - CMU Graphics Library files must be present

### Running the Application

1. **Execute** the built application
2. **Draw Mode** (default startup):

   - Select shapes from toolbar
   - Click and drag to create shapes
   - Use color palette to change colors
   - Access file operations and edit tools

3. **Play Mode**:
   - Click "Switch to Play" button
   - Follow on-screen instructions for games
   - Use sound controls as needed

## 🎮 How to Use

### Drawing Mode

1. **Creating Shapes**:

   - Select desired shape from toolbar
   - Click and drag on canvas to create shape
   - Shape appears with current draw/fill colors

2. **Editing Shapes**:

   - Click "Select" tool, then click on a shape
   - Use "Move" to relocate shapes
   - Use "Resize" to change shape dimensions
   - Use "Delete" to remove selected shape

3. **Color Management**:

   - "Change Draw Color": Modify outline color
   - "Change Fill Color": Modify interior color
   - Colors apply to newly created shapes

4. **File Operations**:
   - "Save": Store current drawing to file
   - "Load": Open previously saved drawing
   - Files saved in custom format in `Saved/` folder

### Play Mode

1. **Shape Recognition Games**:

   - "Pick by Figure": Click on shapes of specified type
   - "Pick by Color": Click on shapes with specified color
   - "Pick by Both": Match both shape type and color

2. **Game Features**:
   - Audio feedback for correct/incorrect selections
   - Score tracking and win/lose conditions
   - Progressive difficulty levels

## 📁 File Structure

```
paint-for-kids/
├── main.cpp                    # Application entry point
├── ApplicationManager.*        # Core application management
├── DEFS.h                     # Global definitions and enums
├── Actions/                   # All user action implementations
│   ├── Action.h               # Base action class
│   ├── Add*Action.*          # Shape creation actions
│   ├── *Action.*             # Edit, file, and game actions
├── Figures/                   # Shape class hierarchy
│   ├── CFigure.*             # Abstract base figure class
│   ├── C*.*                  # Concrete shape implementations
├── GUI/                       # User interface components
│   ├── Input.*               # Input handling
│   ├── Output.*              # Drawing and rendering
│   └── UI_Info.h             # Interface definitions
├── CMUgraphicsLib/           # Graphics library
├── images/                   # UI graphics and icons
├── Sounds/                   # Audio files
└── Saved/                    # Saved drawing files
```

## 🎵 Audio Features

The application includes rich audio feedback:

- **Shape Sounds**: Each shape type has unique creation sound
- **Game Audio**: Win/lose/correct/wrong feedback sounds
- **System Sounds**: Start, end, and interaction feedback
- **Mute Option**: Toggle all audio on/off

## 💾 Save/Load Format

Drawings are saved in a custom text format containing:

- Number of figures
- For each figure: type, coordinates, colors, fill status
- Maintains all visual properties for accurate restoration

## 🎯 Educational Value

### Learning Objectives

- **Shape Recognition**: Identify basic geometric shapes
- **Color Learning**: Distinguish between different colors
- **Hand-Eye Coordination**: Mouse control and precision
- **Spatial Awareness**: Understanding position and size relationships
- **Problem Solving**: Game-based challenges

### Age Group

- **Primary Target**: Ages 4-10
- **Interface**: Simple, icon-based navigation
- **Feedback**: Immediate visual and audio responses
- **Difficulty**: Progressive complexity in games

## 🔧 Technical Details

### Dependencies

- **CMU Graphics Library**: Provides windowing and drawing primitives
- **Windows API**: System integration and file operations
- **Standard C++ Libraries**: STL containers, file I/O, strings

### Performance Considerations

- **Figure Limit**: Maximum 200 shapes per drawing
- **Undo History**: 5-level undo/redo buffer
- **Recording Limit**: 20 operations per recorded session
- **Memory Management**: Proper cleanup of dynamically allocated figures

### Known Limitations

- **Platform**: Windows-only (due to CMU Graphics Library)
- **Graphics**: 2D only, no 3D capabilities
- **File Format**: Custom format, not compatible with standard image formats
- **Resolution**: Fixed window size and coordinate system

## 🤝 Contributing

This appears to be an educational project. If you're working with this codebase:

1. **Code Style**: Follow existing C++ conventions
2. **Architecture**: Respect the Command and Factory patterns used
3. **Testing**: Test both drawing and playing modes thoroughly
4. **Documentation**: Update this README for any new features

## 📄 License

Educational project - see source files for any specific licensing information.

## 🐛 Troubleshooting

### Common Issues

1. **Build Errors**: Ensure Windows SDK and Visual Studio C++ tools are installed
2. **Missing Graphics**: Verify `images/` folder contents and paths
3. **No Sound**: Check `Sounds/` folder and Windows audio settings
4. **Save/Load Issues**: Ensure `Saved/` folder exists and has write permissions

### System Requirements

- **OS**: Windows 7 or later
- **RAM**: Minimum 512MB
- **Storage**: 50MB free space
- **Graphics**: Any DirectX-compatible graphics adapter
- **Audio**: Windows-compatible sound card (optional)

---

**Note**: This project uses the CMU Graphics Library, which provides cross-platform graphics capabilities primarily designed for educational purposes.
