# Setting Up the Project

This guide will walk you through the steps needed to install Android Studio and set up a development environment for React Native.

## Prerequisites

Before starting, ensure that you have the following installed:

1. **Node.js**: [Download and install Node.js](https://nodejs.org/).
2. **Watchman (Optional)**: Used for file watching. Install it using Homebrew (macOS):
   ```bash
   brew install watchman
   ```

3. **Java Development Kit (JDK)**: Install OpenJDK 11 or later. You can download it from [AdoptOpenJDK](https://adoptopenjdk.net/) or for linux, use:
   ```bash
   sudo apt install openjdk-11-jdk
   ```
   
* When installing the jdk in windows, use the msi installer. If you are using the zip, then make sure that you add the $JAVA_HOME variable to the system path.

## Step 1: Install Android Studio

1. **Download Android Studio**:
    - Go to the [Android Studio Download Page](https://developer.android.com/studio) and download the latest version for your operating system.

2. **Install Android Studio**:
    - Follow the installation steps specific to your platform (Windows, macOS, or Linux).

3. **Set Up the Android SDK**:
    - Launch Android Studio.
    - Go to `Preferences` (macOS) or `File > Settings` (Windows/Linux).
    - Navigate to `Appearance & Behavior > System Settings > Android SDK`. (If this is your first time, open Android Studio and select more actions and go to SDK Manager from there.)
    - Under the SDK Platforms tab, select:
        - Android 14.0 or your preferred version. (An actual android device is recommended instead of the emulator.)
    - Under the SDK Tools tab, ensure that the following are checked:
        - Android SDK Build-Tools (latest)
        - Android Emulator (optional)
        - Android NDK (Side by Side) (26.1^~)
        - Android SDK Platform-Tools (latest)
        - Android SDK Command-Line Tools (latest)
        - CMake (latest)
    - Click `Apply` to install the packages.

## Step 2: Set Up Environment Variables

1. Open the **Environment Variables** settings:
   - Right-click on `This PC` or `My Computer` and select `Properties`.
   - Click `Advanced system settings` > `Environment Variables`.

2. Add a new system variable:
   - **Variable name**: `ANDROID_HOME`
   - **Variable value**: The path to your Android SDK (e.g., `C:\Users\YourUsername\AppData\Local\Android\Sdk`).

3. Edit the `Path` system variable and add the following:
   - `%ANDROID_HOME%\emulator`
   - `%ANDROID_HOME%\tools`
   - `%ANDROID_HOME%\tools\bin`
   - `%ANDROID_HOME%\platform-tools`

4. Click `OK` to save changes.

## Step 3: Run Your React Native App

1. Navigate to your project directory:
   ```bash
   cd MyReactNativeApp
   ```

2. Install Dependencies (first time only)
   ```bash
   npm install
   ```

3. Run the project on an android device
   ```bash
   npx expo run:android
   ```
   
* The first build takes approximately 10 - 30 minutes to complete depending on the computer specifications.

## Troubleshooting

1. **Error: Unable to load script from assets**:
    - Ensure your emulator is running and accessible.

2. **Java Heap Size Error**: (Should not happen with java sdk 9+)
    - Increase the heap size in `gradle.properties`:
      ```
      org.gradle.jvmargs=-Xmx2048m
      ```

3. **Android SDK Not Found**:
    - Verify `ANDROID_HOME` and `PATH` variables are correctly set.

## Additional Resources

- [React Native Documentation](https://reactnative.dev/docs/getting-started)
- [Android Studio Documentation](https://developer.android.com/studio/intro)

You're now ready to build React Native apps with Android Studio! 🎉
