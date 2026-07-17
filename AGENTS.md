# Repository Guidelines

## Project Structure & Module Organization

Ice is a macOS 14+ menu-bar application written in Swift and SwiftUI. Open `Ice.xcodeproj` and use the shared `Ice` scheme. Application code is grouped by responsibility under `Ice/`: `Main/` contains app startup and shared state, `MenuBar/`, `Settings/`, `Hotkeys/`, and `Permissions/` contain feature code, while `UI/` holds reusable views and controls. Put cross-cutting helpers in `Utilities/`, macOS interop in `Bridging/`, and images/colors in `Assets.xcassets/`. Root-level `Resources/` contains project artwork and media.

## Build, Test, and Development Commands

Use Xcode to resolve Swift Package Manager dependencies, build, and run the app. From a machine with the full Xcode app selected, these commands are useful:

```sh
xcodebuild -project Ice.xcodeproj -scheme Ice build
xcodebuild -project Ice.xcodeproj -scheme Ice test
swiftlint --strict
```

The first builds the Debug app; the second runs any tests added to the scheme. There is currently no committed test target, so validate UI and menu-bar behavior manually on macOS 14 or later. `swiftlint --strict` matches the GitHub Actions lint check.

## Coding Style & Naming Conventions

Follow the existing Swift style: four spaces, no tabs, one primary type per appropriately named file, and a standard file header (`FileName.swift`, `Ice`). Use `UpperCamelCase` for types and `lowerCamelCase` for members; name manager types with a `Manager` suffix and SwiftUI views with a `View` suffix. Prefer focused feature directories and document non-obvious public or stateful behavior with `///` comments. SwiftLint requires trailing commas in multiline collections and arguments; do not weaken `.swiftlint.yml` to bypass violations.

## Testing Guidelines

Add XCTest coverage for logic that can be separated from AppKit/SwiftUI behavior. Name tests after the behavior, for example `testRehideStrategyHidesSectionWhenFocusChanges()`. For UI, permission, and menu-bar changes, record the macOS version and manual scenarios exercised, including multi-display or notch behavior when relevant.

## Commits & Pull Requests

Recent commits use short, imperative subjects such as `Fix possible retain cycle` and `Rework menus and pickers`. Keep commits scoped and avoid unrelated formatting churn. Pull requests should explain the user-visible change and implementation rationale, link the relevant issue when applicable, include screenshots or recordings for visual behavior, and state the build, lint, and manual checks performed.
