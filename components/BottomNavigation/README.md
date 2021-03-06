<!--docs:
title: "Bottom Navigation"
layout: detail
section: components
excerpt: "Bottom navigation provides a bar at the bottom of the screen with items to navigate between different views."
iconId: bottom_navigation
path: /catalog/bottomnavigation/
api_doc_root: true
-->

<!-- This file was auto-generated using ./scripts/generate_readme BottomNavigation -->

# Bottom Navigation

<div class="article__asset article__asset--screenshot">
  <img src="docs/assets/bottomnavigation.png" alt="Bottom Navigation" width="375">
</div>

[Bottom navigation](https://material.io/go/design-bottom-navigation) makes it easy to explore and switch between top-level views in a single tap. Tapping on a bottom navigation icon takes you directly to the associated view or refreshes the currently active view.

Bottom navigation should be used for top-level destinations in an app of similar importance or destinations requiring direct access from anywhere in the app. 

Be cautious when combining bottom navigation with similar navigation placed at the bottom of the screen (e.g. a bottom tab bar), as the combination may cause confusion when navigating an app. For example, tapping across both bottom tabs and bottom navigation could display a mixture of different transitions across the same content.

## Design & API documentation

<ul class="icon-list">
  <li class="icon-list-item icon-list-item--spec"><a href="https://material.io/go/design-progress-indicators">Material Design guidelines: Progress & activity</a></li>
  <li class="icon-list-item icon-list-item--link"><a href="https://material.io/components/ios/catalog/progress-indicators/activity-indicators/api-docs/Classes/MDCActivityIndicator.html">API: MDCActivityIndicator</a></li>
  <li class="icon-list-item icon-list-item--link"><a href="https://material.io/components/ios/catalog/progress-indicators/activity-indicators/api-docs/Enums/MDCActivityIndicatorMode.html">API: MDCActivityIndicatorMode</a></li>
  <li class="icon-list-item icon-list-item--link"><a href="https://material.io/components/ios/catalog/progress-indicators/activity-indicators/api-docs/Protocols/MDCActivityIndicatorDelegate.html">API: MDCActivityIndicatorDelegate</a></li>
</ul>

## Related components

<ul class="icon-list">
  <li class="icon-list-item icon-list-item--link"><a href="../ProgressView">ProgressView</a></li>
</ul>

## Table of contents

- [Overview](#overview)
- [Installation](#installation)
  - [Installation with CocoaPods](#installation-with-cocoapods)
  - [Importing](#importing)
- [Extensions](#extensions)
  - [Color Theming](#color-theming)
- [Example code](#example-code)
  - [Typography Theming](#typography-theming)
- [Example code](#example-code)

- - -

## Overview

MDCBottomNavigationBar can be added to a view hierarchy like any UIView. Material Design guidelines recommend always placing bottom navigation at the bottom of the screen.

MDCBottomNavigationBar works much like a UITabBar and both are populated with an array of UITabBarItems. However, MDCBottomNavigationBar is built with Material Design in mind and should be used with other Material Design components where possible to provide a consistent look and feel in an app. Additionally, while MDCBottomNavigationBar has similar features to MDCTabBar, MDCTabBar is chiefly intended for top navigation, whereas MDCBottomNavigationBar — as the name indicates — in intended for bottom navigation.

It is recommended that three to five items are used to populate the content of the bottom navigation bar. If there are fewer than three destinations, consider using tabs instead. If your top-level navigation has more than six destinations, provide access to destinations not covered in bottom navigation through alternative locations, such as a navigation drawer.

Title visibility can be configured in three ways: only show the title of the *selected  <li class="icon-list-item icon-list-item--spec">item, always show title regardless of any item's selection state, and never show title regardless of any item's selection state. The default behavior of bottom navigation is to only show the title for an item that is selected.</li>
</ul>

In landscape orientation, items can be configured to be justified or compactly clustered together. When items are justified the bottom navigation bar is fitted to the width of the device. Justified items can have their titles shown below their respective icons or adjacent to their respective icons.

## Installation

<!-- Extracted from docs/../../../docs/component-installation.md -->

### Installation with CocoaPods

Add the following to your `Podfile`:

```bash
pod 'MaterialComponents/BottomNavigation'
```
<!--{: .code-renderer.code-renderer--install }-->

Then, run the following command:

```bash
pod install
```

### Importing

To import the component:

<!--<div class="material-code-render" markdown="1">-->
#### Swift
```swift
import MaterialComponents.MaterialBottomNavigation
```

#### Objective-C

```objc
#import "MaterialBottomNavigation.h"
```
<!--</div>-->


## Extensions

<!-- Extracted from docs/color-theming.md -->

### Color Theming

You can theme a bottom navigation with your app's color scheme using the ColorThemer extension.

You must first add the Color Themer extension to your project:

```bash
pod 'MaterialComponents/BottomNavigation+Extensions/ColorThemer'
```

## Example code

<!--<div class="material-code-render" markdown="1">-->
#### Swift
```swift
// Step 1: Import the ColorThemer extension
import MaterialComponents.MaterialBottomNavigation_ColorThemer

// Step 2: Create or get a color scheme
let colorScheme = MDCSemanticColorScheme()

// Step 3: Apply the color scheme to your component
MDCBottomNavigationBarColorThemer.applySemanticColorScheme(colorScheme, to: component)
```

#### Objective-C

```objc
// Step 1: Import the ColorThemer extension
#import "MaterialBottomNavigation+ColorThemer.h"

// Step 2: Create or get a color scheme
id<MDCColorScheming> colorScheme = [[MDCSemanticColorScheme alloc] init];

// Step 3: Apply the color scheme to your component
[MDCBottomNavigationBarColorThemer applySemanticColorScheme:colorScheme
     toBottomNavigation:component];
```
<!--</div>-->

<!-- Extracted from docs/typography-theming.md -->

### Typography Theming

You can theme a bottom navigation with your app's typography scheme using the TypographyThemer extension.

You must first add the Typography Themer extension to your project:

```bash
pod 'MaterialComponents/BottomNavigation+Extensions/TypographyThemer'
```

## Example code

<!--<div class="material-code-render" markdown="1">-->
#### Swift
```swift
// Step 1: Import the TypographyThemer extension
import MaterialComponents.MaterialBottomNavigation_TypographyThemer

// Step 2: Create or get a typography scheme
let typographyScheme = MDCTypographyScheme()

// Step 3: Apply the typography scheme to your component
MDCBottomNavigationBarTypographyThemer.applyTypographyScheme(typographyScheme, to: component)
```

#### Objective-C

```objc
// Step 1: Import the TypographyThemer extension
#import "MaterialBottomNavigation+TypographyThemer.h"

// Step 2: Create or get a typography scheme
id<MDCTypographyScheming> typographyScheme = [[MDCTypographyScheme alloc] init];

// Step 3: Apply the typography scheme to your component
[MDCBottomNavigationBarTypographyThemer applyTypographyScheme:colorScheme
     toBottomNavigationBar:component];
```
<!--</div>-->

