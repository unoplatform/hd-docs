---
uid: Uno.HotDesign.Overview
---

# Hot Design<sup>®</sup> Overview

[!include[hd-important-info](includes/hd-important-info.md)]

Welcome to **Hot Design<sup>®</sup>**, a next-generation runtime visual designer for cross-platform .NET applications!

> [!Video https://www.youtube-nocookie.com/embed/fODrUH0zno0]

## What is Hot Design?

**Hot Design** transforms your live, running app into a real-time visual designer that works with any IDE on any OS. It allows you to make UI changes on the fly without restarting your app or losing state, while seamlessly synchronizing your XAML code and visual designs.

In addition, [Hot Reload](xref:Uno.Features.HotReload) works seamlessly with **Hot Design**, allowing you to see UI changes instantly without rebuilding your app. This boosts productivity, reduces iteration time, and provides real-time feedback for both visual and functional tweaks in your UI. Hot Reload also includes a visual indicator to help you monitor changes as you develop, further enhancing your workflow.

**Hot Design** is part of **Uno Platform Studio**, an AI-native productivity suite for building enterprise-grade, cross-platform .NET applications.

With **Uno Platform Studio 3.0**, Hot Design works alongside two new AI-native components:

- **Uno Platform Studio App** — go from a prompt to a working, cross-platform app in minutes, then continue building in your IDE.
- **Uno Platform Studio Agent** — an orchestration layer that brings deep, cross-platform .NET domain knowledge and 70+ Uno Platform-specific skills to AI models, delivered through the `uno-platform-studio` plugin for Claude Code, GitHub Copilot, and OpenAI Codex.

Together with Hot Reload, Design-to-Code, and the Uno Platform MCPs, these tools streamline your cross-platform development and boost productivity.

[➜ Learn more about Uno Platform Studio](xref:Uno.Platform.Studio.Overview)

### Key Features

**Hot Design** empowers you to:

- **Achieve the Fastest Inner DevLoop**: With a single click, turn your running app into a visual Designer. Another click returns you to your app, keeping you in your workflow without disruption.
- **Design in Real Time**: Modify your app’s UI instantly while it’s running, enabling fast, interactive development.
- **Leverage Your Favorite IDE**: Seamlessly integrate with Visual Studio, VS Code, or JetBrains Rider on any OS, with IDE-agnostic support.
- **Synchronize Code and Designer**: Reflect changes instantly between the Designer and code, ensuring your live app and XAML remain a single source of truth.
- **Integrate Live Data**: Connect your UI to data sources intuitively and see real-time updates to data bindings as you build, simplifying the process.
- **Work Directly with Real Data**: Skip mock data creation by working with actual data sources from your running app, gaining a true-to-life feel of your app's behavior. Mock data is also supported for added flexibility.
- **Reuse Custom & 3rd-Party Controls**: Incorporate custom and third-party UI components effortlessly while maintaining a consistent look and behavior across platforms.
- **Manage State with Flexibility**: Work seamlessly with MVVM or MVUX to consume real-time data while keeping UI logic separate from core logic.
- **Apply Styles Easily**: Enhance your app’s UI and UX with predefined styles, applied effortlessly in just a few clicks — no coding required.
- **Explore Responsive Layouts**: Test layout options with a single click and instantly visualize how your app adapts to different devices and form factors.
- **Switch Themes Effortlessly**: Toggle between light and dark modes with one click to ensure a consistent user experience across color schemes.
- **Design on Remote Devices**: Fine-tune your UI directly on remote devices or emulators, instantly seeing changes without the need for constant redeployment.
- **Simplify Property Management**: Use Smart Properties to quickly find, modify, and bind key UI properties without leaving the live design environment, saving time and effort.
- **Design Components in Isolation**: Use **Previews** to open a single control, page, `UserControl`, data template, or styled variant on its own, in the data state you care about — without navigating your app to the screen that uses it.
- **See and Shape Your Design System**: Use **Theme** to review the controls, palette, and type scale your design system produces, rendered live by your running app, and adjust its seed colors, shapes, spacing, density and typeface with the change applied at once.

## Why Hot Design<sup>®</sup>?

**Hot Design<sup>®</sup>** brings together runtime UI design, live data integration, and cross-platform development to streamline your app-building process. It empowers you to work more efficiently, stay in the flow, and deliver polished, cross-platform apps with ease.

By simplifying UI development and accelerating your workflow, **Hot Design** helps you stay productive and focus on creating great applications.

**Let’s get started!**

## Core Features & Documentation

### Workspace and Navigation

- **[Toolbar](xref:Uno.HotDesign.Toolbar)** — Modes, undo/redo, form factor, zoom, theme, and panel visibility
- **[Scope Selector](xref:Uno.HotDesign.ScopeSelector)** — Navigate and edit UserControls and DataTemplates in isolation
- **[Toolbar and External Tool Window](xref:Uno.HotDesign.ToolbarExternalWindow)** — Fixed toolbar options, external window mode, and tool layout management

### Design and Elements

- **[Toolbox](xref:Uno.HotDesign.Toolbox)** — Categorized controls, snippets, and drag-and-drop design
- **[Elements](xref:Uno.HotDesign.Elements)** — Visual tree structure and hierarchy management
- **[Canvas](xref:Uno.HotDesign.Canvas)** — Interactive design surface with real-time preview
- **[Properties](xref:Uno.HotDesign.Properties)** — Smart and advanced property editing

### Components

- **[Previews](xref:Uno.HotDesign.Previews)** — Design a single component in isolation, in the data state you choose
- **[Theme](xref:Uno.HotDesign.Themes)** — Review the design system your app applies — its controls, palette, and type scale — and adjust it

### Reference

- **[Keyboard Shortcuts](xref:Uno.HotDesign.Shortcuts)** — Quick keyboard navigation and actions
- **[Troubleshooting](xref:Uno.HotDesign.Troubleshooting)** — Known issues and solutions

## Next Steps

- **[Get Started Guide](xref:Uno.HotDesign.GetStarted.Guide)**
  Getting started with setting up **Hot Design** and exploring the key areas and features of the visual designer it offers.

- **[Counter App Tutorial](xref:Uno.HotDesign.GetStarted.CounterTutorial)**
  A hands-on walkthrough for building the [Counter App](xref:Uno.Workshop.Counter) using **Hot Design**, showcasing its features and workflow in action.
