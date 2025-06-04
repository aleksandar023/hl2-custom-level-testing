# Test Plan: Custom Half-Life 2 Level

## Introduction:
This test plan outlines the manual QA process for the "Mines" section of my custom Half-Life 2 level, titled "Coast”. The goal is to verify gameplay-critical logic and ensure reliable player progression through all enemy encounters and puzzles. Priority is given to entity functionality and logical flow over visuals or performance.


## Test Objectives

* Validate the level's layout and navigation, ensuring all intended areas of the level are accessible 
* Ensure all enemy encounters and puzzles play out correctly by verifying the behaviour and placement of individual point and brush entities.
* Verify the correct placement and functionality of pickups and objects

## Scope of Testing

### Included in this phase:
* Level blockout and navigation
   * Accessibility of all playable areas
   * Prevention of out-of-bounds exploits or unintended shortcuts
   * Proper collision for world geometry and props
* Level gameplay-critical logic
   * Verification of key elements (point and brush entities) to ensure enemy encounters and puzzles work as intended:
   * Trigger volumes (e.g., trigger_once, trigger_multiple, trigger_relay).
   * NPC placement, spawn logic, and navigation.
   * Scripted sequences (e.g., animations, choreographed scenes).
   * Interactive objects (e.g., doors, buttons, key pickups).
   * Crucial sound cues tied to gameplay logic.
   * Base lighting that contributes to gameplay (visibility and guidance).


* Autosaving and level completion
   * Functionality and timing of trigger_autosave volumes.
   * Proper activation of the level completion trigger (trigger_changelevel).
*Pickups
   * Proper placement and availability of essential and non-essential weapons (crowbar, gravity gun, pistol).
   * Functionality of optional pickups (e.g., shotgun, health kits, batteries, crates).
   * Interaction logic for breakables and physics-based items.


### Excluded from this phase:
* Lighting, shadows, and visual polish
* Non-cruical sound effects, music, and voice lines
* Final environmental detail passes
* Performance optimization and FPS stability
* Art/asset review (textures, models)


## Test Strategy & Approach

Sequential Area-Based Testing
The map is divided into smaller zones labeled A1 to A9 to facilitate structured and consistent testing. A detailed top-down map is provided, showing player spawn and exit points, marked zones, enemy encounter and puzzle locations, as well as all key pickups and enemy placements. Each segment is carefully tested before moving to next one.


Event Chain Verification: Combat encounters and puzzles are grouped into named sequences made up of smaller, interdependent scripted actions. To support verification of input/output logic and flow, each event sequence is visualized using a graph diagram illustrating the order and relationship between entities.

Checklist-Driven Coverage
A comprehensive testing checklist was created, covering all logic responsible for enemy encounters, puzzles, player spawning, autosaving, and other key gameplay elements. Tests were prioritized based on priority and structured to follow the logical flow of the level. Additionally, each checklist section was mapped to a specific zone (A1–A9) , as outlined in the level map, to ensure full spatial and functional coverage.

Negative Testing: Edge case testing is performed to intentionally break gameplay logic—such as bypassing puzzles, interrupting enemy AI, or triggering entities out of sequence—to ensure the level behaves predictably under unintended conditions.

Regression testing: Re-test previously reported issues after fixes to confirm no new regressions are introduced.



## Environment and Tools

Platform: PC, Windows 10

Game Version: Half-Life 2, 
Build ID: 17324696

Map File: Level_mines.bsp
Version: v1.6

Tools used:

Valve Hammer Editor [version 4.1] - for in-editor testing
Google Sheets - for checklist creation and test tracking
draw.io – for visual event diagrams (puzzle/enemy logic flow)
Adobe photoshop - for annotated top-down map creation



Testing Aids (Console Commands):
 		
map [mapname] – to reload or jump to specific test points
sv_cheats 1 – to enable debug/testing tools
noclip – to test out-of-bounds prevention and navigation
god – for safe traversal during event tests
ai_disable / ai_enable – to control enemy behavior for isolated testing




## Deliverables
The following materials will be produced and maintained as part of the testing process:

-Design Document - A reference document outlining the rationale behind key level design decisions, including gameplay mechanics, level layout, narrative elements, environmental storytelling, and primary inspirations.

-Test Plan Document – This document outlining the objectives, scope, strategy, environment, and approach used in testing the level.

-Gameplay and Logic Checklist – A detailed checklist covering all map zones (A1–A9), scripted events, enemy encounters, puzzles, pickups, and transitions. Used to drive and document test coverage.

-Bug Report Log – A log of all identified bugs, including descriptions, reproduction steps, affected entities, map areas, and resolution status.

-Visual References:

📌 Top-down map overview with marked zones, spawn/exit points, encounter triggers, and pickups.

📌 Entity sequence diagrams (e.g., puzzle/encounter flowcharts) created with Draw.io for clarity on logic dependencies.


-Test Summary Report – A short summary of the testing outcome, major findings, and final recommendations.

## Exit Criteria

Testing is considered complete when the following conditions are met:

All enemy encounters and puzzle events have been verified to trigger and play out correctly in the intended order, with each related entity functioning as expected.
All intended areas of the level are accessible
All interactive objects (e.g., doors, buttons, breakables) are working as designed in both scripted and player-driven scenarios.
Autosaves and level transitions trigger function correctly
All previously identified issues (if any) have been retested and resolved

