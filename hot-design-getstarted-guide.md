---
uid: Uno.HotDesign.GetStarted.Guide
---

# Getting Started with Hot Design<sup>®</sup>

**Hot Design<sup>®</sup>** is the next-generation runtime Visual Designer for cross-platform .NET applications, transforming your live, running app into a real-time Designer.

This guide provides the steps to set up Hot Design and introduces its key features and visual design capabilities, helping you start creating and refining user interfaces efficiently and intuitively.

## Set Up Your Environment for Hot Design

[!include[hd-important-info](includes/hd-important-info.md)]

> [!IMPORTANT]
> If you're new to developing with Uno Platform, make sure to set up your environment by [following our getting started guide](xref:Uno.GetStarted).

To start using **Hot Design**, ensure you are signed in with your Uno Platform account. Follow [these instructions](xref:Uno.GetStarted.Licensing) to register, activate your license, and sign in.

### Upgrading Existing Applications

Hot Design requires **Uno.Sdk 6.0 or later** (we recommend our newer versions to get the most out of the latest Hot Design features), so you’ll need to update your project to the [latest **Uno.Sdk** version](https://www.nuget.org/packages/Uno.Sdk). For detailed steps, see our [migration guide](xref:Uno.Development.MigratingFromPreviousReleases).

If you’re coming from **Uno.Sdk 5.4 or lower**, note that `EnableHotReload()` in *App.xaml.cs* has been deprecated. Replace it with `UseStudio()` to keep Hot Reload working.

Once you’ve updated your project and **[signed in with your Uno Platform account](xref:Uno.GetStarted.Licensing)**, you can access **Hot Design** by clicking the **flame** icon in the diagnostics overlay that appears over your app.

<p align="center">
  <img src="Assets/enter-hot-design-mode.png" alt="Hot Design flame icon to enter design mode" />
</p>

## Hot Design® Agent

**New in Uno Platform Studio 2.0 is the Hot Design® Agent**. An AI-powered assistant that enables rapid UX/UI creation and enhancement within your application. It leverages data contexts and live previews to help developers design, refine, and interact with user interfaces in real time, using deep knowledge of Uno Platform and your running app to simplify cross-platform .NET design.

To get started with **Hot Design® Agent**, jump to the [Hot Design® Agent](xref:Uno.HotDesign.Agent) page.

![Hot Design Agent Panels Highlighted](Assets/hot-design-agent-view.png)

## Hot Design® Core Tool Panels

Once in Hot Design, your running app becomes an interactive canvas.
Hot Design offers an intuitive interface for designing and interacting with your app. This enables you to seamlessly create, edit, and refine your app's user interface in real-time, streamlining the design process for maximum efficiency and simplicity.

![Hot Design Core Tool Panels Highlighted](Assets/hot-design-design-view.png)

Here are the tool panels available on the interactive canvas:

### Toolbox

On the upper-left side, the **[Toolbox](xref:Uno.HotDesign.Toolbox)** panel provides a categorized list of available controls you can use in your application, including custom and third-party UI controls. It features a search bar for quickly finding specific controls, which you can drag and drop directly onto the canvas or the **[Elements](xref:Uno.HotDesign.Elements)** panel for easy integration into your design.

[➜ Learn more about the Toolbox panel](xref:Uno.HotDesign.Toolbox)

### Elements

Below the **[Toolbox](xref:Uno.HotDesign.Toolbox)**, the **[Elements](xref:Uno.HotDesign.Elements)** panel displays the hierarchical structure of your app. It represents the visual tree of your app, allowing you to select and organize elements. Clicking on an element in this panel highlights it on the canvas for detailed modifications.

[➜ Learn more about the Elements panel](xref:Uno.HotDesign.Elements)

### Canvas

The main **[Canvas](xref:Uno.HotDesign.Canvas)** in the center of the interface represents your running app. It is an interactive area where you can visually design and interact with the user interface. You can select controls, see their outlines, and preview any changes made to the layout or properties.

[➜ Learn more about the interactive Canvas](xref:Uno.HotDesign.Canvas)

### Properties

The **[Properties](xref:Uno.HotDesign.Properties)** panel, located on the right side of the interactive canvas, displays the attributes of the currently selected element on the canvas. By default, it highlights **Smart** properties, prioritizing the most commonly adjusted settings for the element. If you need access to all available properties, you can switch to the **All** view.

This panel also allows you to search for specific properties and make adjustments directly, such as modifying styles, layouts, appearances, data bindings, resources, responsiveness, and interactions, to customize your UI elements effectively.

[➜ Learn more about the Properties panel](xref:Uno.HotDesign.Properties)

### Toolbar

<p align="center">
  <img src="Assets/hot-design-toolbar.png" alt="Hot Design Toolbar" Height=100/>
</p>

Located at the top of the interactive canvas, the **Toolbar** streamlines your design workflow by providing quick access to essential actions and tools, such as:

- <img src="Assets/toolbar-hot-design-enter-icon.png" alt="Enter Hot Design Toolbar flame icon" height=30  />  Entering **Hot Design** mode.

- <img src="Assets/toolbar-hot-design-exit-icon.png" alt="Leave Hot Design Toolbar flame icon" height=30  />  Leaving **Hot Design** mode.

- <img src="Assets/hot-design-design-mode-toggle.png" alt="Toggle design mode icon" height=30 />  Toggling between **Design** and **Agent** mode.

- <img src="Assets/toolbar-play.png" alt="Hot Design Toolbar play icon" height=30  /><img src="Assets/toolbar-pause.png" alt="Hot Design Toolbar pause icon" height=30  />  Playing with the live running app to test functionality and pausing to return to adjusting properties, layout, and other design aspects without leaving the interactive designer.

- <img src="Assets/toolbar-undo.png" alt="Hot Design Toolbar undo icon" height=30  /><img src="Assets/toolbar-redo.png" alt="Hot Design Toolbar redo icon" height=30  />   Undoing and redoing changes.

- <img src="Assets/toolbar-designer-settings-form-factor-icon.png" alt="Hot Design Toolbar form factor icon" height=30  />  Changing the form factor of the app to test different screen sizes.

- <img src="Assets/toolbar-light-theme.png" alt="Hot Design Toolbar light theme icon" height=30  /><img src="Assets/toolbar-dark-theme.png" alt="Hot Design Toolbar dark theme icon" height=30  />   Switching between light and dark themes.

- <img src="Assets/toolbar-connection-status.png" alt="Hot Design Toolbar connection status icon" height=30  />  Viewing the connection status and the latest updates from **Hot Reload**.

- <img src="Assets/toolbar-more-options.png" alt="Hot Design Toolbar more options icon" height=30  />  More options, including showing or hiding the various tool panels, providing flexibility in customizing your design workspace.

[➜ Learn more about the Toolbar](xref:Uno.HotDesign.Toolbar)

## Using Hot Design

### Selecting Elements

You can select controls on the app's current screen by simply clicking on them. A visual adorner (blue border) appears around the selected elements, clearly indicating their boundaries. The type, height, and width of the selected element are displayed below the adorner for easy reference.

<p align="center">
  <img src="Assets/canvas-select-single-item.png" alt="Selecting a single item on the main canvas" />
</p>

You can also click on controls in the **Elements** panel. This provides an alternative to clicking directly on the canvas, making it easier to precisely select small elements or their containers.

To select multiple elements, hold down the `Ctrl` key while clicking. This enables you to view and edit shared properties in the **Properties** panel.

<p align="center">
  <img src="Assets/canvas-select-multiple-items.png" alt="Selecting multiple items on the main canvas" />
</p>

### Placing and Deleting Elements

You can add controls to your app by dragging them from the **Toolbox** onto the canvas, or directly into the **Elements** panel to position them within a specific hierarchy.

![Dragging item from Toolbox into the Elements panel](Assets/toolbox-drag.gif)

To delete a control, right-click on it either in the canvas or the **Elements** panel and select the delete option.

<p align="center">
  <img src="Assets/delete-elements.png" alt="Delete an element from the Elements panel" />
</p>

### Setting Properties

The **Properties** panel displays the current values of a control's properties, which you can modify in several ways. Examples include:

- **Changing a property value**, such as the **Text** property of a `TextBlock` control:

    ![Text property of a TextBlock control](Assets/properties-view-text-property.png)

- **Adjusting the alignment** of a control:

    ![Control alignment example](Assets/properties-view-alignment-property.png)

- **Using the autosuggest box** to set a property, such as the **Background** property of a control:

    ![Background property with autosuggest](Assets/properties-view-autosuggest-property.png)

To the right of each property value is the **Advanced** button, which provides information on how the value is defined. For example:

- ![None](Assets/properties-view-advcd-button-none.png) indicates that nothing is set.
- ![XAML](Assets/properties-view-advcd-button-xaml.png) indicates a **Literal**/**XAML** value is set.
- ![Binding](Assets/properties-view-advcd-button-binding.png) indicates a **Binding** is set.
- ![Resource](Assets/properties-view-advcd-button-resource.png) indicates a **Resource** is set.
- ![Mixed Responsive](Assets/properties-view-advcd-button-mixed-responsive.png) indicates **Mixed Responsive** values are set using the Responsive Extension.

Clicking the **Advanced** button opens a flyout with three settings for each property: **Value**, **Binding**, or **Resource**.

![Three options for property setting and reset button](Assets/properties-view-button-flyout.png)

> [!TIP]
> To quickly clear a property's value, click the **Reset** button. Cleared properties behave as though they weren't specified in the original XAML file.

If a property is not set, it will appear similar to this:

![Unset property](Assets/properties-view-text-empty.png)

### Changing the Form Factor

The **Toolbar** provides the ability to change the form factor of your app within Hot Design, represented by the following icon:

<p align="center">
<img src="Assets/toolbar-form-factor.png" alt="Hot Design Toolbar form factor icon" height=50 />
</p>

The height and width of your running app will dynamically adjust to match the selected form factor. You can also specify a custom height and width for precise testing.

<p align="center">
<img src="Assets/form-factor-and-zoom-flyout.png" alt="Form factor and zoom level flyout" />
</p>

At the bottom of the flyout, you can view and adjust the current zoom level. Modifying this setting dynamically scales Hot Design's view of your app, making it easier to fine-tune your design.

### Toggling Theme

The **Toolbar** includes a feature to toggle between your app's light and dark themes. This also updates the Hot Design layout to match the selected theme. Use this feature to validate your app's theme-sensitive styles and ensure proper responsiveness to theme changes.

<p align="center">
<img src="Assets/hot-design-light-theme.png" alt="Example Hot Design with Light Theme" height=300 /><img src="Assets/hot-design-dark-theme.png" alt="Example Hot Design with Dark Theme" height=300 />
</p>

### Interacting with the Canvas

You can interact with the canvas using standard design-surface navigation shortcuts that let you zoom, pan, and scroll while working in Hot Design.

For a complete reference of all keyboard and mouse shortcuts, see [Hot Design Shortcuts](xref:Uno.HotDesign.Shortcuts).

### Next Step

Follow the [Create a Counter App with Hot Design<sup>®</sup>](xref:Uno.HotDesign.GetStarted.CounterTutorial) step-by-step tutorial on getting started with Hot Design to apply what you’ve learned.
