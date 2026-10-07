---
uid: Uno.HotDesign.ReadOnlyMode
---

# Read-only Mode

Read-only mode opens Hot Design for looking, not editing. Use it to walk someone through an app's UI, review a design, or explore a screen without the risk of changing the project.

## What you can do

- Select elements on the canvas and in the **Elements** panel.
- Switch between **Selection** and **Interactive** mode.
- Switch the theme between light and dark, and change the form factor and zoom.
- Move between the **Application**, **Previews** and **Theme** workspaces.
- Open a preview, and open the component a preview shows.
- Read every property value, including theme properties.
- Hide an element on the canvas from the **Elements** panel.

## What is turned off

- The **Toolbox** is covered by its disabled overlay, so nothing can be dragged out of it.
- Nothing can be dragged on the canvas or within the **Elements** panel, and the margin, padding, size and spacing handles are not shown.
- Menus offer no action that adds, moves, wraps or deletes an element, and the `Delete` key does nothing.
- Property values, collection items and theme properties cannot be changed.
- Previews cannot be added, duplicated, renamed or deleted.
- **Undo** and **Redo** are hidden, and their shortcuts do nothing.

**Agent** mode and the chat stay available, but any change they would make to the app is refused.

Read-only mode does not change which Hot Design features you are licensed for. A feature you do not have stays unavailable, and a feature you do have is shown without its editing actions.

## Turning it on

Read-only mode is chosen when the app starts and stays on until the app is closed. It cannot be turned off from inside Hot Design.

### Desktop

Start the app with the `--hotdesign-read-only` argument:

```bash
dotnet run --project MyApp/MyApp.csproj -f net9.0-desktop -- --hotdesign-read-only
```

The forms `hotdesign-read-only=true` and `--hotdesign-read-only=1` are also accepted.

### WebAssembly

Add `hotdesign-read-only=true` to the page address:

```text
https://localhost:5001/?hotdesign-read-only=true
```

## Good to know

- Read-only mode protects against accidental edits. It is not a security control: anyone with the project's source can still change it outside Hot Design.
- The `hotdesign-` prefix keeps the option from clashing with an argument or query parameter your app uses for itself.
- When read-only mode is on, the app's log records it once at start-up, with where the request came from.
