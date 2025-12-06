# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a collection of MakeCode tutorials for Minecraft Education Edition, written in Korean. The project contains multiple self-contained tutorial modules that teach basic Minecraft block coding concepts using only the built-in MakeCode blocks (no custom extensions).

## Architecture

### Tutorial Structure
Each tutorial is a standalone module in `tutorials/XX-name/` with two required files:
- `pxt.json` - MakeCode project configuration
- `tutorial.md` - Step-by-step tutorial content in MakeCode tutorial format

### Tutorial Naming Convention
Tutorials follow the pattern: `XX-descriptive-name` where XX is a two-digit number (01, 02, etc.) indicating the order.

### Tutorial Content Format
Tutorial markdown files use MakeCode-specific syntax:
- `## Introduction @unplugged` - Non-interactive intro screens
- `## Step N` - Interactive coding steps
- ` ```blocks ` - Code block examples showing expected code
- `## Complete! @unplugged` - Completion screen with extension ideas

Key MakeCode tutorial annotations:
- `@unplugged` - Marks informational steps without user interaction
- Code blocks use TypeScript-like syntax but represent visual blocks

## MakeCode Configuration (pxt.json)

Each tutorial's `pxt.json` must include:
- `name` - Unique identifier for the tutorial
- `targetVersions.target` - MakeCode version (currently "1.7.25")
- `targetVersions.targetId` - Always "minecraft"
- `supportedTargets` - Array containing ["minecraft"]
- `preferredEditor` - Always "blocksprj" (blocks editor)
- `dependencies` - Must include `"core": "*"` and `"builder": "*"`
- `files` - Array containing ["tutorial.md"]

## Minecraft MakeCode Block Categories

The tutorials use these built-in block categories:

### Player
- `player.onChat()` - Trigger code when player types chat command
- `player.say()` - Display message from player
- `player.position()` - Get player's current position

### Blocks
- `blocks.place()` - Place single block at position
- `blocks.fill()` - Fill region with blocks (Replace/Outline/Hollow modes)
- `blocks.clone()` - Copy blocks from one area to another

### Positions
- `pos(x, y, z)` - Create position coordinate
- `positions.add()` - Add offset to position

### Shapes
- `shapes.circle()` - Draw circle (specify axis: X/Y/Z)
- `shapes.line()` - Draw line between two points
- `shapes.sphere()` - Draw sphere (Replace/Outline modes)

### Mobs
- `mobs.spawn()` - Spawn mob at position

### Gameplay
- `gameplay.timeSet()` - Set time (Day/Night/Sunrise/Sunset)
- `gameplay.setWeather()` - Change weather

## Creating New Tutorials

1. Create new directory: `tutorials/XX-tutorial-name/`
2. Copy `pxt.json` from existing tutorial as template
3. Update the `name` field to unique identifier
4. Create `tutorial.md` following the established format:
   - Start with `@unplugged` introduction
   - Number steps sequentially
   - Show progressive code examples in ```blocks
   - End with `@unplugged` completion and suggestions
5. Keep tutorials focused on one core concept
6. Use only built-in MakeCode blocks (no custom extensions)

## Testing Tutorials

Tutorials are tested in Minecraft Education Edition MakeCode:
1. Open MakeCode in Minecraft Education Edition
2. Import the tutorial folder
3. Follow the tutorial steps to verify:
   - All blocks are available
   - Code examples match what students build
   - Instructions are clear and actionable

## Language

All tutorial content is in Korean. When creating or modifying tutorials:
- Use Korean for all user-facing text
- Keep technical terms in English when standard (e.g., "block", "position")
- Use informal/friendly tone appropriate for students
