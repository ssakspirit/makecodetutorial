# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This repository contains tutorial files for Microsoft MakeCode for Minecraft Education Edition. Tutorials are step-by-step, markdown-based guides that provide interactive coding lessons in a constrained environment, serving as educational tools to teach editor functionality and block basics.

## Tutorial Structure

Tutorials use a simple two-level hierarchy:
- **Level 1 heading (`#`)**: Tutorial title (appears first)
- **Level 2 headings (`##`)**: Individual steps

### Basic Format

```markdown
# Tutorial Title

## Step 1
Step instructions here

## Step 2
More instructions
```

## Code Blocks

### 1. Template Block
The `template` block contains initial starter code loaded when the tutorial begins:

```template
agent.teleportToPlayer()
player.onTravelled(WALK, function () {
})
```

### 2. Blocks Block (Hint Code)
Blocks placed at the top define available blocks in the toolbox. When included in step hints, they provide solution examples:

```blocks
player.say(":)")
agent.teleportToPlayer()
agent.move(FORWARD, 1)
```

**Important**: When code examples are included in hints, the editor restricts toolbox selection to only blocks used in those examples.

### 3. Block Configuration
Customize toolbox block parameters:

```blockconfig.local
// Step-specific configuration
randint(-10, 10)
```

```blockconfig.global
// Tutorial-wide configuration
randint(-10, 10)
```

### 4. Code Validation
Enable validators to check student code:

```validation.global
// Tutorial-wide validation
BlocksExistValidator
```

```validation.local
// Step-specific validation
BlocksExistValidator
```

Currently supports `BlocksExistValidator` which confirms tagged blocks exist in user code.

## Step Content Guidelines

- **Caption text**: All content before the first code block or image displays in the step caption
- **Keep captions short**: Content should fit without requiring user to click to expand
- **Hints**: Remaining text, code samples, and visuals appear in expandable hint dialogs

## Step Modifiers

Add special behaviors using `@` notation after step heading:

### @showdialog
Shows content in a dialog that auto-advances (replaces deprecated `@unplugged`):

```markdown
## Step 1 @showdialog
Welcome message shown in dialog
```

### @showhint
Displays an overlay window with dramatic introductions (replaces deprecated `@fullscreen`):

```markdown
## Step 1 @showhint
Important instruction shown as overlay
```

## Activity-Based Tutorials

Enable grouped activities using metadata at document top:

```markdown
### @activities 1
```

With activities enabled, use three-level hierarchy:
- **Level 2 headings (`##`)**: Activity sections
- **Level 3 headings (`###`)**: Steps within activities

```markdown
### @activities 1

## Activity 1: Introduction
### Step 1
First step instructions

### Step 2
Second step instructions

## Activity 2: Advanced
### Step 1
Advanced step instructions
```

## Hint Macros

Create collapsible hint sections using tilde delimiters:

```markdown
~hint This content is hidden until the user clicks to expand hint~
```

## Images and Media

Embed images using standard markdown:

```markdown
![description](/static/tutorials/example.png)
```

**Requirements**:
- Max file size: 1 MB
- Max width: 800 pixels
- Formats: PNG, JPEG, GIF
- Location: Host under `./docs/static/` with URLs starting at `/static/`

## Common Block APIs for Minecraft

- **Player blocks**: `player.onTravelled()`, `player.onChat()`, `player.say()`
- **Agent blocks**: `agent.teleportToPlayer()`, `agent.move()`, `agent.turn()`, `agent.place()`, `agent.destroy()`, `agent.collectAll()`, `agent.inspect()`, `agent.detect()`, `agent.drop()`, `agent.setAssist()`
- **Control structures**: `while()`, `if/else`, `for` loops
- **Blocks API**: `blocks.place()`, `blocks.blockByName()`, `blocks.blockById()`
- **Utilities**: `randint()`, `pos()`

## Testing Tutorials

1. Use a new anonymous/incognito browser window to bypass local caching
2. Tutorial content is cached locally to reduce server interactions
3. For GitHub-hosted tutorials, create new releases to force cache clearing

## Localization

Add localized tutorials to: `_locales/[isocode]/[filename].md`

## File Structure

- `test.md` - Example tutorial file in Korean
- `.claude/settings.local.json` - Claude Code permissions for accessing makecode.com

## Best Practices

1. Keep step instructions concise and focused
2. Use code hints strategically - they restrict available blocks
3. Place `template` and global `blocks` sections at the top
4. Write descriptive step headings (e.g., "Flash all the LEDs" vs "Step 1")
5. Test tutorials in incognito mode to avoid cache issues
6. Consider activity-based structure for tutorials with logical groupings
