Scramble Assembly
A classic side-scrolling space shooter game written entirely in x86 Assembly language for DOS.

📋 Description
Scramble Assembly is a retro-style arcade game inspired by the classic Scramble arcade game from the 1980s. Players pilot a spaceship through three challenging phases, each with unique terrain and obstacles. The game features procedurally generated terrain, enemy AI, and a scoring system.

✨ Features
3 Unique Phases: Each phase features different terrain generation algorithms and difficulty levels

Phase 1: Yellow mountainous terrain with moderate difficulty (+10 points/second)
Phase 2: Red volcanic terrain with increased difficulty (+15 points/second)
Phase 3: Block-based brick terrain with highest difficulty (+20 points/second)
Game Mechanics:

Lives system (3 lives)
Missile firing system
Enemy generation and AI
Real-time score tracking
Countdown timer
Procedural terrain generation
Graphics:

320x200 resolution (VGA Mode 13h - 256 colors)
Custom sprite system
Animated backgrounds
Smooth scrolling terrain
🎮 Controls
(Controls need to be inferred from code - typical setup would be)

Arrow Keys: Move spaceship
Space/Ctrl: Fire missile
Enter: Select menu option
ESC: Pause/Exit
🔧 Requirements
DOS Environment or DOS emulator (DOSBox recommended)
Assembler: TASM (Turbo Assembler) or MASM (Microsoft Macro Assembler)
Linker: TLINK or equivalent
VGA-compatible display adapter
🚀 Compilation and Execution
Using TASM:
bash
tasm Game.asm
tlink Game.obj
Game.exe
Using MASM:
bash
masm Game.asm;
link Game.obj;
Game.exe
Using DOSBox:
Mount the directory containing the game files
Navigate to the directory
Compile using the commands above
Run Game.exe
🎯 Game Mechanics
Scoring System
Phase 1: 10 points per second survived
Phase 2: 15 points per second survived
Phase 3: 20 points per second survived
Additional points for destroying enemies
Lives System
Start with 3 lives
Lives displayed as ship icons in the HUD
Game over when all lives are lost
Phases
Each phase lasts 60 seconds (1200 frames at ~60 FPS). Successfully completing all three phases results in victory.

🏗️ Technical Details
Architecture
Model: Small memory model (. model small)
Stack Size: 256 bytes
Video Mode: 0x13 (320x200, 256 colors)
Frame Rate: Approximately 60 FPS
Key Components
Terrain Generation:

Phase 1 & 2: Sine-wave based procedural generation
Phase 3: Tile-based block system with variable heights
Sprite System:

Custom sprite rendering functions
Transparency support
Multiple sprite sizes (7x19, 13x29, 24x16)
Game Loop:

Frame-based timing using BIOS timer interrupts
Entity update system
Collision detection
Input handling
HUD System:

Score display with leading zeros
Timer display (MM:SS format)
Lives indicator with graphical icons
📁 Code Structure
Code
Game.txt (Assembly Source)
├── Data Section
│   ├── Title and menu strings
│   ├── Sprite definitions
│   ├── Terrain tables
│   └── Game variables
└── Code Section
    ├── String rendering (escreve_string)
    ├── Terrain generation (render_terreno_gen, render_terreno_fase3)
    ├── Sprite rendering (pinta_7x19, pinta_bloco_fase3)
    ├── HUD system (desenha_score, desenha_tempo, desenha_vidas)
    ├── Timer management (timer_tick, tempo_to_str)
    └── Game logic (entity management, collision detection)
🎨 Assets
All graphics are defined as byte arrays in the data section:

nave (ship): 13x29 pixels
meteoro (meteor): 13x29 pixels
nave_menu: 7x19 pixels (used for lives icons)
bloco3_1, bloco3_2: 24x16 pixels (terrain blocks)
