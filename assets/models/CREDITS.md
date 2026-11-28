# Models

`soldier.glb` is built from Mixamo (https://www.mixamo.com, Adobe) downloads. Mixamo characters and animations are
royalty-free for use in games and other projects (Adobe's Mixamo FAQ / General Terms); they may not be redistributed
as standalone assets.

- **Character:** "Swat Guy" (Ch15), FBX Binary in T-pose.
- **Animations:** Without Skin, 30 fps, no keyframe reduction. Locomotion clips were downloaded "In Place".

| Clip | Mixamo animation |
|---|---|
| idle | Rifle Idle |
| aim_idle | Rifle Aiming Idle |
| walk | Rifle Walk |
| run | Rifle Run |
| walk_back | Backwards Rifle Walk |
| strafe_left / strafe_right | Strafe Left / Strafe Right (rifle walk strafe) |
| crouch_idle | Rifle Kneel Idle (not used yet) |
| hit_1 | Hit Reaction (left reaction to front hit, holding a rifle) |
| hit_2 | Walking Hit Reaction (rifle) |
| death_1 / death_2 / death_3 / death_4 | Death From The Front / From The Back / From Right / From Front Headshot |
| surrender | Kneeling Down (the hands are raised in code) |
| prisoner_idle | Terrified |
| throw | Toss Grenade |

**Conversion** (`scripts/models/convert.js`):
- Scaled to 1.85 m, feet at y = 0, facing −Z.
- Material groups merged (two draw calls).
- Hip drift pinned on locomotion clips; the death slide capped at 0.8 m.
- Textures: base colour JPEG 2048 px, normal maps JPEG 1024 px.

## Women (enemy variants)

`erika.glb`, `eve.glb`, `maria.glb`: Mixamo characters "Erika Archer", "Eve By J.Gonzales" and "Maria J J Ong", FBX Binary
in T-pose, converted with `scripts/models/convert_char.js` (character only, no clips). That script rebuilds one clean
skeleton (the Erika FBX nests a copy of each bone per mesh), drops the alpha eyelash cards and bakes the model to
~1.76–1.78 m. In game they play the soldier's clips, with the hips track rescaled to each model's rest height.
