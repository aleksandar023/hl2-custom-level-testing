# Test Plan: Custom Half-Life 2 Level

## Introduction:
This test plan outlines the manual QA process for the "The Tunnels System" section of my custom Half-Life 2 level, titled "Coast”. The goal is to verify gameplay-critical logic and ensure reliable player progression through all enemy encounters and puzzles. Priority is given to entity functionality and logical flow over visuals or performance.


## Test Objectives

* Validate the level's layout and navigation, ensuring all intended areas of the level are accessible 
* Ensure all enemy encounters and puzzles play out correctly by verifying the behaviour and placement of individual point and brush entities.
* Verify the correct placement and functionality of interactable objects

## Scope of Testing

### Included in this phase:
* **Level blockout and navigation**
   * Accessibility of all playable areas
   * Prevention of out-of-bounds exploits or unintended shortcuts
   * Proper collision for world geometry and props
* **Level gameplay-critical logic**
   * Verification of key elements (point and brush entities) to ensure enemy encounters and puzzles work as intended:
   * Trigger volumes (e.g., trigger_once, trigger_multiple, trigger_relay).
   * NPC placement, spawn logic, and navigation.
   * Scripted sequences (e.g., animations, choreographed scenes).
   * Interactive objects (e.g., doors, buttons, key pickups).
   * Crucial sound cues tied to gameplay logic.
   * Base lighting that contributes to gameplay (visibility and guidance).


* **Autosaving and level completion**
   * Functionality and timing of trigger_autosave volumes.
   * Proper activation of the level completion trigger (trigger_changelevel).
* **Pickups**
   * Proper placement and availability of essential and non-essential weapons (crowbar, gravity gun, pistol).
   * Functionality of optional pickups (e.g., shotgun, health kits, batteries, crates).
   * Interaction logic for breakables and physics-based items.


### Excluded from this phase:
* Lighting, shadows, and visual polish
* Non-crucial sound effects, music, and voice lines
* Final environmental detail passes
* Performance optimization and FPS stability
* Art/asset review (textures, models)


## Test Strategy & Approach

* **Sequential Area-Based Testing** - The map is divided into smaller zones labeled A1 to A9 to facilitate structured and consistent testing. A detailed top-down map is provided, showing player spawn and exit points, marked zones, enemy encounter and puzzle locations, as well as all key pickups and enemy placements. Each segment is carefully tested before moving to the next one.


* **Event Chain Verification** - Combat encounters and puzzles are grouped into named sequences made up of smaller, interdependent scripted actions. To support verification of input/output logic and flow, each event sequence is visualized using a graph diagram illustrating the order and relationship between entities.

* **Checklist-Driven Coverage** - A comprehensive testing checklist was created, covering all logic responsible for enemy encounters, puzzles, player spawning, autosaving, and other key gameplay elements. Tests were prioritized based on priority and structured to follow the logical flow of the level. Since I am both the creator and tester of this custom Half-Life 2 level, I have used technical naming conventions based on the in-engine structure (e.g., entity names). This approach streamlines the testing process by allowing direct reference to key logic elements without ambiguity.

Additionally, each checklist section was mapped to a specific zone (A1–A9), as outlined in the level map, to ensure full spatial and functional coverage.

* **Negative Testing** - Intentionally breaking gameplay logic, such as bypassing puzzles, interrupting enemy AI, or triggering entities out of sequence, ensuring that the level behaves predictably under unintended conditions.

* **Regression testing** - Re-test previously reported issues after fixes to confirm no new defects are introduced.


## Environment and Tools

* **Platform:** PC, Windows 10

* **Game Version:** Half-Life 2, 
  * **Build:** 9526483 

* **Map File:** Level_tunnels_system.bsp
  * **Version:** v1.6

* **Tools used:**

  * Valve Hammer Editor [version 4.1] - for in-editor testing
  * Google Sheets - for checklist creation and test tracking
  * draw.io – for visual event diagrams (puzzle/enemy logic flow)
  * Adobe Photoshop - for annotated top-down map creation
  * Nvidia app for taking screenshots and videos
  * Handbrake for compressing and trimming videos


* **Testing Aids (Console Commands):**
 		
  * map [mapname] – to reload or jump to specific test points
  * sv_cheats 1 – to enable debug/testing tools
  * noclip – to test out-of-bounds prevention and navigation
  * god – for safe traversal during event tests
  * ai_disable / ai_enable – to control enemy behaviour for isolated testing




## Deliverables
The following materials will be produced and maintained as part of the testing process:

* 📎 **[Design document](https://www.artstation.com/artwork/g8vPvZ)** - A reference document outlining the rationale behind key design decisions, including gameplay mechanics, level layout, narrative elements and primary inspiration:
  
* **Test Plan Document** – A document outlining the objectives, scope, strategy, environment and exit criteria used in testing the level.

* 📎 **[Gameplay and Logic Checklist](https://github.com/aleksandar023/hl2-custom-level-testing/blob/eb85b0661592b8e2e0afdaf15278467a1480a820/hl2_custom_level_checklist.md)** – A detailed checklist covering all map zones (A1–A9), scripted events, enemy encounters, puzzles, pickups, and transitions. Used to drive and document test coverage.

* 📎 **[Bug Report Log](https://github.com/aleksandar023/hl2-custom-level-testing/blob/main/hl2-custom-level-bugs.md)** – A log of all identified bugs, including bug summaries, reproduction steps, observed and expected results, severity, environment and attachments

* **Visual References:**

  * 📎 **[Top-down map](./images/The_Tunnels_System_Zones_Map.png)** overview with marked zones, spawn/exit points, various encounters, puzzles and pickups   

  * Entity sequence diagrams (📎 **[Part1](./images/The_Tunnels_System_Diagram_Part_1.drawio.svg)** & 📎 **[Part2](./images/The_Tunnels_System_Diagram_Part_2.drawio.svg)**) created with Draw.io for clarity on logic dependencies.

* 📎 **[Test Summary Report](https://github.com/aleksandar023/hl2-custom-level-testing/blob/main/hl2-custom-level-summary-report.md)** – A concise overview of testing outcomes, including test tasks, results, newly discovered and reopened defects, encountered issues or trends and any other relevant findings

## Exit Criteria

Testing is considered complete when the following conditions are met:

* All enemy encounters and puzzle events have been verified to trigger and play out correctly in the intended order, with each related entity functioning as expected.
* All intended areas of the level are accessible
* All interactive objects (e.g., doors, buttons, breakables) are working as designed in both scripted and player-driven scenarios.
* Autosaves and level transitions trigger function correctly
* All previously identified issues (if any) have been retested and resolved

