# lib/core/constants Explained

This directory contains Dart files that define constant values and utility classes used throughout the application.

## `custom_colors.dart`

This file defines color palettes for both light and dark themes. It typically contains classes like `LightThemeColors` and `DarkThemeColors`, each holding static `Color` constants for primary, secondary, text, and background colors. This centralizes color definitions, making it easier to maintain consistent theming.

## `theme.dart`

This file contains the `ThemeSave` class, which is responsible for managing theme settings. It utilizes `SharedPreferences` (accessed via a dependency injection locator) to persist the user's preferred theme (light or dark) across app sessions. It provides methods to save and retrieve the boolean value indicating the selected theme.

## `variable_onstants.dart`

This file holds various static constant variables used globally within the application. These can include:

*   `roomId`: A constant identifier for a specific "room" or context.
*   `webAppNAme`: The name of the web application.
*   `domian`: The domain name or base URL for API requests or web views.
*   `imageAddress`: The base URL for accessing images.
*   `selectedImage`: Variables related to the management of selected images, potentially storing paths or identifiers.

This file serves as a central repository for important, unchanging values used throughout the app.