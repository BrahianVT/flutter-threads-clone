This code defines three individual UI components (widgets) for the authentication screen, likely located within the `lib/screen/auth/widgets` directory. These widgets are built using Flutter and interact with the `AuthBloc` for state management.

## `logo_auth.dart`

This file defines a stateless widget responsible for displaying the application's logo and introductory text on the authentication screen.

*   **Imports:**
    *   `package:danter/screen/auth/bloc/auth_bloc.dart'`: Imports the `AuthBloc` to access the `AuthState` class, which is used to determine the current authentication mode (login or signup).
    *   `package:flutter/material.dart'`: Imports the core Flutter Material Design library.

*   **`LogoAuth` Class:**
    *   `const LogoAuth({ ... })`: The constructor takes a `Key`, `themeData`, and `state` as required parameters.
        *   `themeData`: Provides access to the current theme's colors and text styles.
        *   `state`: The current state of the `AuthBloc`, used to determine whether to display "Welcome" and "Please Login..." or "Register" and "Set your email...".
    *   `final ThemeData themeData;`: Stores the theme data.
    *   `final AuthState state;`: Stores the current authentication state.
    *   `@override Widget build(BuildContext context) { ... }`: The `build` method describes the UI for this widget.
        *   `return Column(...)`: The main layout is a `Column`, arranging its children vertically in the center.
        *   `Image.asset('assets/images/d.png', ...)`: Displays an image from the application's assets (presumably the app's logo). The `color` property is set to the `primary` color from the theme's color scheme, allowing the logo color to adapt to the current theme.
        *   `SizedBox(height: 14)`: Adds vertical spacing.
        *   `Text(state.isLoginMode ? 'Welcome' : 'Register', ...)`: Displays the main title text ("Welcome" or "Register") based on the `state.isLoginMode`. The text style uses the `primary` color and a fixed font size.
        *   `SizedBox(height: 16)`: Adds vertical spacing.
        *   `Text(state.isLoginMode ? 'Please Login to your account' : 'Set your email and password', ...)`: Displays the subtitle text, also changing based on the authentication mode. The text style uses the `primary` color and a fixed font size.
        *   `SizedBox(height: 24)`: Adds vertical spacing.

**Purpose of `LogoAuth`:**

This widget provides the visual header for the authentication screen, displaying the app logo and relevant text based on whether the user is in login or signup mode. It's a presentational widget that receives data (theme and state) from its parent and renders the UI accordingly.

## `password_textField.dart`

This file defines a stateful widget for a password input field, including the ability to toggle password visibility.

*   **Imports:**
    *   `package:flutter/material.dart'`: Imports the core Flutter Material Design library.

*   **`PasswordTextField` Class:**
    *   `const PasswordTextField({ ... })`: The constructor takes a `Key`, `onbackground`, `passwordController`, and `titelText` as required parameters.
        *   `onbackground`: A `Color` value, likely the `onBackground` color from the theme, used for the container's background.
        *   `passwordController`: A `TextEditingController` for managing the text in the input field.
        *   `titelText`: The label text for the input field (e.g., "password" or "repeat the password").
    *   `final TextEditingController passwordController;`: Stores the text editing controller.
    *   `final String titelText;`: Stores the label text.
    *   `final Color onbackground;`: Stores the background color.
    *   `@override State<PasswordTextField> createState() => PasswordTextFieldState();`: Creates the mutable state for this stateful widget.

*   **`PasswordTextFieldState` Class:**
    *   `bool obscureText = true;`: A boolean variable to control whether the text in the input field is obscured (for password masking). It's initialized to `true`.
    *   `@override Widget build(BuildContext context) { ... }`: The `build` method describes the UI for the input field.
        *   `return Container(...)`: A `Container` with a background color (from the theme's `onBackground` color scheme property) and rounded corners.
        *   `TextField(...)`: The actual text input field.
            *   `cursorHeight`, `controller`, `keyboardType`: Configures the cursor height, assigns the provided `TextEditingController`, and sets the keyboard type to `TextInputType.visiblePassword`.
            *   `obscureText: obscureText`: Controls password masking based on the `obscureText` state variable.
            *   `style`: Sets the text style for the input text.
            *   `decoration: InputDecoration(...)`: Configures the input field's decoration.
                *   `suffixIcon: IconButton(...)`: Displays an icon button at the end of the input field.
                    *   `onPressed: () { setState(() { obscureText = !obscureText; }); }`: The `onPressed` callback toggles the `obscureText` state variable and calls `setState` to rebuild the widget and update the icon and password visibility.
                    *   `icon: Icon(...)`: Displays either the "visibility" or "visibility\_off" icon based on the `obscureText` state. The icon color is set to the `primary` color with some opacity.
                *   `label: Text(...)`: Sets the label text for the input field using the provided `titelText`. The text style uses the theme's `labelSmall` style with some overrides.

**Purpose of `PasswordTextField`:**

This widget provides a reusable and interactive password input field component. It handles the logic for toggling password visibility and uses the provided `TextEditingController` to manage the entered text. It's a self-contained UI element that manages its own internal state (`obscureText`).

## `text_field_auth.dart`

This file defines a stateless widget that contains the username, password, and password confirmation input fields, as well as the authentication button and the switch between login and signup modes.

*   **Imports:**
    *   `package:danter/screen/auth/bloc/auth_bloc.dart'`: Imports the `AuthBloc` and `AuthState` to interact with the BLoC.
    *   `package:danter/screen/auth/widgets/password_textField.dart'`: Imports the custom `PasswordTextField` widget.
    *   `package:flutter/material.dart'`: Imports the core Flutter Material Design library.
    *   `package:flutter_bloc/flutter_bloc.dart'`: Imports the `flutter_bloc` package for interacting with the BLoC within the UI.
    *   `package:loading_indicator/loading_indicator.dart'`: Imports a package for displaying loading indicators.

*   **`TextFieldAuth` Class:**
    *   `const TextFieldAuth({ ... })`: The constructor takes a `Key`, `themeData`, `usernameController`, `onbackground`, `passwordController`, `passwordConfirmController`, and `state` as required parameters.
        *   `themeData`: Provides access to the current theme.
        *   `usernameController`, `passwordController`, `passwordConfirmController`: `TextEditingController`s for managing the text in the respective input fields.
        *   `onbackground`: A `Color` value for the background of the text field containers.
        *   `state`: The current state of the `AuthBloc`, used to determine which input fields to display and the text on the button.
    *   `final ThemeData themeData;`: Stores the theme data.
    *   `final TextEditingController ...Controller;`: Store the text editing controllers.
    *   `final Color onbackground;`: Stores the background color.
    *   `final AuthState state;`: Stores the current authentication state.
    *   `@override Widget build(BuildContext context) { ... }`: The `build` method describes the UI for this widget.
        *   `return Column(...)`: The main layout is a `Column` for vertical arrangement.
        *   `Container(...)`: A `Container` for the username input field, similar in styling to the password field container.
        *   `TextField(...)`: The username input field.
            *   `cursorHeight`, `controller`, `keyboardType`: Configures the field properties.
            *   `style`: Sets the text style.
            *   `decoration: InputDecoration(...)`: Configures the decoration with a "username" label.
        *   `SizedBox(height: 16)`: Adds vertical spacing.
        *   `PasswordTextField(...)`: Includes the custom `PasswordTextField` for the password.
        *   `SizedBox(height: 16)`: Adds vertical spacing.
        *   `(!state.isLoginMode) ? PasswordTextField(...) : Container(),`: This is a conditional rendering based on the `state.isLoginMode`. If the state is *not* login mode (meaning it's signup mode), it displays another `PasswordTextField` for password confirmation. Otherwise, it displays an empty `Container`.
        *   `SizedBox(height: 16)`: Adds vertical spacing.
        *   `SizedBox(height: 55, child: ElevatedButton(...))`: A `SizedBox` to set the height of the button, containing an `ElevatedButton`.
            *   `style: ElevatedButton.styleFrom(...)`: Customizes the button's appearance, setting the background color to the theme's `primary` color.
            *   `onPressed: () { ... }`: The `onPressed` callback for the button.
                *   `BlocProvider.of<AuthBloc>(context).add(...)`: This is where the UI interacts with the BLoC. It gets the `AuthBloc` instance from the widget tree using `BlocProvider.of` and dispatches an `AuthButtonIsClicked` event. The event includes the text from the username, password, and password confirmation controllers.
            *   `child: state is AuthLoading ? SizedBox(...) : Text(...)`: This uses a ternary operator to conditionally display either a loading indicator or the button text based on the current `state`.
                *   If `state is AuthLoading`, it displays a `LoadingIndicator` from the imported package, with customized appearance based on the theme colors.
                *   Otherwise, it displays a `Text` widget with the button label ("Login" or "Register") based on `state.isLoginMode`, with customized text style.
        *   `SizedBox(height: 24)`: Adds vertical spacing.
        *   `GestureDetector(onTap: () { ... }, child: Row(...))`: A `GestureDetector` to make the text "Don't have an account?" / "You have an account?" tappable.
            *   `onTap: () { ... }`: The `onTap` callback dispatches an `AuthModeChangeIsClicked` event to the `AuthBloc`, triggering the switch between login and signup modes.
            *   `Row(...)`: Arranges the two text widgets horizontally.
            *   `Text(...)`: Displays the first part of the text, changing based on `state.isLoginMode`.
            *   `SizedBox(width: 8)`: Adds horizontal spacing.
            *   `Text(...)`: Displays the second part of the text ("Register" or "Login"), also changing based on `state.isLoginMode`. This text has an underline decoration to indicate it's tappable.

These three widgets together form the UI for the authentication screen, demonstrating how to structure a Flutter UI using reusable components and manage state with the BLoC pattern. The widgets receive the BLoC state and theme data as inputs and render the UI accordingly, while user interactions trigger events that are sent back to the BLoC for processing.
