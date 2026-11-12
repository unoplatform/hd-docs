---
uid: Uno.HotDesign.Themes
---

# Theme

**Theme** shows you the design system your app applies — the controls it dresses, the palette it defines, and the type scale it sets — gathered on one surface instead of scattered across the screens that happen to use them. The **Properties** panel beside it is where you change that design system: pick a seed color, a corner radius, a spacing or a typeface, and the running app takes it at once.

Your design system is the [Uno Themes](xref:Uno.Themes.Overview) theme your app merges: the `BaseTheme` that generates its palette, its type scale and its spacing and shape scales, whichever theme that is. This article calls it the design system to keep it apart from the light and dark theme your app switches between.

Everything on the surface is rendered by your running app, with your app's own resources, so what you see is your theme rather than a picture of it — change a token and the view changes with it — see [On local overrides](#on-local-overrides).

The design system's settings are offered in Theme mode only. In **Application** and **Previews** the Properties panel shows the selected element.

<!-- TODO(image): Theme mode opened on the Controls section — the Application / Previews / Theme navigation bar, the section list titled "Theme", the light and dark control panels side by side, and the Properties panel showing the design system's Shapes settings. -->

> [!NOTE]
> Theme is a preview feature and is not switched on for everyone yet. Editing the design system is a second preview feature, switched on separately, so you may have Theme mode without the settings beside it. The rest of this article assumes both are on. Where editing is off, the **Properties** panel is hidden with the other panels, and the design system's settings cannot be reached from anywhere in the designer.

## Reaching Theme mode

The **navigation bar** down the left edge of the window switches between Hot Design's modes, such as **Application** and **Previews** — see [the Get Started guide](xref:Uno.HotDesign.GetStarted.Guide#previews). Where it is available, **Theme** appears there too: the mode in which you inspect and adjust the design system the other modes are drawn with.

Choosing **Theme** shows the design system in place of the canvas. Neither your app's content nor a preview is shown behind it, and the **Toolbox** and **Elements** panels are hidden. The **Properties** panel is the one tool window that stays, showing the design system's settings beside it.

Choosing **Application** again brings your app back: the editors you had open are still open, and every tool window that was showing is showing again. What you had selected is not kept — select it again to carry on.

Hot Design remembers which mode you were in and returns you to it the next time you enter Hot Design. If Theme mode is no longer available to that app, you are returned to **Application** instead.

> [!IMPORTANT]
> Tool windows you keep in the [external tool window](xref:Uno.HotDesign.ToolbarExternalWindow) stay open while Theme is showing, but apart from **Properties** they cannot be acted on — the surface they describe is not on screen. You can always leave Theme mode from the navigation bar.

## When the Theme entry is available

The entry appears when two things are true:

- **The feature is switched on for you.**
- **Your app applies an Uno Themes theme**, merged the way its [getting-started guide](xref:Uno.Themes.Overview) shows. Referencing the package is not enough, and a theme merged through the deprecated resource-dictionary entry points does not count.

Neither stands in for the other: with no design system applied there is nothing to show, and the entry is withheld however the feature was switched on.

If the entry is missing and you expect it, check your app's log: Hot Design logs a warning when the feature is on but it found no design system to show. The check runs once per session, so restart the app after you fix your theme.

### Shown, but not editable

Theme mode needs a design system to *show*; the Properties panel needs to know where it is *declared* to edit it. When Hot Design cannot find the declaration, the settings are shown read-only and everything else in Theme mode works as usual. That is the case for:

- a design system created in **code** rather than in XAML;
- a design system that is the **root element** of its own resource-dictionary file, rather than an element inside `App.xaml` or a dictionary it merges;
- an app built with tooling that does not record where its dictionaries are declared.

In those cases the design system is changed by editing your XAML or code instead.

> [!NOTE]
> When Hot Design runs nested inside **Uno Platform Studio**, the studio provides its own way into Theme mode and Hot Design's in-app navigation bar is not shown. The design-system prerequisite still applies — the studio can switch the capability on, it cannot put a design system into the app you are designing.

## The section list

The design system is shown a facet at a time. Theme mode lists its sections down the left side, under a **Theme** title, the way the designer's other panels are titled.

Three sections are offered — **Controls**, **Colors** and **Typography** — and exactly one is shown at a time; the others take up no space at all. **Controls** is the section shown when Theme mode first opens; for the rest of the session it reopens on the section you last chose.

The list behaves like the **Previews** and **Elements** lists you already use: hovering over a row outlines it, and the chosen row is filled. A selected row stays marked as the selected one while it is hovered. None of the rows expand — no section has anything beneath it.

Drag the splitter between the list and the section it is showing to resize it. The section beside it gives up exactly what the list gains, and the width you choose is kept as you move between sections.

<!-- TODO(image): the section list with Colors selected — the filled row, and the splitter between the list and the Colors summary. -->

## Controls

The **Controls** section shows what your design system *looks like*, by rendering the controls every app has and letting your theme dress them:

- **Buttons** — three, on one row and at one height.
- **Input fields** — a `TextBox` and a `PasswordBox`, each with its header.
- **A card** — a title, supporting text, and an action.
- **Basic controls** — a `ToggleSwitch` shown both on and off, a `CheckBox` shown both checked and unchecked, and a `Slider`.
- **Status and info** — a `ProgressBar` and progress rings.

The set is made only of controls that design systems provide a style for, so nothing in it is there just to show the framework's own defaults.

The whole set is shown **twice, once in light and once in dark**, side by side, so a change can be judged against both at once instead of by toggling between them. The panels themselves are drawn on a surface Hot Design owns — the light panel in its light form, the dark panel in its dark form — while what the controls show is your theme.

Everything the theme sets is what you see: its colors, its corner radii, its fonts and its control sizes. Change a token and the summary changes with it. If the summary is taller than the window has room for, it scrolls rather than being clipped.

<!-- TODO(image): the Controls section — the BUTTONS, INPUT FIELDS, CARD, BASIC and STATUS & INFO groups, rendered in the light and the dark panel. -->

## Colors

The **Colors** section shows your palette as swatches, one per entry, each filled with the color it names.

The palette is made of **pairs**: a color, and the color anything drawn on top of it is written in. Each pair is shown as a single card of two rows — the color above, its `On…` counterpart below — and each swatch's label is written in its counterpart's color. A pair that cannot be read is therefore visible as such, instead of having to be worked out from two hex values.

Seven pairs are shown: **primary**, **primary container**, **secondary**, **secondary container**, **tertiary**, **error** and **error container**, each followed by its counterpart. What each color role is for is described in [Material Colors and Brushes](xref:Uno.Themes.Material.Colors).

Like the controls, the palette is shown twice — once in light and once in dark, side by side — and it scrolls when the window is short. Overriding one of the palette's colors in your app changes both the swatch for that color and every label written in it.

> [!NOTE]
> The section reads a Material-shaped palette. An app whose design system does not define these entries reaches Theme mode and its other sections normally, but its swatches render unfilled — the values simply are not there to show.

<!-- TODO(image): the Colors section — the seven pair cards with each label written in its counterpart's color, in the light and the dark panel. -->

## Typography

The **Typography** section lists the semantic type scale — the named roles your app writes in, from the largest display text down to the smallest label. The scale itself is described in [Design Tokens](xref:Uno.Themes.DesignTokens#typography).

Fifteen entries are grouped under the five roles they belong to, each group headed by its name:

| Group | Entries |
| --- | --- |
| Display | Display Large, Display Medium, Display Small |
| Headline | Headline Large, Headline Medium, Headline Small |
| Title | Title Large, Title Medium, Title Small |
| Body | Body Large, Body Medium, Body Small |
| Label | Label Large, Label Medium, Label Small |

Each entry's sample is set in that entry's own style, so the scale can be judged by reading it — change the style and the sample changes. Beside the sample the entry states what the style actually resolved to: the **family**, the **weight**, and the **size over the line height**, separated by bullets — for example `Roboto • Regular • 16/24 px`.

An entry whose style leaves the line height to the font states only its size. An entry your theme does not define says **Not defined by this theme** — the section still opens and the rest of the scale still reads.

Unlike the controls and the palette, the scale is listed **once** rather than once per theme: a type scale does not change between light and dark. It scrolls when the window is short.

<!-- TODO(image): the Typography section — the DISPLAY group's three rows, each sample set in its own style with its family, weight and metrics beside it. -->

## Editing the design system

Opening Theme mode selects your design system into the **[Properties](xref:Uno.HotDesign.Properties)** panel, headed by the design system's type name. The panel is pared down to the design system's own settings — there is no property search and no filter — and the rows follow the section you are looking at:

| Section | Settings offered |
| --- | --- |
| Controls | **Corner radius**, chosen from five presets from square to fully rounded; **Spacing**, set by number or by slider; **Density** |
| Colors | The **Primary**, **Secondary** and **Tertiary** seed colors, each a swatch beside its value, with a color picker in the row's [Advanced Flyout](xref:Uno.HotDesign.Properties.AdvancedFlyout) |
| Typography | The **Font family**, chosen from the same fonts every other font row offers |

Each row edits a property of your theme. What the property controls — the radius and spacing scales, the density modes, the seeds the palette is generated from, the typeface the type scale uses — is described in [Design Tokens](xref:Uno.Themes.DesignTokens) and [Seed Color Palette](xref:Uno.Themes.SeedColors).

A setting the design system's version does not carry contributes no row, and a seed that is not set reads as optional rather than empty. The rows are labelled as the design system names them — *Corner radius*, *Spacing*, *Font family* — not by their property names.

<!-- TODO(image): the Properties panel beside the Colors section — the Primary, Secondary and Tertiary seed rows, with the color picker open on one of them. -->

**Every change is applied to the running app first, then saved.** Pick a seed and the palette regenerates and the controls take the new color at once; choose a corner radius, a spacing, a density or a typeface and the controls already on screen take it. The app is not rebuilt to show the change.

Colors your app overrides keep their values — see [On local overrides](#on-local-overrides).

The value is written into the design system's declaration in your XAML — whether that is `App.xaml` or a resource dictionary it merges — so your source stays the single record of your theme.

Undo restores both the file and the running app. Consecutive changes to one setting are one undo step: pick a seed twice and one undo returns to the seed you started from. Changes to different settings are separate steps.

A setting takes a literal value only. Each row still has its **Advanced** button, and its flyout is where a setting is **Reset**, but neither a binding nor a resource can be chosen there, and no setting offers per-breakpoint responsive values.

> [!NOTE]
> The settings are read-only when Hot Design cannot find where the design system is declared — see [Shown, but not editable](#shown-but-not-editable).

While the design system is selected, **Delete** removes nothing and **Escape** leaves it selected — there is no element behind it to delete or step away from. Choosing **Application** or **Previews** in the navigation bar ends the selection: the Properties panel follows the canvas selection again, and shows **No selection** until you select an element.

## On local overrides

The summaries show your design system as your app resolves it, app-wide overrides included. The Properties panel edits the **base** theme: the seeds, scales and typeface the design system generates its resources from. Where your app overrides a generated value, the override wins, so a change you make to the base may not show in the summary — or in your app. The change is still saved; nothing in Theme mode tells you an override is masking it.

Uno Themes documents how its overrides work and which one wins: [Color Precedence](xref:Uno.Themes.SeedColors#color-precedence) for the palette, [Overriding Tokens](xref:Uno.Themes.DesignTokens#overriding-tokens) for the type scale and the spacing, shape and density scales, and [Lightweight Styling](xref:Uno.Themes.LightweightStyling) for a single resource key. If a change does not show up, check those overrides first.

## Next steps

- **[Properties](xref:Uno.HotDesign.Properties)** — the panel the design system's settings are edited in
- **[Canvas](xref:Uno.HotDesign.Canvas)** — the design surface Theme mode replaces
- **[Previews](xref:Uno.HotDesign.Previews)** — the other mode on the navigation bar
- **[Uno Themes](xref:Uno.Themes.Overview)** — the design systems Theme mode shows, and the settings it edits
- **[Resources](xref:Uno.HotDesign.Properties.Resources)** — assign a theme resource to a property from the Properties panel
- **[Troubleshooting](xref:Uno.HotDesign.Troubleshooting)** — known issues and how to resolve them
