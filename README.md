# TrackMe AI v0.2 — free personal camera tracker

## Added
- Push-up tracker
- Squat tracker
- Plank timer
- Study mode with observable presence/seated/focused estimate
- Local session history (last 50 sessions)
- Mode switching
- No paid API and no cloud backend
- All tracking logic is intended to run on-device

## Model
Google's current MediaPipe Android Pose Landmarker documentation uses `com.google.mediapipe:tasks-vision` and the `pose_landmarker_lite.task` model in `src/main/assets`.

Official model URL:
https://storage.googleapis.com/mediapipe-models/pose_landmarker/pose_landmarker_lite/float16/1/pose_landmarker_lite.task

Download that file into:
app/src/main/assets/pose_landmarker_lite.task

Google's docs confirm Pose Landmarker supports live video streams and outputs pose landmarks in image and world coordinates:
https://developers.google.com/edge/mediapipe/solutions/vision/pose_landmarker/android

## Important engineering note
The current analyzer includes a simple Y-channel fallback to keep the source self-contained, but production quality should replace it with a proper YUV_420_888 -> RGB conversion or the current CameraX/MediaPipe image path. This matters for accurate pose inference.

## Next upgrade
- Proper RGB conversion
- Face/eye/head-direction signal for stronger study detection
- Desk-zone calibration
- Custom rule builder
- Optional offline natural-language rule parser
- Better repetition validation and form scoring
