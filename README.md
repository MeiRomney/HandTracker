# Hand Gesture Control & Finger Counting

This project uses **OpenCV**, **Mediapipe (via a custom HandTrackingModule)**, and **Pycaw** to create a real-time hand gesture recognition system. It allows you to:

1. Count the number of fingers shown to the camera and display corresponding images.  
2. Control your computer’s volume using the distance between your thumb and index finger.

---

## Features

### Finger Counting
- Detects hands and identifies finger positions using a custom `HandTrackingModule`.
- Counts the number of raised fingers.
- Displays a corresponding overlay image for the counted number.
- Displays the count in a stylized rectangle on the video feed.

### Volume Control
- Detects the distance between the thumb tip and index finger tip.
- Maps this distance to your system volume.
- Shows a volume bar and percentage in real-time.
- Changes the volume dynamically as you move your fingers closer or farther apart.

---

## Requirements

- Python 3.8+  
- OpenCV (`opencv-python`)  
- NumPy (`numpy`)  
- Pycaw (`pycaw`)  
- comtypes (`comtypes`)  
- Mediapipe (used in `HandTrackingModule`)  

Install the dependencies using pip:

```bash
pip install opencv-python numpy pycaw comtypes mediapipe
```

## File Structure
```
HandMotionCounting/
│
└─ dist/
   └─ img/               # Images for finger counting overlay
   └─ src/
      ├─ HandTrackingModule.py  # Custom module for hand detection and landmark tracking
      ├─ FingerCounting.py     # Script for counting fingers and displaying images
      ├─ HandTrackingMin.py     # Script for minimum code to detect hands
      └─ VolumeHandControl.py      # Script for controlling system volume with hand gestures
```

## How to Use
### Finger Counting

Ensure the folder HandMotionCounting/dist/img contains images named for each finger count.
Run the script:
```
python finger_counting.py
```

Show your hand to the camera. The program will detect the number of raised fingers and display the corresponding image and count.

### Volume Control
Run the script:
```
python volume_control.py
```

Use your thumb and index finger to control the system volume:
Closer together → Lower volume
Further apart → Higher volume
The video feed will show a volume bar and percentage.

## Notes

* Make sure your camera is working.
* Lighting conditions may affect hand detection accuracy.
* The hand detection is based on Mediapipe landmarks; avoid obstructing your hand.
* The volume control uses the Pycaw library, which works on Windows only.

## Screenshots

<img width="1917" height="1016" alt="image" src="https://github.com/user-attachments/assets/33d5f6d2-72cb-42f7-bbcb-44b0e7e4efc7" />


<img width="1917" height="1017" alt="image" src="https://github.com/user-attachments/assets/7f0d6430-fe14-4906-bc31-06a1d13f6650" />

## License
MIT
