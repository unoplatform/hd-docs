---
uid: Uno.HotDesign.Shortcuts
---

# Hot Design Shortcuts

This page lists all keyboard and mouse shortcuts available in the **Hot Design** experience for quick reference. You can also open it from Hot Design itself: **More** (⋯) > **Windows** > **Shortcuts**.

On macOS, use `Cmd` wherever `Ctrl` is listed.

## General Editing

| Action                | Shortcut                    |
|-----------------------|-----------------------------|
| Delete element(s)     | Delete                      |
| Undo                  | Ctrl + Z                    |
| Redo                  | Ctrl + Y or Ctrl + Shift + Z |
| Duplicate selection   | Ctrl + Drag                 |
| Multi-select elements | Ctrl + Click                |

In [read-only mode](xref:Uno.HotDesign.ReadOnlyMode), Delete, Undo and Redo do nothing.

## Element Selection & Navigation

| Action                                  | Shortcut         |
|-----------------------------------------|------------------|
| Select the element under the pointer, then cycle outward through its parents | Alt + Click |
| Select / clear multiple in tree         | Ctrl + Click     |
| Select the parent element               | Shift + Enter    |
| Edit the selected UserControl           | Ctrl + Shift + U |
| Clear the selection                     | Escape           |
| Step out of the current editor          | Escape, with nothing selected |

## Interactive Mode

| Action                                            | Shortcut         |
|---------------------------------------------------|------------------|
| Toggle Interactive mode (Selection ↔ Interactive) | Ctrl + Shift + I |

## Canvas Zoom & Pan

| Action                           | Shortcut                                 |
|----------------------------------|------------------------------------------|
| Zoom in                          | Ctrl + Mouse Wheel Up or Ctrl + `+`      |
| Zoom out                         | Ctrl + Mouse Wheel Down or Ctrl + `-`    |
| Fit content to the canvas        | Ctrl + 0                                 |
| Zoom to 100%                     | Ctrl + 1                                 |
| Zoom to 200%                     | Ctrl + 2                                 |
| Zoom to 300%                     | Ctrl + 3                                 |
| Toggle Auto-fit view             | Ctrl + 9                                 |
| Pan horizontally (when zoomed)   | Shift + Mouse Wheel                      |
| Pan vertically (when zoomed)     | Mouse Wheel                              |
| Pan any direction (when zoomed)  | Middle-click and drag                    |

## Canvas Rulers & Guides

| Action                                  | Shortcut                        |
|-----------------------------------------|---------------------------------|
| Show or hide the rulers and guides      | Ctrl + R                        |
| Show or hide the crosshair              | Ctrl + Shift + R                |
| Measure from a point (crosshair on)     | Hold Shift and move the pointer |
| Add a guide                             | Drag out of a ruler             |
| Move a guide                            | Drag the guide                  |
| Delete a guide                          | Drag it onto its ruler and release it there |

These are preview features and are off by default — see [Working on the canvas](xref:Uno.HotDesign.Canvas) for how to switch them on.

## Design Surface Size

| Action                                                  | Shortcut               |
|---------------------------------------------------------|------------------------|
| Resize the design surface to the window size            | Ctrl + Shift + 0       |
| Resize the design surface to the visible canvas size    | Ctrl + Shift + 1       |
| Cycle forward through the form factor presets           | Ctrl + Shift + `+`     |
| Cycle backward through the form factor presets          | Ctrl + Shift + `-`     |

## UI Panel Toggles

| Panel      | Shortcut          |
|------------|-------------------|
| All panels | Ctrl + Shift + A  |
| Toolbox    | Ctrl + Shift + T  |
| Elements   | Ctrl + Shift + E  |
| Properties | Ctrl + Shift + P  |
