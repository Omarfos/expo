# expo-constants

Provides system information that remains constant throughout the lifetime of your app.

# API documentation

- [Documentation for the master branch](https://github.com/expo/expo/blob/master/docs/pages/versions/unversioned/sdk/constants.md)
- [Documentation for the latest stable release](https://docs.expo.io/versions/latest/sdk/constants/)

# Installation in managed Expo projects

For managed [managed](https://docs.expo.io/versions/latest/introduction/managed-vs-bare/) Expo projects, please follow the installation instructions in the [API documentation for the latest stable release](https://docs.expo.io/versions/latest/sdk/constants/).

# Installation in bare React Native projects

For bare React Native projects, you must ensure that you have [installed and configured the `react-native-unimodules` package](https://github.com/expo/expo/tree/master/packages/react-native-unimodules) before continuing.

### Add the package to your npm dependencies

```
expo install expo-constants
```

### Optional: set up script to get app config

Optionally, you can set up a build script that will grab your app's config (from app.json or app.config.js) and embed it into your build. This will ensure `Constants.manifest` is defined on the first run of your app (before it has downloaded any OTA updates). If your app doesn't use `Constants.manifest`, you can skip this step.

To set up the script on iOS, add the following line to the **Bundle React Native code and images** Build Phase in your Xcode project:

```
../node_modules/expo-constants/scripts/get-app-config-ios.sh
```

To set up the script on Android, apply the following diff to `android/app/build.gradle`:

```diff
 apply from: "../../node_modules/react-native/react.gradle"
+apply from: "../../node_modules/expo-constants/scripts/get-app-config-android.gradle"
```

# Contributing

Contributions are very welcome! Please refer to guidelines described in the [contributing guide](https://github.com/expo/expo#contributing).
