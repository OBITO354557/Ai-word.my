# AI Smart Study Monitor

A local-first, installable study companion dashboard built with Vite and vanilla JavaScript.

## Run

```bash
npm install
npm run dev
```

Open the local URL in a browser, click **Enable camera**, then start a session.

## What works

- Browser camera permission flow using `getUserMedia` with helpful errors.
- Local-only camera stream; no upload or recording.
- Real session timer, session history, focus score derived from session events, and event timeline stored in `localStorage`.
- Original uploaded MP3s preserved verbatim in `assets/audio/` and mapped to eyes closed, face covered, or phone detected by default.
- Voice library with test buttons, master volume, alert toggle, and mapping persistence.
- PWA manifest and service worker.
- Responsive desktop, tablet, and mobile layouts.
- Optional native `FaceDetector` support: when the browser exposes it, a real face bounding box is drawn. When it does not, the UI explicitly says **AI MODEL UNAVAILABLE** rather than faking detection values.

## Vision limitation

FaceDetector, eye landmark, pose, and phone object detection are browser/model dependent. This build never fabricates those values. On browsers without a compatible local vision API/model, the camera stream still works and the dashboard shows the limitation honestly. A production deployment can add a bundled MediaPipe/ONNX model under `models/` without changing the camera/privacy contract.
