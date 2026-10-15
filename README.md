# Weapon Detection Using OpenCV

A small Python demo that uses an OpenCV Haar cascade to highlight possible guns in webcam footage or a video file. It includes two Jupyter notebooks: one for a local webcam and one for a video clip.

> **Research/demo only.** This project can produce false detections or miss weapons. Do not use it as the sole basis for security, emergency, or law-enforcement decisions.

## What’s included

```text
Weapon-Detection-Using-OpenCV/
├── cascade.xml                 # Haar cascade classifier
├── Real time gun detection.ipynb
├── gun detection.ipynb          # Video-file example
└── README.md                    # Original project notes
```

The video notebook expects a clip at `data/gun4_3.mp4`. That clip and the training dataset described in the original notes are not included in this repository.

## Requirements

- Python 3
- A webcam for the live demo, or a video clip for the file-based demo
- OpenCV, NumPy, and imutils
- Jupyter Notebook

## Setup

Clone the repository and enter the project directory:

```bash
git clone https://github.com/Symmetry7/weapon-detection-.git
cd weapon-detection-/Weapon-Detection-Using-OpenCV
```

Create and activate a virtual environment (optional but recommended), then install the packages:

```bash
python -m venv .venv
```

Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

macOS/Linux:

```bash
source .venv/bin/activate
```

Install dependencies and Jupyter:

```bash
python -m pip install opencv-python numpy imutils notebook
```

## Run the webcam demo

From `Weapon-Detection-Using-OpenCV`, start Jupyter and open the live notebook:

```bash
jupyter notebook "Real time gun detection.ipynb"
```

Run the first code cell. The notebook reads camera index `0`, draws a box around cascade detections, and prints whether it detected a gun when the cell ends. Press **q** in the OpenCV video window to stop. Your operating system may ask you to allow camera access.

## Run the video demo

Place a video file at `Weapon-Detection-Using-OpenCV/data/gun4_3.mp4`, then open and run the first cell of:

```bash
jupyter notebook "gun detection.ipynb"
```

The notebook reads that file, displays detections in an OpenCV window, and exits when the video ends or you press **q** in the window. To use another clip, change the path passed to `cv2.VideoCapture` in the notebook.

## Notes and limitations

- Run the notebooks locally in a desktop session; they use `cv2.imshow` for display.
- The classifier file is loaded using the relative path `cascade.xml`, so start Jupyter from this project directory.
- The original project notes describe a dataset of 255 gun images, but the dataset and training code are not included here.
- This is a basic Haar cascade demonstration, not a validated or production-ready threat detection system. Performance depends on the classifier, image quality, lighting, camera angle, and distance.

## Acknowledgements

The project notes cite prior work on OpenCV object detection and real-time object detection with OpenCV. See the original notes in [`Weapon-Detection-Using-OpenCV/README.md`](Weapon-Detection-Using-OpenCV/README.md) for the references and project background.
