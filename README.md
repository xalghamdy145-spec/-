# Sim Game – Respect Edition (MVP)

Unity rhythm *Sim Game* starter made for mobile (iOS/Android). 
This package includes scripts, a sample chart JSON, and a silent audio track so you can hit Play immediately.

## How to use
1. Open **Unity 2021.3+** (or 2022/2023 LTS).
2. Create a new 2D URP or 2D project.
3. Close Unity, then copy the **Assets** folder from this zip into your project (merge/replace).
4. Reopen Unity.
5. Create a new Scene:
   - Add an **AudioSource** and assign `Resources/Audio/midnight_silence.wav`.
   - Add an empty `GameObject` named `Conductor` and attach **Conductor.cs**; drag the AudioSource to its field; set `offsetMs = -30` (optional).
   - Create 4–6 lane `GameObject`s with **BoxCollider2D** each; add **LaneController.cs** and set `laneIndex` accordingly (0..5).
   - Add **InputController.cs** on a `GameObject` and assign Main Camera to `cam`, and your lanes array to `lanes`.
   - Add **ScoreManager.cs** on a `GameObject` to see logs for judgement/score.
   - Add **ChartLoader.cs** on a `GameObject`; set `chartPath = "Charts/midnight_drive_easy"` and `lanes` to your lanes; set `notePrefab` to any sprite with **Note.cs**.
   - Create a simple **Note** prefab: a Sprite (e.g., square), add **Note.cs**, set `travelTimeMs = 1200`, assign the `hitLine` (an empty Transform at the bottom of the screen), and drag its parent lane to `lane` at runtime via `LaneController.Register(note)` (handled).
6. Hit **Play** and press/click lanes when notes reach the hit line. The audio is silence (for timing test). Replace it with your music in `Resources/Audio` and update the chart JSON BPM/offset.

## Chart JSON example
See `Assets/Resources/Charts/midnight_drive_easy.json`.

## Notes
- This is an MVP; polish, prefabs, and visuals are minimal by design.
- Replace the silent audio with your own track and chart it.
- Object pooling is included but minimal; expand for production.

Enjoy! ✨
