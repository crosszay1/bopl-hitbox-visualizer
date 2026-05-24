# bopl battle hitbox visualizer
A mod for bopl battle which draws lines around hitboxes. made by Jo912345.

# Build
Before building, set up the required game references:

1. Install **Bopl Battle**.
2. Update DLL reference paths in `/home/runner/work/bopl-hitbox-visualizer/bopl-hitbox-visualizer/HitBoxVisualizerPlugin.csproj` if your game is not installed at:
   - `C:\Program Files (x86)\Steam\steamapps\common\Bopl Battle\BoplBattle_Data\Managed\...`
3. Place a publicized `Assembly-CSharp-publicized.dll` at:
   - `../__local game assemblies/Assembly-CSharp-publicized.dll` (relative to this repository root).

Then run from the repository root:

```bash
dotnet build HitBoxVisualizerPlugin.sln
```

# Test
From the repository root:

```bash
dotnet test HitBoxVisualizerPlugin.sln
```

If you see errors like missing `BoplFixedMath`, `Vec2`, `DPhysicsBox`, `DPhysicsCircle`, or `DetPhysics`, your game DLL references (step 2/3) are not set correctly.

# Notes
- As of version 3.0.0, rectangular hitboxes are now always drawn 100% accurately. In old versions the drawn hitbox edge extended half of the line thickness past the real hitbox edge, and the corners didn't quite connect.
- Circular hitboxes are and always were drawn accurately, no matter the line thickness.
- Shapes that are multi-colored are internally marked as active, and black and white if internally marked as disabled. (assuming a default color config).
- As of version 3.0.0, line colors can be modified in the config file.
- You can enable `Output Settings > consoleOutputMode` in the config to print active hitboxes as `ObjectType, x, y` in the BepInEx console/log instead of drawing them. Use `consoleOutputIntervalSeconds` to control print rate.

# Credits
- Programming:
  - Jo912345 (me)
- playtesting:
  - Jo912345 (me)
  - [Caty1 on youtube](https://www.youtube.com/@Caty15)
  - [Kopflos on youtube](https://www.youtube.com/channel/UCFSR0grPylj3dJkm-QbW0pw)
