# Gap Calculator Pro

Gap Calculator Pro is a complete, professional, offline-first sequential numbers difference analyzer for Android built with Kotlin, Jetpack Compose, and Material Design 3. 

It enables users to input sequences of numbers, automatically calculates and color-codes sequential difference gaps (positive in green, negative in red), offers smart persistent storage, summarizes calculation chains, and confirms whether formulas are mathematically verified and matched.

---

## 🎨 Key Features

- **Sequential Gap Analysis**: Enter numbers sequentially to see automatic step-by-step gap calculations (e.g. `10 → 22 = +12`, `22 → 15 = -7`).
- **Color-Coded Feedback**: Instant visual scanning with custom green-colored positive differences and red-colored negative differences.
- **Verification Summary**: Automatically verifies calculation flows via the formula `Final Result = First Number + Total Gap` and displays high-visibility status badges (`✓ MATCHED` or `✗ NOT MATCHED`).
- **Auxiliary Input Toggles**: On-screen helper buttons to easily toggle negative values and insert decimals, bypassing soft keyboard device limitations.
- **Smart Data Persistence**: Automatically stores entered sequences in `SharedPreferences` to restore state instantly upon app re-opening.
- **Pro Clipboard Syncing**: Click a single button to copy a complete, formatted report of entered data, individual gaps, first/last numbers, sums, and verification status.

---

## 🛠️ Project Setup & Structure

The repository contains a fully structured Android Studio project that can be compiled, tested, and exported immediately:

- **Jetpack Compose UI**: Designed inside `MainActivity.kt` with modern Material Design 3, custom responsive styling, safe drawing insets, and standard test-tag identifiers.
- **MVVM Architecture**: Clean state-handling separation utilizing a persistent `GapCalculatorViewModel` with custom number formatting.
- **Local Verification**: Includes unit and screenshot testing setups (`ExampleRobolectricTest` and `GreetingScreenshotTest`) with Roborazzi.
- **CI/CD Integration**: Out-of-the-box support for automatic builds via GitHub Actions.

---

## 🚀 How to Open and Run

### 1. Open the Project in Android Studio
1. Launch Android Studio.
2. Select **File > Open** or choose **Open an Existing Project** from the welcome screen.
3. Select the root folder of this project and click **Open**.
4. Android Studio will automatically synchronize the Gradle configuration and download dependencies.

### 2. Run on Emulator or Physical Device
1. Connect a physical Android device with USB debugging enabled, or start a Virtual Device (AVD).
2. Select `app` as the run configuration and click the **Run** button (green play icon) or press `Shift + F10`.

---

## 📦 How to Build the APK

To build the application manually from the command line:

```bash
# On Linux and macOS:
./gradlew assembleDebug

# On Windows:
gradlew.bat assembleDebug
```

The compiled APK will be located at:
`app/build/outputs/apk/debug/app-debug.apk`

---

## 🧪 Running Tests

To verify local JVM unit and Roborazzi screenshot tests:

```bash
# Run unit and Robolectric tests
./gradlew :app:testDebugUnitTest

# Record/Update Roborazzi reference screenshots (if UI changes are made)
./gradlew :app:recordRoborazziDebug

# Verify screenshots against references
./gradlew :app:verifyRoborazziDebug
```

---

## 🤖 GitHub Actions Workflow

The repository includes a production-ready GitHub Actions workflow located in `.github/workflows/android.yml`.

### How it Works:
1. Every time you push to `main` or `master` branches, or open a pull request, the workflow is automatically triggered.
2. It sets up a JDK 17 environment, grants execute permissions to the wrapper, and builds the app using `./gradlew assembleDebug`.
3. It uploads the compiled `app-debug.apk` as a pipeline artifact so it can be downloaded directly from the GitHub run summary.
