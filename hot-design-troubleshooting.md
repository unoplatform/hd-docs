---
uid: Uno.HotDesign.Troubleshooting
---

# Hot Design Troubleshooting

This guide lists known issues and troubleshooting steps for **Hot Design**.
If you encounter a problem not listed here, please [file a bug report](https://github.com/unoplatform/studio/issues).

## Current limitations

These are known, intentional boundaries of the current release rather than defects — they are listed here so you know what to expect.

| Area | Limitation |
| --- | --- |
| Project style | Hot Design supports **XAML** only. C# Markup is not supported, and .NET 9 or later is required. |
| Target framework | Not available for the WinAppSDK target framework (`netX.0-windowsX.X.X`). |
| Flyouts | Editing *nested* flyouts is not supported. See [Edit Flyouts from the Canvas](xref:Uno.HotDesign.Canvas#edit-flyouts-from-the-canvas). |
| External tool window | Drag-and-drop from the Toolbox into the running app is not supported; zoom, scroll, and form factor are unavailable; and [Previews](xref:Uno.HotDesign.Previews) mode is not available — the canvas is switched back to **Application** mode. Use double-click insertion or drop onto the **Elements** tree instead. |
| Previews | A preview whose content declares an `x:Name` cannot be duplicated. Hot Design explains this and writes nothing rather than producing invalid XAML. |
| Previews | Adding and duplicating previews need the previews feature grant and a resolvable previews folder. Where either is missing — including when Hot Design runs nested inside Studio Live — the **Add** and **Duplicate** actions are hidden while browsing keeps working. |
| Previews | A `Style` added to your app's resources from **C# code** appears on the **System** tab rather than **App**, because it carries no XAML source identity and so is not editable in the designer. |
| Template properties | The **Create** / **Edit** button is disabled when the value is a template *selector*. Navigate to the individual branch from the [Scope Selector](xref:Uno.HotDesign.ScopeSelector) instead. |
| Responsive Extension | Per-breakpoint values can be a literal value or a resource, but not a **Binding** — and the Responsive toggle is disabled while the property's current value is a binding. |
| `x:Bind` static members | Only public static **properties** and **parameterless, non-void static methods** on your own (non-framework) types are offered. Static fields and constants, generic and nested declaring types, and `Task`/`ValueTask`-returning methods are not. Static bindings are `OneTime`. |

## Known issues

### All Platforms

#### A tip says the app was started without the Uno tooling

- **Description:** A tip appears beside the Hot Reload indicator saying the app is running but the developer setup is not complete, and offering the Uno Platform extension for Visual Studio, Visual Studio Code or Rider, and the Uno MCPs.
- **Cause:** The app was started directly — for example with `dotnet run` from a terminal — rather than by the Uno Platform extension for Visual Studio, Visual Studio Code or Rider, or by the Uno App MCP. A terminal hosted inside an IDE still counts as a direct start: the IDE is running, but it did not start the app.
- **Solution:**
  - Choose your IDE in the tip to open its getting started guide, then install the extension and start the app from the IDE, or
  - Choose **Setup MCPs** to open the Uno Platform MCP page and start the app through the Uno App MCP.
  - The tip is shown once and does not come back. Close it with **Not now**.
  - If you are unsure which tool the app credits with starting it, the application log says so at startup: `Application launched by Direct.` — or `VisualStudio`, `VisualStudioCode`, `Rider`, `UnoAppMcp`, or `Unknown` when the platform cannot report it.

#### Previews are missing and the build reports HDSG002

- **Description:** The **Previews** panel cannot resolve your app's previews folder, the **Add preview** action is unavailable, and the build emits warning **HDSG002**.
- **Cause:** Resolving the previews folder requires an aligned Uno SDK that sets the `HotDesignPreviewsFolder` MSBuild property. An SDK that only sets the older `HotDesignStoriesFolder` name is no longer bridged.
- **Solution:** Update your project to a current [**Uno.Sdk**](https://www.nuget.org/packages/Uno.Sdk) version.

#### External Tool Window Lost or Hidden

- **Description:** The external tool window opened but is now off-screen or minimized.
- **Cause:** The window may have been positioned outside the visible screen area or minimized.
- **Solution:**
  - Click **More** > **Windows** > **Show Tools In-App** to close the external window.
  - Then toggle it again **Show Tools In-App** to move tools back to the main view.
  - Alternatively, check your taskbar to see if the window is minimized and restore it.

#### Tools and External Window Not Syncing

- **Description:** Changes made in the app aren't reflected in the external tool window, or vice versa.
- **Cause:** Communication between the external window and main app was interrupted.
- **Solution:**
  - Check your connection status in the toolbar (connection icon).
  - If offline or disconnected, reconnect and try the action again.
  - Close the external window and reopen it by toggling: **More** > **Windows** > **Show Tools In-App**.
  - If the issue persists, restart Hot Design.

#### Native Controls Disappear on Hover

- **Description:** Native controls (such as WebView2, MediaPlayerElement, or other platform-native elements) disappear or become invisible when hovering over them with the mouse in Hot Design mode.
- **Cause:** This occurs when non-empty managed overlays (such as visual adorners shown on hover) are displayed on top of native controls. In this scenario, the native embedding clips the entire native surface (including the control itself), causing the control to become invisible.
- **Workaround:** This is a known limitation of how native content is clipped when combined with managed overlays. There is currently no direct solution except to:
  - Avoid hovering over native controls while Hot Design mode is enabled to prevent overlays from being displayed.
  - Temporarily disable Hot Design mode when working with native controls.
  - Use alternative non-native controls where possible (e.g., Skia-rendered controls).
- **Related Issue:** This is the same root cause as [unoplatform/uno#21309](https://github.com/unoplatform/uno/issues/21309).

### Linux / WSL

#### Window Maximize/Restore State Not Preserved

- **Description:** When using Hot Design on Linux or WSL, the window maximize/restore state is not preserved across sessions.
- **Cause:** The underlying windowing API (`OverlappedPresenter.State`) is not reliable on Linux/WSL and causes a native X11 error when accessed, so Hot Design skips reading it.
- **Workaround:** Window size is still tracked and preserved. Only the maximize/restore state is not remembered between sessions. You can manually maximize or restore the window each time you activate Hot Design.
- **Related Issue:** [#6234](https://github.com/unoplatform/uno.hotdesign/issues/6234)

## Contributions and Feedback

If you encounter recurring issues or specific scenarios not covered in this guide, please consider the following:

- [File a bug report](https://github.com/unoplatform/studio/issues).
- For details on how to share feedback and suggestions, see [Providing Feedback for Uno Platform Studio](xref:Uno.Platform.Studio.Feedback).

Your input matters, it helps us continuously improve the **Hot Design** experience for everyone.
