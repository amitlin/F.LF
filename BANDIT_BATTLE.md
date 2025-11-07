# CPU Bandit Battle Mode

## Overview
A new game mode has been added to F.LF that features an all-CPU free-for-all battle with 8 bandit characters.

## Features
- **8 CPU Players**: All characters are controlled by AI
- **All Bandits**: Every character is a bandit
- **Free-for-All**: Each bandit is on an independent team (team 0), creating a true free-for-all battle
- **Random AI**: Each bandit gets a randomly assigned AI controller
- **Random Background**: The battle takes place on a randomly selected background

## How to Access

### Method 1: From the Main Menu
1. Launch the game normally by opening `game/game.html`
2. On the frontpage, you'll see a new button: **"CPU Bandit Battle (Free-for-All)"**
3. Click the button to start the battle

### Method 2: Direct Launch
Open `game/bandit_battle.html` in your browser to jump directly into the battle.

### Method 3: URL Parameter
Add `?bandit_battle=true` to any game URL, for example:
```
game/game.html?bandit_battle=true
```

## Controls
- Press **Esc** to exit the battle and return to the main menu
- Or click the "here" button that appears at the top of the screen

## Technical Details
- The mode automatically searches for the bandit character in the loaded character list
- Default character ID is 6 (typical bandit ID in LF2)
- The search looks for characters with "bandit" or "hunter" in their name
- Each bandit is given a unique name (Alpha, Beta, Gamma, Delta, Epsilon, Zeta, Eta, Theta)
- All bandits have team value 0, which means "Independent" in the game engine

## Code Changes
The following files were modified:
- `LF/manager.js`: Added the `start_bandit_battle()` function and UI integration
- `game/bandit_battle.html`: New file for direct access to the mode

## Customization
To modify the battle configuration, edit the `start_bandit_battle` function in `LF/manager.js`:
- Change `banditId` to use a different character
- Modify the number of players (currently 8)
- Adjust team assignments (currently all 0 for FFA)
- Change background selection (currently -1 for random)
- Modify AI difficulty settings

