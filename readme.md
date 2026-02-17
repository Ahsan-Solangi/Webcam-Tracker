Problem 1: AttributeError: module 'mediapipe' has no attribute 'solutions'
Cause: The script was written for the old MediaPipe API (mp.solutions.face_mesh), which was removed in MediaPipe 0.10.x+. The installed version was 0.10.30.
Attempted Solution 1: Downgrade MediaPipe to 0.10.3
Outcome: Failed — only versions 0.10.30, 0.10.31, and 0.10.32 are available on PyPI for Python 3.13.
Attempted Solution 2: Rewrite the script to use the new FaceLandmarker task-based API
Outcome: Failed — MediaPipe 0.10.30 has broken C bindings on Windows (function 'free' not found error), making the new API unusable too.

Problem 2: Python 3.13 incompatibility with MediaPipe
Cause: MediaPipe has no official Windows support for Python 3.13. Only the three most recent broken versions are published for it.
Solution: Create a separate Python 3.11 environment using Conda, where older working versions of MediaPipe are available.
"conda create -n eyetracker python=3.11"

