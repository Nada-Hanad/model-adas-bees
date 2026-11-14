# Exercise form checker (pose estimation)

A Python prototype that checks exercise form from a camera or image: MediaPipe Pose finds the body landmarks, and the script measures the angles between joints (for example hip, knee and ankle) to tell a correct squat, plank or donkey kick from a common mistake. The joint angles are drawn on the frame with OpenCV so the user can see what is off.

## How it works

1. MediaPipe Pose returns 33 landmarks per frame.
2. `findAngle(p1, p2, p3)` computes the angle at `p2` from the two segments, using `atan2`, normalised to 0–360°.
3. Thresholds per exercise decide whether the posture matches the correct form; the repository includes labelled example images of correct and incorrect versions of each exercise.

## Running it

```bash
pip install opencv-python mediapipe numpy
python basics.py
```

Built in March 2022 as the computer-vision part of a team project ("Adas Bees").
