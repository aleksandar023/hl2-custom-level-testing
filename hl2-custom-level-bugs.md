### 🐞 Bug Report: HL2001 [Level_tunnels_system][A8] – Zombie in the Mines control room does not react to being shot during scripred sequence

**Steps to Reproduce:**

1. Launch Launch Half-Life 2
2. Load the level using the console: Level_tunnels_system.bsp
3. Progress through the level until reaching the Elevator Puzzle section (map section A8)
4. Approach the entrance of the control room, where a zombie is thumping on the window (Note: Avoid stepping too far into the room to prevent triggering the volume that ends the sequence)
5. While standing just outside or near the doorway, shoot the zombie multiple times

**Observed Result:**
Zombie does not react when being shot while the scripted sequence is playing. The sequence is not interrupted, and the zombie does not enter the combat state.

**Expected Result:**
Zombie reacts when being shot at during the scripted sequence, entering the combat state right away.

**Severity:** Minor

**Environment:**

- Platform: PC
- Operating System: Windows 10
- Game Version: Half-Life 2, build: 9526483
- Display: 1920x1080, Fullscreen

**Attachments:**

📎 [Hl2001 The Tunnels System.mp4](./images/Hl2001_The_Tunnels_System.mp4)


---

### 🐞 Bug Report: HL2002 [Level_tunnels_system][A8] – Invisible collision pushes the player when pressing button in the Mines control room
**Steps to Reproduce:**

1. Launch Launch Half-Life 2
2. Load the level using the console: Level_tunnels_system.bsp
3. Progress through the level until reaching the Elevator Puzzle section (map section A8)
4. Enter the control room and kill the zombie
5. Locate the button near the window
6. Stand close to the button and press it


**Observed Result:**
An invisible object appears briefly upon pressing the button, pushing the player backwards slightly. The object disappears after a short moment and reappears if the button is pressed again.

**Expected Result:**
Pressing the button should not generate any invisible or obstructive collision that affects player movement.

**Severity:** Minor

**Environment:**

- Platform: PC
- Operating System: Windows 10
- Game Version: Half-Life 2, build: 9526483
- Display: 1920x1080, Fullscreen

**Attachments:**

📎 [Hl2002 The Tunnels System.mp4](./images/Hl2002_The_Tunnels_System.mp4)
