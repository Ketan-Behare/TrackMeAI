# Build TrackMe AI v0.3 on GitHub

1. Upload this project to a GitHub repository.
2. Open the repository's **Actions** tab.
3. Select **Build TrackMe AI APK**.
4. Tap **Run workflow**.
5. Wait for the build to finish.
6. Open the successful workflow run.
7. Under **Artifacts**, download `TrackMeAI-v0.3-debug-apk`.
8. Extract the downloaded ZIP and install `app-debug.apk` on Android.

The workflow downloads the MediaPipe Pose Landmarker Lite model during the build, so the model does not need to be uploaded manually.
