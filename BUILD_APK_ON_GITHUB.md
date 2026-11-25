# Build Open Jarvis APK with GitHub Actions (phone-friendly)

This source archive includes `.github/workflows/android-apk.yml` to build a **debug APK** on GitHub's hosted runner. It does not contain a prebuilt APK.

## Steps
1. Create a new empty repository on GitHub (for example `open-jarvis-phone`).
2. Upload the **contents** of this project folder to the repository root (not the ZIP file itself). Keep the `.github/workflows/android-apk.yml` path intact.
3. Open the repository's **Actions** tab and enable Actions if GitHub asks.
4. Select **Build Open Jarvis APK** in the left panel, tap **Run workflow**, then **Run workflow** again.
5. Wait for the run to finish with a green check mark.
6. Open that successful run, scroll to **Artifacts**, and download `OpenJarvis-debug-apk`.
7. Extract the artifact ZIP on Android and install `app-debug.apk`. If Android blocks installation, allow the browser/file manager to install unknown apps.

## Build details
- Uses Java 17, Gradle 8.2, Android SDK 34.
- Builds `:app:assembleDebug` only. This is a debug-signed APK, not a Play Store release.
- No API key is needed to compile. Add your Gemini/Groq key inside the installed app's provider settings, never commit it to GitHub.

## Important
This project requests Accessibility and overlay capabilities. Review permissions and only enable them if you trust the source. The build workflow does not change app code or grant permissions automatically.
