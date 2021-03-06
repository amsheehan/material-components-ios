<!--docs:
title: "Feature Highlight"
layout: detail
section: components
excerpt: "Feature Highlight highlights a part of the screen in order to introduce users to new features and functionality."
iconId: feature_highlight
path: /catalog/feature-highlights/
api_doc_root: true
-->

<!-- This file was auto-generated using ./scripts/generate_readme FeatureHighlight -->

# Feature Highlight

<div class="article__asset article__asset--screenshot">
  <img src="docs/assets/feature_highlight.png" alt="Feature Highlight" width="375">
</div>

The Feature Highlight component is a way to visually highlight a part of the screen in order to introduce users to new features and functionality.

## Design & API documentation

<ul class="icon-list">
  <li class="icon-list-item icon-list-item--link"><a href="https://material.io/guidelines/growth-communications/feature-discovery.html">Material Design guidelines: Feature Discovery</a></li>
</ul>

## Table of contents

- [Installation](#installation)
  - [Installation with CocoaPods](#installation-with-cocoapods)
  - [Importing](#importing)
- [Usage](#usage)
  - [Typical use: highlight a view](#typical-use-highlight-a-view)
- [Extensions](#extensions)
# [Feature Highlight Color Theming](#feature-highlight-color-theming)
- [Example code](#example-code)
# [Feature Highlight Typography Theming](#feature-highlight-typography-theming)
- [Example code](#example-code)

- - -

## Installation

<!-- Extracted from docs/../../../docs/component-installation.md -->

### Installation with CocoaPods

Add the following to your `Podfile`:

```bash
pod 'MaterialComponents/FeatureHighlight'
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
import MaterialComponents.MaterialFeatureHighlight
```

#### Objective-C

```objc
#import "MaterialFeatureHighlight.h"
```
<!--</div>-->


## Usage

<!-- Extracted from docs/typical-use-highlight-a-view.md -->

### Typical use: highlight a view

<!--<div class="material-code-render" markdown="1">-->
#### Swift
```swift
let completion = {(accepted: Bool) in
  // perform analytics here
  // and record whether the highlight was accepted
}

let highlightController = MDCFeatureHighlightViewController(highlightedView: viewToHighlight,
                                                            completion: completion)
highlightController.titleText = "Just how you want it"
highlightController.bodyText = "Tap the menu button to switch accounts, change settings & more."
highlightController.outerHighlightColor =
  UIColor.blue.withAlphaComponent(kMDCFeatureHighlightOuterHighlightAlpha)
present(highlightController, animated: true, completion:nil)
```

#### Objective-C
```objc
MDCFeatureHighlightCompletion completion = ^(BOOL accepted) {
  // perform analytics here
  // and record whether the highlight was accepted
};

MDCFeatureHighlightViewController *highlightController =
[[MDCFeatureHighlightViewController alloc] initWithHighlightedView:viewToHighlight
                                                        completion:completion];
highlightController.titleText = @"Just how you want it";
highlightController.bodyText = @"Tap the menu button to switch accounts, change settings & more.";
highlightController.outerHighlightColor =
    [[UIColor blueColor] colorWithAlphaComponent:kMDCFeatureHighlightOuterHighlightAlpha];
[self presentViewController:highlightController animated:YES completion:nil];
```
<!--</div>-->

Often when highlighting a view you will want to display a different view to the one you are highlighting. For example, flipping the primary and secondary colors in the presented version.

<!--<div class="material-code-render" markdown="1">-->
#### Swift
```swift
let displayedButton = UIButton(type: .system)
displayedButton.setTitle(highlightedButton.title(for: .normal), for: .normal)
displayedButton.setTitleColor(highlightedButton.backgroundColor, for: .normal)
displayedButton.backgroundColor = highlightedButton.titleColor(for: .normal)

let highlightController = MDCFeatureHighlightViewController(highlightedView: highlightedButton, andShow: displayedButton, completion: completion)
```

#### Objective-C
```objc
UIButton *displayedButton = [UIButton buttonWithType:UIButtonTypeSystem];
[displayedButton setTitle:[highlightedButton titleForState:UIControlStateNormal]
                 forState:UIControlStateNormal];
[displayedButton setTitleColor:highlightedButton.backgroundColor forState:UIControlStateNormal];
displayedButton.backgroundColor = [highlightedButton titleColorForState:UIControlStateNormal];
MDCFeatureHighlightViewController *highlightController =
[[MDCFeatureHighlightViewController alloc] initWithHighlightedView:highlightedButton
                                                       andShowView:displayedButton
                                                        completion:completion];
```
<!--</div>-->


## Extensions

<!-- Extracted from docs/color-theming.md -->

<!--docs:
title: "Color Theming"
layout: detail
section: components
excerpt: "How to theme Feature Highlight using the Material Design color system."
iconId: feature_highlight
path: /catalog/feature-highlights/color-theming/
-->

# Feature Highlight Color Theming

You can theme feature highlight with your app's color scheme using the ColorThemer extension.

You must first add the Color Themer extension to your project:

```bash
pod 'MaterialComponents/FeatureHighlight+Extensions/ColorThemer'
```

## Example code

<!--<div class="material-code-render" markdown="1">-->
#### Swift
```swift
// Step 1: Import the ColorThemer extension
import MaterialComponents.MaterialFeatureHighlight_ColorThemer

// Step 2: Create or get a color scheme
let colorScheme = MDCSemanticColorScheme()

// Step 3: Apply the color scheme to your component
MDCFeatureHighlightColorThemer.applySemanticColorScheme(colorScheme, to: component)
```

#### Objective-C

```objc
// Step 1: Import the ColorThemer extension
#import "MaterialFeatureHighlight+ColorThemer.h"

// Step 2: Create or get a color scheme
id<MDCColorScheming> colorScheme = [[MDCSemanticColorScheme alloc] init];

// Step 3: Apply the color scheme to your component
[MDCFeatureHighlightColorThemer applySemanticColorScheme:colorScheme
     toFeatureHighlightViewController:component];
```
<!--</div>-->

<!-- Extracted from docs/typography-theming.md -->

<!--docs:
title: "Typography Theming"
layout: detail
section: components
excerpt: "How to theme Feature Highlight using the Material Design typography system."
iconId: feature_highlight
path: /catalog/feature-highlights/typography-theming/
-->

# Feature Highlight Typography Theming

You can theme feature highlight with your app's typography scheme using the TypographyThemer extension.

You must first add the Typography Themer extension to your project:

```bash
pod 'MaterialComponents/FeatureHighlight+Extensions/TypographyThemer'
```

## Example code

<!--<div class="material-code-render" markdown="1">-->
#### Swift
```swift
// Step 1: Import the TypographyThemer extension
import MaterialComponents.MaterialFeatureHighlight_TypographyThemer

// Step 2: Create or get a typography scheme
let typographyScheme = MDCTypographyScheme()

// Step 3: Apply the typography scheme to your component
MDCFeatureHighlightTypographyThemer.applyTypographyScheme(typographyScheme, to: component)
```

#### Objective-C

```objc
// Step 1: Import the TypographyThemer extension
#import "MaterialFeatureHighlight+TypographyThemer.h"

// Step 2: Create or get a typography scheme
id<MDCTypographyScheming> typographyScheme = [[MDCTypographyScheme alloc] init];

// Step 3: Apply the typography scheme to your component
[MDCFeatureHighlightTypographyThemer applyTypographyScheme:colorScheme
     toFeatureHighlightViewController:component];
```
<!--</div>-->

