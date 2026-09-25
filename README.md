# Curve Designer 0.1.1

**An all-in-one curves editor toolkit for system designers and gameplay programmers.**

Minimum code boilerplate. Maximum customizability. Utilities without the spreadsheet round trip.

## Visualize the data you already have

Add `[CurveContext]` to your existing curves, arrays, or lists. Map the fields you want to see; keep your data structure.

```csharp
[CurveContext("Drop count", "Weight", X = nameof(DropEntry.count),
	Y = nameof(DropEntry.weight), PreviewMode = DiscretePreviewMode.Bars)]
public List<DropEntry> drops;
```

![Visualizing an existing collection as a bar chart](Documentation/Media/collection-preview.gif)

[Collection examples and Inspector setup](Documentation/Inspector.md).

## Build your curve library

Save, organize, search, and reuse presets instead of starting from scratch.

![Browsing and searching presets in Curve Designer's dark theme](Documentation/Media/curve-library-dark.gif)

## Keep the gameplay code simple

Shape your progression visually, then evaluate it in gameplay code. Group editing, tangents, and Undo keep iteration quick.

```csharp
[CurveContext("Level", "Required XP")]
public AnimationCurve experienceByLevel;

public float GetRequiredExperience(int level) => experienceByLevel.Evaluate(level);
```

![Dragging an XP key and adjusting its tangent handles in Unity](Documentation/Media/key-and-tangent-editing.gif)

Select several keys and move them together.

![Box-selecting two XP keys and moving the group in Unity](Documentation/Media/group-editing.gif)

Typed curves also support `Vector2` outputs, such as damage ranges. [Runtime examples](Documentation/RuntimeUseCases.md).

![Editing two-dimensional damage values in Curve Designer](Documentation/Media/damage-ranges.gif)

## Try equations before applying them

An equation evaluator inside Unity: type a formula, compare its shape, and apply the result when it fits.

![Changing equations in the full Curve Designer window](Documentation/Media/formula-preview.gif)

## Work with Excel

Copy two columns from Excel—input and value—and paste into the graph with **Ctrl/Cmd+V**. Sheet Preview keeps the numbers beside the curve and copies them back to Excel.

![Curve edits updating Sheet Preview in Unity](Documentation/Media/sheet-preview.gif)

## Put it to work

| System | Use cases |
| --- | --- |
| Progression | XP requirements, enemy health, rewards by level |
| Economy | Upgrade prices, resource costs by tier |
| Combat | Damage ranges, cooldowns, distance falloff |
| Loot | Drop-count weights, reward multipliers |
| Encounters | Spawn counts, difficulty by wave |

Light and dark Unity themes supported.

![Curve Designer in dark and light Unity themes](Documentation/Media/theme-comparison.gif)

Native-curve optimization removes unnecessary keys at your chosen sampled accuracy.

[Quick start](Documentation/QuickStart.md) · [Runtime API](Packages/com.wanderbyte.curve-designer/RuntimeEvaluation.md)

## Integration and your data

Native curves and collections stay on your objects. Typed curves use the package's runtime assembly. Your personal preset library is local to the project's `Library` folder—back it up before clearing that folder. [Details](Documentation/IntegrationAndSupport.md).

## Support and updates

Use the **bug icon** in Curve Designer to prepare, review, and save a diagnostic report with Unity/system details and optional editor-log excerpts. Share the saved report through your beta invitation channel; automatic email delivery is not configured yet. [Changelog](Packages/com.wanderbyte.curve-designer/CHANGELOG.md).

## Compatibility and license

Unity **2019.4 LTS** minimum. Other Unity versions and IL2CPP/Burst still need validation. Proprietary private beta: **testing only; no redistribution or commercial production use**. [License](Packages/com.wanderbyte.curve-designer/LICENSE.md).
