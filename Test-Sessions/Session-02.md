# SESSION-02 — Session Report

## Session Information

* **Session ID:** SESSION-02
* **Date:** 09/09/2026
* **Game:** Farmbotic
* **Game Version:** 0.5.4
* **Testing Type:** Follow-up Testing / Exploratory Testing
* **Primary Focus:** John / Farmbot mission and progression
* **Additional Focus:** Secondary missions, exploration and save persistence

---

## Session Objective

The main objective of this session was to continue from the previous testing session without repeating the initial First-Time User Experience tests.

The session focused mainly on completing the mission related to John and Farmbot, as this was the main progression point that remained unclear during SESSION-01.

Additional objectives were:

* Complete John's mission and verify how the waiting period works.
* Explore the remaining missions and their gameplay.
* Check the clarity of mission objectives and progression.
* Perform free exploration.
* Test what happens when the game is closed unexpectedly.
* Verify whether the game correctly saves mission progress.

---

## John / Farmbot Mission

The mission related to John requires waiting for a certain number of days before continuing.

During the previous session, the meaning of the `0/2` counter was unclear. During this session, it became clear that the player can advance the required days by sleeping.

This was discovered when starting the session again. The game showed the mission as `1/2`, while the character was already in bed.

After completing the required waiting period, the mission itself was relatively straightforward to complete.

### Mission Text and Character Location

One point that caused some confusion was the mission instruction to visit John, while John was located at the player's farm.

This could potentially be related to the translation or wording of the mission objective. It should be checked whether the original English text uses the same wording or if this is specific to the Spanish localization.

At this point, it is considered a **localization/wording observation**, rather than a confirmed issue.

---

## Time Progression and Sleeping

The character's sleep restriction continued to have a noticeable impact on progression.

If the player reaches 2:00 AM, the character faints. This became particularly frustrating when trying to complete objectives that require travelling between several locations.

In this session, the restriction meant that part of the route through the mine had to be completed again after fainting.

The mechanic itself appears to be intentional, but the combination of travelling, loading times, exploration and mission objectives can make it difficult to manage the available time.

This creates a situation where the player has to keep track of several things at once:

* Current mission objective.
* Location.
* Travel time.
* Energy.
* Time of day.
* Sleep deadline.

Further testing could determine whether this becomes less noticeable as the player becomes more familiar with the game.

---

## Mission Objectives and Progression Clarity

Several missions were explored during this session.

One mission instructs the player to:

> "Desbloquea tuberías de transporte en el árbol tecnológico."

The objective itself explains what needs to be unlocked, but it does not indicate where the player needs to go or how to access the technology tree.

This can be confusing, especially if the player does not remember where the technology tree is located.

A similar issue occurred with the mission that requires connecting the mining well to the warehouse. The objective was not immediately clear when first starting the mission.

These cases suggest that some objectives could benefit from additional direction or contextual information.

---

## Tower Mission and Required Materials

While progressing through the tower-related mission, a problem occurred when trying to use materials that had already been collected.

For example, the player had copper wire available, but the mission did not recognize it as an available material.

Because of this, progression through the main mission could not continue at that point.

Further investigation is required to determine whether:

* The material had to be obtained in a specific way.
* The material needed to be stored somewhere specific.
* The mission requires the material to be collected after accepting the objective.
* Or the mission simply failed to recognize an already obtained item.

This was more significant than the general mission clarity observations because it directly prevented progression.

---

## Secondary Missions

During the session, it became apparent that some secondary missions are required in order to progress with the main tower mission.

This was not immediately clear from the mission structure.

The player may initially interpret the secondary missions as optional content, but completing them can be necessary to continue the main progression.

This relationship between secondary and main missions could be communicated more clearly.

---

## Machine Instructions

While progressing through the missions, it became apparent that some machines require the player to remember how they work after the initial explanation.

### Improvement Suggestion

A possible improvement would be to include a small information or help section within each machine explaining its basic operation.

For example, a player may have learned how to use a machine during an earlier tutorial but forget the procedure after several days without playing.

Having the instructions available again would make the system more practical and reduce unnecessary frustration.

This could be especially useful for players who:

* Play for short periods of time.
* Take breaks between sessions.
* Have to remember several different machines.
* Miss or forget an explanation from the initial tutorial.

This is considered an **improvement suggestion**, not a confirmed usability defect.

---

## Unexpected Game Closure — Save Persistence Test

An unexpected game closure was performed to test the game's autosave behavior.

After restarting the game, the progress from the mission involving the connection between the mining well and the warehouse had not been preserved.

As a result, the mission had to be completed again.

This indicates that the current autosave behavior may not preserve all mission progress at the moment the game is unexpectedly closed.

Further testing would be useful to determine exactly when autosaves are triggered and which types of progression are included.

---

## Assembler Mission — Progression State Issue

A more serious issue occurred while working on the mission related to placing the Assembler.

The player went to sleep while this mission was active. During the transition, the screen remained black and the game did not continue normally.

The game had to be closed forcibly.

After restarting the game, the mission progress had not been preserved correctly.

The game returned to an earlier stage of the mission, requiring the player to unlock the Assembler again.

However, the Assembler was still physically present in the game world.

This created an inconsistent state:

* The Assembler was already placed.
* The mission indicated that the Assembler had not been completed.
* Destroying the existing Assembler and placing another one did not advance the mission.
* Restarting the game did not resolve the issue.

### Reproduction Attempt

The issue was tested again after restarting the game.

A new Assembler was placed, but the mission continued to display the same objective and did not recognize the action as completed.

The issue therefore persisted after restarting the game.

### Evidence

The following screenshots were captured during the investigation:

![Assembler mission state](image.png)

The Assembler had been placed, but the mission continued to require the same action.

![Mission remains unchanged after placing another Assembler](image-1.png)

After attempting the action again, the mission still did not update.

At the end of the session, the issue remained unresolved.

---

## Session Findings

The main findings from this session were related to **mission progression, objective clarity and save persistence**.

The John mission itself was successfully understood and completed after determining how the two-day waiting period worked.

However, several other missions presented different levels of uncertainty regarding where to go, what actions were required and whether secondary missions were mandatory for main progression.

The most significant issue found during the session was the inconsistent state of the Assembler mission after an unexpected game closure. The game preserved the placed Assembler in the world but did not preserve the corresponding mission state, leaving the player unable to progress normally.

The autosave test also showed that some mission progress was lost after an unexpected closure.

---

## Follow-Up

The following points should be investigated in future testing:

* Verify the original English wording of the John mission.
* Determine whether the tower mission correctly recognizes previously obtained materials.
* Investigate the relationship between secondary missions and main mission progression.
* Determine when autosaves occur and which mission states they preserve.
* Attempt to reproduce the Assembler mission issue from a clean save.
* Verify whether the black screen during sleep can be reproduced.
* Determine whether the Assembler mission can become permanently blocked after an unexpected closure.
* Check whether other construction/building missions can enter a similar inconsistent state.

---

## Session Summary

SESSION-02 focused primarily on progressing beyond the point reached during SESSION-01 rather than repeating the initial experience tests.

The John/Farmbot mission was successfully investigated and completed, clarifying that the required waiting days advance through sleeping.

The session also revealed several progression and clarity issues, particularly around missions that do not clearly indicate where the player should go or how different objectives are connected.

The unexpected closure test produced a more significant problem: mission progress was not always preserved, and in the case of the Assembler mission, the game world and mission state became inconsistent. This issue persisted after restarting the game and required further investigation.

Overall, the session provided more concrete findings about **progression and save-state behavior** than the first session.
