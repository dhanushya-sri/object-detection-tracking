# yolov8-objection-detection

Lightweight example using YOLOv8 (Ultralytics) and OpenCV for realtime object detection on video. This repository contains a small demo script `yolov8_n_opencv.py` that runs a YOLOv8n model on a video stream and displays detections with class names and colored bounding boxes.

**Prerequisites**
- Python 3.8+ (3.10/3.11 recommended)
- `pip` for installing Python packages
- (Optional) A CUDA-enabled GPU and matching PyTorch build for faster inference

**Install**
- Install required packages from `requirements.txt`:

```powershell
pip install -r requirements.txt
```

**Quick Start / Usage**
- By default the demo script reads the video `inference/videos/input.mp4`, uses the model weights in `weights/yolov8n.pt`, and the class list in `utils/coco.txt`.

- Run the demo:

```powershell
python yolov8_n_opencv.py
```

- Controls:
  - Press `q` in the display window to quit.

**Configuration & Notes**
- Model weights: The script loads the model from `weights/yolov8n.pt`. If your weights are in a different location, update the path in `yolov8_n_opencv.py` (the `YOLO("weights/yolov8n.pt", "v8")` line).
- Class names: `utils/coco.txt` contains one class name per line. The script reads this file to display labels.
- Input source: The script currently uses `cv2.VideoCapture("inference/videos/input.mp4")`. To use a webcam, change it to `cv2.VideoCapture(0)` or set the desired camera index.
- Confidence threshold: The script passes `conf=0.45` to `model.predict()`. Adjust this in the source if needed.

**Repository Structure**
- `yolov8_n_opencv.py` - demo script using Ultralytics YOLO and OpenCV
- `requirements.txt` - Python dependencies
- `inference/` - sample `images/` and `videos/` input folders
- `utils/` - helper files including `coco.txt` and `weights/`
- `weights/` - model weights (e.g. `yolov8n.pt`)

**Troubleshooting**
- If OpenCV window does not open, ensure your environment supports GUI windows (on headless servers use an alternative display method or save frames to disk).
- If model import fails, confirm `ultralytics` is installed and that PyTorch is installed correctly for your platform (CPU vs GPU).

**Next steps / Improvements**
- Add CLI arguments to select `--source`, `--weights`, `--conf`, and `--save` for easier use.
- Add saving of output video/images.
- Add optional drawing/styling options and FPS display.

**Author / Contact**
- Repository: `yolov8-silva` (owner: DAVIDNYARKO123)

