# ReadMoreTextView

A custom Android `TextView` that trims long text and lets the user expand or collapse it.

This fork migrates the original project from the legacy Android Support Library to AndroidX. It builds with `android.enableJetifier=false`, so applications do not need Jetifier for this library.

## Requirements

- AndroidX
- Android API 14 or newer
- Compile SDK 35 or newer

## Build

```bash
./gradlew build
```

Jetifier is intentionally disabled in [`gradle.properties`](gradle.properties). A successful build therefore verifies that the project has no legacy Support Library bytecode requiring translation.

The library also supports local Maven publication:

```bash
./gradlew :readmoretextview:publishToMavenLocal
```

This publishes `com.borjabravo:readmoretextview:2.2.0-androidx` to the local Maven repository.

## Usage

Add `ReadMoreTextView` to a layout:

```xml
<com.borjabravo.readmoretextview.ReadMoreTextView
    android:id="@+id/text_view"
    android:layout_width="match_parent"
    android:layout_height="wrap_content" />
```

Available attributes:

- `app:trimExpandedText`: text shown when the view is expanded.
- `app:trimCollapsedText`: text shown when the view is collapsed.
- `app:trimLength`: character count used by length mode.
- `app:trimLines`: visible line count used by line mode.
- `app:showTrimExpandedText`: whether to show the collapse action.
- `app:colorClickableText`: color of the clickable action text.
- `app:trimMode`: `trimModeLength` or `trimModeLines`.

## Screenshots

![Collapsed text](screenshots/collapsed.png)
![Expanded text](screenshots/expanded.png)

## License

Copyright 2016 Borja Bravo

Licensed under the [Apache License, Version 2.0](LICENSE).
