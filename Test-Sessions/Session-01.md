# Session 01 — First-Time User Experience

## Session Information

| Field            | Details                                       |
| ---------------- | --------------------------------------------- |
| Session ID       | SESSION-01                                    |
| Date             | August 30, 2026                               |
| Game Version     | 0.5.4                                         |
| Game Mode        | Single-player                                 |
| Tutorials        | Enabled                                       |
| Testing Approach | First-Time User Experience / Natural Gameplay |
| Tester           | Independent Playtest                          |

---

## 1. Session Objective

The objective of this session was to evaluate the initial player experience of Farmbotic from the perspective of a first-time player.

The session focused on natural gameplay rather than deliberate defect hunting. Observations were collected regarding:

* Initial understanding of the game.
* Tutorial clarity.
* Gameplay progression.
* UI and navigation.
* Loading times.
* Localization.
* Resource and energy management.
* Mission clarity.
* General usability.
* Areas requiring further investigation.

No observation from this session is automatically classified as a defect. Potential issues will be investigated and reproduced during subsequent testing sessions before being reported as bugs.

---

# 2. Initial Experience

## 2.1 Main Menu

The main menu was perceived positively during the initial interaction.

The menu buttons appeared visually consistent and were positioned in familiar locations, making them easy to identify and reducing the amount of attention required to select the intended option.

**Assessment:** Positive UX observation.

---

## 2.2 Steam Store Link

The game's title/logo in the main menu functions as a link to the game's Steam store page.

During the session, the clickable area appeared to extend slightly beyond the visible logo. This resulted in an unintended interaction while attempting to interact with the surrounding interface.

**Observation:**
The clickable area may be larger than the visible UI element.

**Potential impact:**
Users may unintentionally navigate to the Steam store when attempting to interact with nearby elements.

**Follow-up:**
Verify the clickable area and determine whether the behavior is consistently reproducible.

**Current classification:** UX/UI observation.

---

# 3. Tutorial and Initial Progression

## 3.1 Initial Farming Tutorial

The first missions introduced the basic farming mechanics and provided instructions for the required actions.

During the initial progression, the game generally indicated which button should be used when introducing a new action.

**Positive observation:**
The instructional prompts were sufficiently clear to perform the introduced actions while tutorials were enabled.

---

## 3.2 Tutorial Boundaries

It was not immediately clear which missions should be considered part of the tutorial and which represented the beginning of the regular gameplay experience.

For example, the mission *"Fundamentos de la agricultura tradicional"* appeared to introduce fundamental mechanics, but it was unclear whether subsequent missions should also be considered tutorial content.

**Potential UX concern:**
The transition between guided tutorial content and normal gameplay may not be immediately apparent to a first-time player.

**Follow-up:**
Repeat relevant gameplay with tutorials disabled and evaluate whether the progression remains understandable.

---

# 4. Loading Times

Several loading transitions were observed throughout the session.

Observed approximate loading times included:

| Transition / Area            | Approx. Time |
| ---------------------------- | -----------: |
| General door/area transition |         ~6 s |
| Cave exit                    |       ~9.7 s |
| Mine entrance                |         ~4 s |
| Cave transition              |      ~8.74 s |
| Cave exit                    |      ~7.53 s |
| Farm area                    |     ~11.54 s |
| John's workshop              |         ~5 s |
| Forest → Farm                |     ~10.45 s |
| Sleeping                     |      ~4.46 s |

These measurements were collected during normal gameplay and were not performed under controlled benchmark conditions.

### Observation

Loading times appeared to vary considerably between transitions.

The longest observed transition during this session was entering the farm area, at approximately 11.54 seconds.

Because the farm is an area that the player is expected to visit frequently, longer loading times in this location may become noticeable during normal gameplay.

### Important limitation

The measurements above should not be interpreted as a definitive performance benchmark.

Only a limited number of measurements were taken, and loading times may depend on factors such as:

* Current game state.
* Area being loaded.
* System resource usage.
* Background processes.
* Asset loading.
* Previous areas visited.

### Follow-up

Perform repeated measurements of frequently used transitions and compare their average and range.

**Current classification:** Performance observation.

---

# 5. Localization

## 5.1 In-Game Text

A note encountered during the investigation of a noise presented apparent localization/formatting issues in Spanish.

The observed problems appeared to involve character and punctuation handling rather than incorrect word translation.

Examples included:

* Opening punctuation marks.
* Accented characters.
* The letter `Ñ`.
* Characters that are not part of the English alphabet.

**Evidence:** Screenshot captured during the session.

**Current classification:** Localization observation.

**Follow-up:**
Review additional in-game written materials to determine whether the issue is isolated or occurs throughout the Spanish localization.

---

## 5.2 Text Embedded in Visual Assets

Some text displayed within visual assets, such as drawings or notes, remained in English despite the surrounding game interface being localized.

**Observation:**
Localization may not currently be applied consistently to text embedded directly within visual assets.

**Follow-up:**
Determine whether these elements are intentionally left in English or represent incomplete localization.

**Current classification:** Localization observation.

---

# 6. Cave Exploration and Tutorial Progression

During the first cave-related mission, the player was able to continue exploring beyond the area required to complete the immediate objective.

The tutorial information related to mining appeared after the player had already interacted with and mined the required material.

### Observations

1. The required materials were available without an explicit indication of which tool should be used.
2. Mining-related tutorial information appeared after the mechanic had already been used.
3. The larger area beyond the immediate objective created uncertainty about whether the player was expected to continue exploring or stop at that point.

### Potential UX concern

The order and timing of tutorial information may not always align with the player's natural discovery of a mechanic.

**Follow-up:**
Evaluate whether tutorial prompts consistently appear before the player is expected to perform the associated action.

**Current classification:** UX observation.

---

# 7. Time Progression and Fainting

During the cave-related mission, in-game time progressed into the night and the player eventually fainted after leaving the cave.

The game requires the player to sleep before 2:00 AM to avoid fainting.

### Observation

This interaction raised a design question regarding how players are expected to balance mission progression with the in-game time limit when completing activities that naturally extend into the night.

The behavior itself did not prevent progression.

### Positive observation

After fainting, the player appeared directly at home and the active mission remained available.

### Design consideration

The recovery behavior is convenient because it preserves mission progression, although the resulting transition may feel somewhat disconnected from normal gameplay.

**Current classification:** Gameplay/UX observation.

**Follow-up:**
Continue playing to determine whether this situation occurs frequently and whether the time-management mechanic creates meaningful gameplay pressure or unnecessary frustration.

---

# 8. Mission and Progression Clarity

A significant point of uncertainty occurred during the mission involving John and the Farmbot.

Several aspects of the progression were unclear during the first playthrough:

* Materials collected for the repair did not appear to be removed from the player's inventory.
* The mission indicated that John would repair the Farmbot in two days, while the displayed progress remained at `0/2`.
* The purpose of some secondary missions was unclear, particularly when their displayed reward was `0`.
* A technology-related system was introduced, but its purpose and method of use were not immediately understood.
* The location of the technology-related feature was not initially obvious and was discovered through exploration rather than through a clearly remembered instruction.

### Player impact

The combination of these uncertainties made it difficult to determine the intended next step.

The session was eventually ended because progression could not be confidently continued without understanding the John/Farmbot mission.

### Important distinction

This observation does **not** establish that the mission contains a functional defect.

The current evidence indicates a potential **progression and UX clarity issue**, which requires further investigation.

**Current classification:** UX / progression observation.

**Priority for follow-up:** High.

---

# 9. Energy Management

Basic farming actions such as planting and watering consumed a noticeable amount of energy.

The energy cost felt relatively high during the early stage of the game.

### Design question

Is the current energy consumption intended to establish the game's early-game resource-management loop, or could the costs of basic farming actions be adjusted?

### Important limitation

No conclusion about game balance can be made from this session alone.

The perceived impact may change as the player progresses and obtains additional resources, upgrades, or mechanics.

**Current classification:** Design observation / open question.

**Follow-up:**
Continue playing and evaluate whether energy consumption remains restrictive as additional gameplay systems become available.

---

# 10. Resource Gathering

While uncertain about the next mission objective, additional resource-gathering activities were performed near the farm, including chopping and mining.

### Positive observation

The ability to freely perform these activities and the associated mechanics felt engaging during the session.

### Open question

The immediate purpose of some collected materials was not always apparent at this stage of progression.

**Follow-up:**
Determine when these resources become relevant to progression and whether their purpose is communicated clearly to the player.

**Current classification:** Gameplay / UX observation.

---

# 11. Sleeping

The sleeping transition took approximately 4.46 seconds.

Compared with the other loading transitions observed during the session, this transition was perceived as relatively short and did not appear particularly disruptive.

**Assessment:** Positive performance/UX observation.

---

# 12. Save and Session Termination

The game was saved normally before exiting.

No forced or unexpected termination was performed during this session.

### Planned follow-up testing

The following save-related scenarios should be tested in a future session:

1. Normal save → exit game → restart → load.
2. Save after completing important mission progress.
3. Unexpected/forced game termination.
4. Load after unexpected termination.
5. Verify persistence of player progress and relevant world state.

---

# 13. Follow-Up Testing

The following items were identified for future investigation:

### UX / Progression

* Re-test the John/Farmbot repair mission.
* Determine the intended behavior of the `0/2` progress counter.
* Determine when collected repair materials are supposed to be consumed.
* Investigate the purpose and presentation of secondary missions.
* Investigate discoverability of the technology system.
* Test tutorial clarity with `Show Tutorials` disabled.
* Investigate the timing of cave/mining tutorial information.
* Verify the Steam store link's clickable area.

### Performance

* Perform repeated loading-time measurements.
* Compare frequently visited areas.
* Measure both directions of area transitions.
* Observe whether loading times change during longer sessions.
* Monitor FPS and stuttering during gameplay.

### Localization

* Check additional Spanish text.
* Check punctuation and accented characters.
* Check occurrences of `Ñ`.
* Check text embedded in visual assets.

### Save System

* Verify normal save/load persistence.
* Test unexpected termination.
* Verify mission and world-state persistence.

### Gameplay / Design

* Continue progression to evaluate the impact of energy consumption.
* Determine the purpose of resources collected during the early game.
* Observe whether the sleep/fainting mechanic creates recurring progression issues.

---

# 14. Session Summary

The first session provided a generally positive initial impression of Farmbotic's interface and basic gameplay introduction.

The tutorial successfully communicated basic controls while instructional prompts were enabled, and several gameplay mechanics were immediately enjoyable to interact with.

The primary areas requiring further investigation were:

1. **Mission and progression clarity**, particularly around the John/Farmbot repair sequence.
2. **Loading times**, which varied considerably and were most noticeable in frequently visited areas.
3. **Spanish localization consistency**, including character formatting and text embedded in visual assets.
4. **Tutorial timing and boundaries**, particularly during cave exploration.
5. **Technology system discoverability**.
6. **Save/load behavior**, which has not yet been tested beyond a normal save and exit.

No findings from this session are classified as confirmed software defects at this stage.

Further targeted testing is required before assigning bug classifications, severity, or priority to individual observations.