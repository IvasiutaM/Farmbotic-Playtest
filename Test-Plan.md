# Farmbotic — Playtest Test Plan

## 1. Overview

### 1.1 Purpose

This document defines the testing strategy and methodology used to evaluate the Steam Playtest build of **Farmbotic**.

The purpose of this testing activity is to identify functional issues, reproducible bugs, usability problems, UI/UX inconsistencies, performance issues, and potential areas for improvement.

The testing is conducted from an independent tester perspective, with the goal of providing structured, reproducible, and actionable feedback.

### 1.2 Testing Objectives

The main objectives are:

* Verify that core gameplay systems behave as expected.
* Identify functional defects and unexpected behavior.
* Evaluate the usability and consistency of the user interface.
* Identify potential UX problems that may negatively affect the player experience.
* Test edge cases and unexpected player interactions.
* Observe performance and stability during gameplay.
* Verify save/load behavior and data persistence.
* Document all relevant findings using reproducible test cases and bug reports.
* Provide actionable recommendations where appropriate.
* Re-test previously identified issues when a new game build becomes available.

---

# 2. Scope

## 2.1 In Scope

The following areas are included in the testing process, depending on their availability in the current Playtest build:

### Gameplay

* Player movement and controls
* Core gameplay loop
* Player interactions
* Exploration
* Farming
* Resource gathering
* Crafting
* Construction
* Automation
* Robots
* Mining
* Combat
* Missions and progression
* NPC interactions

### Inventory and Resources

* Inventory management
* Item collection
* Item usage
* Item movement
* Resource consumption
* Resource limits
* Full-inventory behavior

### User Interface and User Experience

* HUD
* Menus
* Buttons
* Navigation
* Information presentation
* Visual feedback
* Input feedback
* Consistency between interfaces
* Discoverability
* Usability
* Accessibility-related observations

### Technical and System Behavior

* Game stability
* Crashes
* Freezes
* Loading times
* Performance
* FPS/stuttering observations
* Resolution and display modes
* Input handling
* Save/load functionality
* Data persistence
* Settings

### Exploratory Testing

Unscripted testing will also be performed to identify unexpected behaviors that may not be covered by predefined test cases.

---

## 2.2 Out of Scope

The following areas will not be considered part of the testing scope unless they become available or relevant during the Playtest:

* Multiplayer functionality
* Cooperative gameplay
* Crossplay
* Features explicitly unavailable in the current build
* Development tools or internal systems
* Unreleased content that is not accessible through the Playtest

A feature that is unavailable in the current build will not automatically be considered a defect.

---

# 3. Testing Approach

Testing will combine several approaches rather than relying exclusively on predefined test cases.

## 3.1 First-Time User Experience

The first gameplay session will initially be performed without deliberately searching for defects.

The purpose is to evaluate the game from the perspective of a player who is unfamiliar with the game.

The following aspects will be observed:

* Clarity of objectives
* Understanding of controls
* Discoverability of mechanics
* Clarity of instructions
* Ease of navigation
* Understanding of available resources
* Player feedback
* Points of confusion or uncertainty

Observations from this phase will primarily contribute to the UX/UI analysis.

---

## 3.2 Functional Testing

Functional testing will verify whether individual game systems behave according to their apparent intended functionality.

Each test case will define:

* Preconditions
* Test steps
* Expected result
* Actual result
* Test status
* Relevant evidence

Possible statuses:

* `PASS`
* `FAIL`
* `BLOCKED`
* `NOT TESTED`
* `NOT APPLICABLE`

---

## 3.3 Exploratory Testing

Exploratory testing will be used to investigate game systems beyond predefined test cases.

The tester will intentionally experiment with:

* Unusual sequences of actions
* Repeated interactions
* Rapid inputs
* Invalid actions
* Boundary conditions
* Unexpected player behavior
* Interactions between different systems

The objective is to discover defects that may not be identified through scripted testing.

---

## 3.4 Edge Case Testing

Edge cases will be tested whenever appropriate.

Examples include:

* Attempting an action without the required resources.
* Attempting an action with a full inventory.
* Repeatedly performing the same action.
* Performing an action while another action is in progress.
* Interacting from unusual positions.
* Attempting to use incompatible items.
* Testing limits of available resources.
* Interrupting actions or processes.

The expected behavior will be documented even when no defect is found.

---

## 3.5 Regression Testing

When a new game build becomes available, previously identified defects will be re-tested whenever possible.

Regression testing will determine whether:

* The issue has been fixed.
* The issue still occurs.
* The issue has changed.
* The fix introduced another problem.

Regression tests will reference the original bug report whenever possible.

---

# 4. Test Areas

Testing will be organized into the following areas:

| Area          | Description                                          |
| ------------- | ---------------------------------------------------- |
| Gameplay      | Core gameplay mechanics and player interactions      |
| Farming       | Planting, growing, harvesting and related mechanics  |
| Automation    | Robots and automated gameplay systems                |
| Crafting      | Item creation and crafting interactions              |
| Construction  | Building and placement systems                       |
| Exploration   | World exploration and environmental interactions     |
| Mining        | Mining-related mechanics and interactions            |
| Combat        | Combat mechanics, when available                     |
| Inventory     | Item management and resource handling                |
| NPCs          | NPC interactions and related systems                 |
| Missions      | Objectives, progression and task completion          |
| UI            | Visual interface and interface consistency           |
| UX            | Usability, navigation and player experience          |
| Save/Load     | Saving, loading and persistence                      |
| Settings      | Game configuration and available options             |
| Performance   | Stability, FPS, loading and stuttering               |
| Accessibility | Readability, controls and accessibility observations |

---

# 5. Test Environment

The following environment information will be recorded for each relevant testing session.

### Hardware

* CPU: 13th Gen Intel(R) Core(TM) i7-13620H
* CPU Cores: 10
* Logical Proccessors: 16
* GPU: Intel(R) UHD Graphics
* RAM: 16 GB DDR4 @ 3200 MT/s
* Storage: 477 GB NVMe SSD (Samsung MZVL8512HELU-00BTW)

### Software

* Operating System: Windows 11
* Game Version:
* Steam Build:
* Display Resolution:
* Display Mode:
* Input Method: Keyboard + Mouse

Additional configuration details will be recorded when they are relevant to reproducing an issue.

---

# 6. Test Case Management

Test cases will be stored in the `Test-Cases/` directory.

Test cases will use a unique identifier following this format:

`TC-[AREA]-[NUMBER]`

Examples:

* `TC-FARM-001`
* `TC-INV-001`
* `TC-UI-001`
* `TC-SAVE-001`

Each test case should contain:

```text
Test Case ID:
Title:
Area:
Priority:

Preconditions:

Test Steps:

Expected Result:

Actual Result:

Status:

Evidence:
```

---

# 7. Bug Reporting

Identified defects will be documented in the `Bug-Reports/` directory.

Each bug report will contain:

* Unique identifier
* Clear title
* Severity
* Priority
* Reproducibility
* Environment
* Preconditions
* Steps to reproduce
* Expected result
* Actual result
* Frequency
* Impact
* Evidence
* Workaround, when applicable

Bug identifiers will follow this format:

`BUG-[NUMBER]`

Examples:

* `BUG-001`
* `BUG-002`
* `BUG-003`

The objective is to make every reported issue as reproducible and actionable as possible.

---

# 8. Severity Classification

Severity describes the technical or gameplay impact of a defect.

| Severity | Description                                                                                                               |
| -------- | ------------------------------------------------------------------------------------------------------------------------- |
| Critical | Prevents the game or a major gameplay flow from functioning, causes severe data loss, or makes continued play impossible. |
| High     | Breaks an important feature or significantly affects gameplay.                                                            |
| Medium   | Affects functionality or usability but does not prevent continued gameplay.                                               |
| Low      | Minor issue with limited impact.                                                                                          |
| Trivial  | Cosmetic, textual, or very minor issue with negligible impact.                                                            |

Severity will be assigned based on the observed impact rather than the tester's personal preference.

---

# 9. Priority Classification

Priority describes how urgently an issue should be considered for resolution.

| Priority | Description                                                          |
| -------- | -------------------------------------------------------------------- |
| P0       | Immediate attention recommended.                                     |
| P1       | High priority; should be addressed before release when feasible.     |
| P2       | Normal priority; should be addressed as part of regular development. |
| P3       | Low priority; improvement can be deferred.                           |

Severity and priority are independent values.

For example, a minor visual problem could have high priority if it affects a highly visible or frequently used interface.

---

# 10. UX/UI Analysis

UX/UI observations will be documented separately from functional defects.

The following categories will be considered:

### UI

* Layout
* Alignment
* Button placement
* Typography
* Icons
* Visual hierarchy
* Contrast
* Consistency
* Overlapping elements
* Clipped elements
* Missing information

### UX

* Learnability
* Discoverability
* Navigation
* Feedback
* Consistency
* Cognitive load
* Number of steps required to perform actions
* Clarity of available actions
* Error prevention
* Recovery from mistakes

A UX/UI issue will not automatically be classified as a bug.

For example:

> A button may function correctly while still being positioned in a way that makes it difficult to discover or use.

---

# 11. Improvement Proposals

When appropriate, significant UX/UI observations may include a proposed improvement.

Improvement proposals will attempt to provide:

1. The current behavior.
2. The identified usability problem.
3. The potential impact on the player.
4. A proposed solution.
5. A visual prototype or mockup when useful.

Prototypes are intended as conceptual suggestions rather than definitive design requirements.

---

# 12. Evidence

Evidence may include:

* Screenshots
* Screen recordings
* Videos
* Logs
* Reproduction notes
* Visual comparisons
* UI mockups

Evidence will be linked to the relevant test case or issue whenever possible.

Sensitive or restricted development information will not be published.

---

# 13. Testing Metrics

The following metrics will be tracked throughout the Playtest:

### Test Execution

* Total test cases
* Executed test cases
* Passed test cases
* Failed test cases
* Blocked test cases

### Issues

* Total bugs
* Critical issues
* High-severity issues
* Medium-severity issues
* Low-severity issues
* UX/UI issues

### Regression

* Issues re-tested
* Issues confirmed fixed
* Issues still reproducible
* Regressions discovered

These metrics will be summarized in the final report.

---

# 14. Entry Criteria

Testing can begin when:

* The Playtest build is accessible.
* The game can be launched successfully.
* The tester can enter the game.
* The relevant testing environment has been recorded.
* Evidence capture is available.
* The testing documentation is prepared.

---

# 15. Exit Criteria

Testing for a specific build may be considered complete when:

* All planned test areas have been reviewed.
* Relevant test cases have been executed.
* Identified defects have been documented.
* Significant UX/UI observations have been documented.
* Important issues have reproducible evidence where possible.
* Regression testing has been performed when applicable.
* The final findings have been summarized.

The exit criteria do not imply that the game is defect-free.

---

# 16. Limitations

This testing project is an independent evaluation performed on a Playtest build.

Results may be affected by:

* Limited testing time
* Limited access to game content
* The temporary nature of the Playtest
* Changes between game builds
* Hardware-specific behavior
* Features that are incomplete or intentionally unavailable
* Lack of access to the development team's internal specifications

Therefore, findings represent observations from the tested build and environment rather than a definitive assessment of the final product.

---

# 17. Deliverables

The project will produce the following documentation:

* Test Plan
* Test Cases
* Bug Reports
* UX/UI Analysis
* Evidence
* Improvement Proposals
* Final QA Report

All deliverables will be maintained in this repository as the testing process progresses.

---

# 18. Testing Principles

The following principles will guide the testing process:

* **Reproducibility:** Issues should be reproducible whenever possible.
* **Objectivity:** Findings should be based on observable behavior.
* **Clarity:** Reports should be understandable without additional context.
* **Evidence:** Significant findings should be supported by appropriate evidence.
* **User perspective:** Testing should consider both system behavior and player experience.
* **Prioritization:** Issues should be evaluated according to their impact.
* **Transparency:** Limitations and assumptions will be documented.
* **Continuous testing:** Findings may be re-evaluated when new builds become available.

---

## 19. Document Status

**Status:** In Progress

**Testing Type:** Independent Playtest QA / Exploratory Testing / UX Evaluation

**Repository:** `Farmbotic-Playtest`

**Playtest Build:** To be recorded

**Testing Period:** August 30, 2026 – September 7, 2026

**Last Updated:** August 30, 2026
