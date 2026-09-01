# TrackMe AI v0.3 — Custom Tracker

## What changed

You can now give the app an instruction instead of selecting only a fixed exercise mode.

Examples:

- `Track me for 20 minutes and count my push-ups.`
- `Track me for 30 minutes and count my squats.`
- `Track me for 1 hour and tell me how long I stayed at my desk.`
- `Track me for 45 minutes and count push-ups and tell me when I leave.`

The parser is **local and deterministic**. It does not send the instruction to an AI API.

## Supported observable rules

- push-up count
- squat count
- stand/sit transition count
- person presence / absence
- seated/focused-time estimate
- session duration

## What "custom" means in v0.3

Natural-language instructions are mapped to these supported signals. The app does NOT yet understand arbitrary concepts such as "know if I am solving maths correctly" or "know whether I am genuinely concentrating".

Those require additional models/signals.

## Privacy

Camera frames are processed by the local MediaPipe pipeline. The custom-rule parser itself is completely offline.

## Technical basis

MediaPipe Pose Landmarker supports live camera streams and provides normalized image landmarks plus 3D world landmarks. Its Android live-stream mode uses an asynchronous result listener, which is the architecture used by this version.
