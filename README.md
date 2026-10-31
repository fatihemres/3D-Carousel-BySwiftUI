# 3D Carousel by SwiftUI

A small **SwiftUI learning exercise** that recreates a rotating, color-chip-style 3D carousel. It demonstrates how drag gestures, 3D rotation, z-ordering and view composition can produce an interactive effect using SwiftUI.

> **Attribution:** This project was created as a study based on [enebin's “SwiftUI | How to make 3D carousel view” (October 6, 2021)](https://enebin.medium.com/swiftui-how-to-make-3d-carousel-view-c81b1914cb25). The original concept and tutorial are credited to **enebin**. This repository should not be presented as an independently invented carousel design or a production-ready component package.

## What the demo does

- Renders **three overlapping carousels** using separate color palettes and horizontal offsets in [`ContentView.swift`](Carousel/View/ContentView.swift).
- Creates **32 color chips per carousel**, with labels derived from RGB values, in [`ThemeColor.swift`](Carousel/Config/ThemeColor.swift).
- Tracks horizontal dragging with `DragGesture`, updates the selected chip, and applies a `rotation3DEffect` around the Y axis.
- Uses `zIndex` to control card overlap and `ThemeFont.swift` to define the card layout and labels.

The display uses fixed dimensions and offsets. It is a visual experiment rather than a responsive, accessible, reusable UI library. It does not have a unit-test or UI-test target.

## Project layout

```text
Carousel/
  CarouselApp.swift             # SwiftUI app entry point
  View/ContentView.swift        # Composition of three demo carousels
  Config/ThemeColor.swift       # 32-card 3D carousel with drag gesture
  Config/ThemeFont.swift        # Color-chip card appearance
  Assets.xcassets/              # App and accent assets
Carousel.xcodeproj/             # Xcode iOS application project
```

## Run locally

1. Open [`Carousel.xcodeproj`](Carousel.xcodeproj) on a Mac with a compatible version of Xcode.
2. Select the shared **Carousel** scheme and an iOS Simulator or supported device.
3. Build and run. Drag horizontally over the color chips to rotate a carousel.

The checked-in project specifies **Swift 5** and a minimum deployment target of **iOS 17.4**. The current repository does not include external dependency-manager configuration.

### Build verification

[GitHub Actions](.github/workflows/ios-build.yml) builds the iOS app for a generic simulator using hosted **macOS 15 / Xcode 16.4**. A successful workflow confirms the project compiles in that environment. It is **not** a simulator interaction test, visual regression test, physical-device test, or distribution/signing verification. Check the latest run before claiming success.

## Origins, licensing and reuse

This is a **tutorial-derived learning project**. Credit for the referenced tutorial and design demonstration belongs to its original author, **enebin**. Review the original article and any accompanying source/license terms before reusing material from it.

The repository's [LICENSE](LICENSE) sets out a proprietary notice for original owner-controlled material and explicitly preserves third-party rights and previously valid grants. That notice does **not** claim ownership of the external tutorial or override any rights in third-party code, graphics or examples. Public GitHub visibility alone is not a permission grant.
