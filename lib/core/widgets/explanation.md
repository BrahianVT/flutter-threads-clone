# lib/core/widgets Explanation

This document provides a detailed technical explanation of the `.dart` files found in the `lib/core/widgets` directory. These files contain reusable Flutter widgets used throughout the application.

*   `Row_Image_Name_Text.dart`:
    This file likely defines a custom stateless or stateful widget that utilizes a `Row` widget for horizontal arrangement. It would typically contain an `Image` widget (possibly a `CircleAvatar` for profile pictures), a `Text` widget for a name, and another `Text` widget for additional descriptive text. The widget would accept parameters such as image source (e.g., `String` for a network URL, `File` for local image), `String` for the name, and `String` for the text. Styling properties for text (e.g., `TextStyle`) and image (e.g., `fit`, `width`, `height`) would be defined within the widget.

*   `bottom_sheet_custom.dart`:
    This file probably implements a custom bottom sheet using the `showModalBottomSheet` function or a similar approach like a custom `ModalRoute`. It would define the content that appears within the bottom sheet, which could be a `ListView` of options, a form built with various input widgets, or any other custom UI. It would likely expose parameters to configure the content displayed, handle user interactions within the bottom sheet, and potentially control its appearance (e.g., background color, shape).

*   `custom_alert_dialog.dart`:
    This file likely defines a custom `AlertDialog` widget. It would structure the dialog's layout using `title`, `content`, and `actions` properties. The `title` and `content` can accept `Widget`s, allowing for flexible layout within the dialog. The `actions` property would be a `List<Widget>`, typically containing `TextButton` or `ElevatedButton` widgets for user interaction (e.g., "OK", "Cancel"). Parameters would likely be used to customize the dialog's title (as a `String` or `Widget`), content (`String` or `Widget`), and the list of actions (`List<Widget>`).

*   `error.dart`:
    This file probably defines a widget to visually represent an error state to the user. This could range from a simple `Text` widget displaying an error message to a more complex layout including an icon (e.g., `Icon(Icons.error)`) and potentially a button (e.g., `ElevatedButton`) to allow the user to retry an operation. The widget would likely take an error message (as a `String`) as a parameter to display.

*   `image.dart`:
    This could be a wrapper widget around Flutter's built-in `Image` widget, adding custom functionality. This might include displaying a loading indicator (e.g., `CircularProgressIndicator`) while the image is loading, showing an error placeholder widget if the image fails to load, or implementing image caching logic. It would likely support different image providers like `NetworkImage`, `FileImage`, and `AssetImage`, and provide parameters for styling and behavior.

*   `image_post.dart`:
    This widget is likely specialized for displaying one or more images associated with a post. If multiple images are supported, it might use a `PageView` or a similar swiping widget to allow users to browse through them. It could also incorporate features like enabling pinch-to-zoom on images or providing a fullscreen view option when an image is tapped.

*   `image_user_post.dart`:
    This widget probably combines a user's profile image with the main content of their post. It would likely use a layout widget like `Row` or `Column` to position the user's image (e.g., within a `CircleAvatar`) alongside the text and other media content of the post.

*   `like_button.dart`:
    This file likely implements a custom interactive button specifically for handling "like" functionality. It would manage the internal state (whether the item is liked or not) and visually represent this state (e.g., a filled heart icon for liked, an outlined heart icon for not liked). It would use a `GestureDetector` or `InkWell` to detect tap events and trigger the corresponding like/unlike logic, potentially updating a like count displayed nearby.

*   `loding.dart`:
    This file probably defines a simple widget that displays a loading indicator to signify that a process is ongoing. This is commonly a `CircularProgressIndicator`, but it could also be a custom animation or a different type of progress indicator. It would likely be a stateless widget.

*   `logo.dart`:
    This widget is likely responsible for displaying the application's logo. This could be achieved using an `Image` widget to display an image from the application's assets, or potentially using a `CustomPaint` widget for a drawn logo.

*   `photo_user_followers.dart`:
    This widget might be used specifically to display a user's profile picture within the context of a list of followers. It would likely be a `CircleAvatar` or a similar widget designed to display a circular image, tailored for use in follower lists.

*   `post_detail.dart`:
    This is likely a composite widget responsible for rendering the complete view of a single post. It would likely use a `Column` to stack various elements, including the user who posted (perhaps using `Row_Image_Name_Text`), the post's text content (`Text` widget), any associated images (`image_post`), the like count and like button (`LikeButton`), and a section for displaying replies or comments (`replies_detail`).

*   `replies_detail.dart`:
    This widget probably focuses on displaying the comments or replies associated with a post. It might use a `ListView` or `Column` to list individual reply widgets. If replies are nested, it could employ a recursive approach to display the hierarchy of comments. Each individual reply within this list might also be a custom widget.

*   `snackbart.dart`:
    This file likely defines a custom `SnackBar` widget. It would specify the content of the Snackbar, typically a `Text` widget for a brief message and optionally an `SnackBarAction` for a user-tappable action within the Snackbar. This custom Snackbar would be shown using `ScaffoldMessenger.of(context).showSnackBar()`.

*   `tabbar_view_delegate.dart`:
    This file is likely related to the implementation of a `TabBarView` and defines a custom `SliverChildDelegate` (such as `SliverChildBuilderDelegate`). This delegate is used by the `TabBarView` to build the widgets for each tab lazily as they become visible, improving performance for large numbers of tabs.

*   `time.dart`:
    This widget could be used to display time-related information, such as the time a post was created or a message was sent. It would likely take a `DateTime` object or a timestamp (e.g., an `int` or `String`) as input and format it into a user-friendly string (e.g., "5 minutes ago", "Yesterday 3:00 PM"). It might use libraries like `timeago` for relative time formatting.

*   `user_detail_follow.dart`:
    This widget likely displays core user information alongside functionality related to following that user. It would probably use a `Row` to arrange elements like the user's profile picture (`Image` or `CircleAvatar`), their username or name (`Text`), and a button to follow or unfollow the user (perhaps a custom button or an `ElevatedButton`/`OutlinedButton` with conditional text and styling based on the follow status).

*   `write.dart`:
    This widget might represent an input area for users to create new content, such as composing a new post or writing a comment. It would likely include a `TextField` or `TextFormField` for multi-line text input. It could also incorporate additional features like buttons for attaching images, mentioning other users, or submitting the content.