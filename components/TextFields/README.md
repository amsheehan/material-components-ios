<!--docs:
title: "Text Fields"
layout: detail
section: components
excerpt: "Text fields allow users to input text into your app."
iconId: text_field
path: /catalog/textfields/
api_doc_root: true
-->

<!-- This file was auto-generated using ./scripts/generate_readme textfields -->

# Text Fields

<div class="article__asset article__asset--screenshot">
  <img src="docs/assets/textfields.png" alt="Text Fields" width="375">
</div>

Text fields allow users to input text into your app. They are a direct connection to your users' thoughts and intentions via on-screen, or physical, keyboard. The Material Design Text Fields take the familiar element to new levels by adding useful animations, character counts, helper text, error states, and styles.

MDC's text fields come in several styles and have a great range of customization. Google's UX research has determined that Outlined and Filled (aka 'text box') styles perform the best by a large margin. So use `MDCTextInputControllerOutlinedField` , `MDCTextInputControllerTextFieldBox`, and `MDCTextInputControllerTextArea` if you can and set colors and fonts that match your company's branding.

For more information on text field styles, and animated images of each style in action, see [Text Field Styles](./styling).

## Design & API documentation

<ul class="icon-list">
  <li class="icon-list-item icon-list-item--link"><a href="https://material.io/guidelines/components/text-fields.html">Material Design guidelines: Text Fields</a></li>
  <li class="icon-list-item icon-list-item--link"><a href="https://material.io/components/ios/catalog/textfields/api-docs/Classes/MDCTextField.html">API: MDCTextFiel</a></li>
  <li class="icon-list-item icon-list-item--link"><a href="https://material.io/components/ios/catalog/textfields/api-docs/Classes/MDCMultilineTextField.html">API: MDCMultilineTextField</a></li>
</ul>

## Table of contents

- [Overview](#overview)
- [Installation](#installation)
  - [Installation with CocoaPods](#installation-with-cocoapods)
  - [Importing](#importing)
  - [Text Field Classes: The Inputs](#text-field-classes-the-inputs)
  - [Text Field Classes: The Controllers](#text-field-classes-the-controllers)
- [Usage](#usage)
- [Examples - Multi Line](#examples---multi-line)
  - [Text Field with Floating Placeholder](#text-field-with-floating-placeholder)
  - [Text Field with Character Count and Inline Placeholder](#text-field-with-character-count-and-inline-placeholder)
- [Extensions](#extensions)
  - [Text Fields Color Theming](#text-fields-color-theming)
  - [Text Fields Typography Theming](#text-fields-typography-theming)

- - -

## Overview

Text Fields provides both a single-line version based on `UITextField` and a multi-line version backed by `UITextView` as well as objects that customize the text fields' behavior and appearance called 'Text Input Controllers'.

The actual components (`MDCTextField` & `MDCMultilineTextField`) are 'dumb': they do not have styles, animations, or advanced features. They are designed to be controlled from the outside, via very liberal public API, with a text input controller.

Most text input controllers included are based on `MDCTextInputControllerUnderline` which manipulates the exposed elements of the text field to make placeholders float.

There is also a text input controller for full-width forms (`MDCTextInputControllerFullWidth`). Like `MDCTextInputControllerUnderline`, it also handles errors and character counting.

Customize the included text input controllers via their parameters or create your own to express your app's brand identity thru typography, color, and animation: if the placeholder should move, add constraints or change the frame. If the trailing label should display validation information, change the text and color it.

This pattern is not a delegation or data source-like relationship but rather a controller-to-view relationship: the text field does not require nor expect to be served data or instruction but is instead malleable and easily influenced by outside interference.

## Installation

<!-- Extracted from docs/../../../docs/component-installation.md -->

### Installation with CocoaPods

Add the following to your `Podfile`:

```bash
pod 'MaterialComponents/textfields'
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
import MaterialComponents.Materialtextfields
```

#### Objective-C

```objc
#import "Materialtextfields.h"
```
<!--</div>-->


<!-- Extracted from docs/classes.md -->

### Text Field Classes: The Inputs

#### Text Field

This is a single-line text input. It's subclassed from `UITextField` and supports all the features you'd expect from a `UITextField`:

* Placeholder
* Overlay views (left and right / leading and trailing)
* Custom fonts, colors
* Clear button

as well as new features:

* Underline
* Labels below the input
* Custom layouts
* Persistable placeholder
* Border view

#### Multi-line Text Field

This is a multi-line text input. It's subclassed from `UIView` with an embedded `UITextView`. It supports all the features of the single-line text field and `UITextView` plus:

* Minimum number of lines

### Text Field Classes: The Controllers

#### Default Text Input Controller

This class holds all the 'magic' logic necessary to make the naturally 'dumb' text field and text view behave with:

* Animations
* Styles
* Errors
* Character counts

- - -

#### Full Width Text Input Controller

Similar to the default text input controller but optimized for full width forms like emails.


## Usage

<!-- Extracted from docs/usage.md -->

A text field that conforms to MDCTextInput can be added to a view hierarchy the same way UITextField and UIView are. But to achieve the animations and presentations defined by the guidelines (floating placeholders, character counts), a controller that conforms to protocol `MDCTextInputController` must be initialized to manage the text field.

**NOTE:** Expect to interact with _both the text field_ (for the traditional API) _and the controller_ (for changes affecting the presentation and state).


<!-- Extracted from docs/examples.md -->

## Examples - Multi Line

### Text Field with Floating Placeholder

<!--<div class="material-code-render" markdown="1">-->
#### Swift

``` swift
let textFieldFloating = MDCMultilineTextField()
scrollView.addSubview(textFieldFloating)

textFieldFloating.placeholder = "Full Name"
textFieldFloating.textView.delegate = self

textFieldControllerFloating = MDCTextInputControllerUnderline(input: textFieldFloating) // Hold on as a property
```

#### Objective-C

``` objc
MDCMultilineTextField *textFieldFloating = [[MDCMultilineTextField alloc] init];
[self.scrollView addSubview:textFieldFloating];

textFieldFloating.placeholder = @"Full Name";
textFieldFloating.textView.delegate = self;

self.textFieldControllerFloating = [[MDCTextInputControllerUnderline alloc] initWithTextInput:textFieldFloating];
```
<!--</div>-->

### Text Field with Character Count and Inline Placeholder

<!--<div class="material-code-render" markdown="1">-->
#### Swift

``` swift
// First the text field component is setup just like a UITextField
let textFieldDefaultCharMax = MDCMultilineTextField()
scrollView.addSubview(textFieldDefaultCharMax)

textFieldDefaultCharMax.placeholder = "Enter up to 50 characters"
textFieldDefaultCharMax.textView.delegate = self

// Second the controller is created to manage the text field
textFieldControllerDefaultCharMax = MDCTextInputControllerUnderline(input: textFieldDefaultCharMax) // Hold on as a property
textFieldControllerDefaultCharMax.characterCountMax = 50
textFieldControllerDefaultCharMax.isFloatingEnabled = false
```

#### Objective-C

``` objc
// First the text field component is setup just like a UITextField
MDCMultilineTextField *textFieldDefaultCharMax = [[MDCMultilineTextField alloc] init];
[self.scrollView addSubview:textFieldDefaultCharMax];

textFieldDefaultCharMax.placeholder = @"Enter up to 50 characters";
textFieldDefaultCharMax.textView.delegate = self;

// Second the controller is created to manage the text field
self.textFieldControllerDefaultCharMax = [[MDCTextInputControllerUnderline alloc] initWithTextInput: textFieldDefaultCharMax];
self.textFieldControllerDefaultCharMax.characterCountMax = 50;
self.textFieldControllerDefaultCharMax.floatingEnabled = NO;
```
<!--</div>-->


## Extensions

<!-- Extracted from docs/color-theming.md -->

### Text Fields Color Theming

You can theme a text field with your app's color scheme using the ColorThemer extension.

You must first add the Color Themer extension to your project:

```bash
pod 'MaterialComponents/TextFields+Extensions/ColorThemer'
```

<!--<div class="material-code-render" markdown="1">-->
#### Swift
```swift
// Step 1: Import the ColorThemer extension
import MaterialComponents.MaterialTextFields_ColorThemer

// Step 2: Create or get a color scheme
let colorScheme = MDCSemanticColorScheme()

// Step 3: Apply the color scheme to your component

// Applying to a text field
MDCTextFieldColorThemer.apply(colorScheme, to: textField)

// Applying to an input controller
MDCTextFieldColorThemer.applySemanticColorScheme(colorScheme, to: inputController)

// Applying to a specific class type of inputController
MDCTextFieldColorThemer.applySemanticColorScheme(colorScheme, 
    toAllControllersOfClass: MDCTextInputControllerUnderline.self)
```

#### Objective-C

```objc
// Step 1: Import the ColorThemer extension
#import "MaterialTextFields+ColorThemer.h"

// Step 2: Create or get a color scheme
id<MDCColorScheming> colorScheme = [[MDCSemanticColorScheme alloc] init];

// Step 3: Apply the color scheme to your component

// Applying to a text field
[MDCTextFieldColorThemer applySemanticColorScheme:colorScheme toTextInput:textField];

// Applying to an input controller
[MDCTextFieldColorThemer applySemanticColorScheme:colorScheme
                            toTextInputController:inputController];

// Applying to a specific class type of inputController
[MDCTextFieldColorThemer applySemanticColorScheme:colorScheme 
                 toAllTextInputControllersOfClass:[MDCTextInputControllerUnderline class]];
```
<!--</div>-->


<!-- Extracted from docs/typography-theming.md -->

### Text Fields Typography Theming

You can theme a text field with your app's typography scheme using the TypographyThemer extension.

You must first add the Typography Themer extension to your project:

```bash
pod 'MaterialComponents/TextFields+Extensions/TypographyThemer'
```

<!--<div class="material-code-render" markdown="1">-->
#### Swift
```swift
// Step 1: Import the TypographyThemer extension
import MaterialComponents.MaterialTextFields_TypographyThemer

// Step 2: Create or get a typography scheme
let typographyScheme = MDCTypographyScheme()

// Step 3: Apply the typography scheme to your component

// Applying to a text field
MDCTextFieldTypographyThemer.apply(typographyScheme, to: textField)

// Applying to an input controller
MDCTextFieldTypographyThemer.apply(typographyScheme, to: inputController)

// Applying to a specific class type of inputController
MDCTextFieldTypographyThemer.apply(typographyScheme, 
    toAllControllersOfClass: MDCTextInputControllerUnderline.self) 
```

#### Objective-C

```objc
// Step 1: Import the TypographyThemer extension
#import "MaterialTextFields+TypographyThemer.h"

// Step 2: Create or get a typography scheme
id<MDCTypographyScheming> typographyScheme = [[MDCTypographyScheme alloc] init];

// Step 3: Apply the typography scheme to your component

// Applying to a text field
[MDCTextFieldTypographyThemer applyTypographyScheme:typographyScheme toTextInput:textField];

// Applying to an input controller
[MDCTextFieldTypographyThemer applyTypographyScheme:typographyScheme
                              toTextInputController:inputController];

// Applying to a specific class type of inputController
[MDCTextFieldTypographyThemer applyTypographyScheme:typographyScheme 
                   toAllTextInputControllersOfClass:[MDCTextInputControllerUnderline class]];
```
<!--</div>-->

