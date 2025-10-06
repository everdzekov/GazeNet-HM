# M-Gaze Dataset

A multimodal eye gaze estimation dataset featuring synchronized RGB, Depth, and Infrared modalities for robust gaze tracking research.

## 📊 Dataset Overview

M-Gaze is a comprehensive multimodal dataset designed to advance research in robust eye gaze estimation under varying environmental conditions. The dataset contains synchronized RGB, Depth, and Infrared image triplets with precise gaze direction annotations.

Key Specifications:
- 15 participants (10 male, 5 female, aged 22-35)
- Multimodal data: Synchronized RGB, Depth, and IR streams
- 50,000+ synchronized triplets with ground-truth gaze vectors
- Diverse conditions: Multiple lighting scenarios and head poses
- Real-world variations: Includes participants with prescription glasses
- African ethnicity representation: Addresses demographic diversity gaps

## 🔬 Data Collection

### Hardware Setup
- Sensor: Intel RealSense D455 depth camera
- RGB: 640×480 resolution, 30 FPS, sRGB color space
- Depth: Infrared stereo depth, aligned with RGB
- IR: Left imager infrared stream

### Collection Protocol
- Lighting conditions: Normal office, dim light, and backlit scenarios
- Head poses: Frontal, ±30° yaw, ±15° pitch variations
- Gaze targets: Moving dot covering wide gaze angles
- Calibration: 9-point grid calibration sequence

## 📁 Dataset Structure
M-Gaze/
├── participants/
│ ├── P001/
│ │ ├── rgb/ # RGB images (.jpg)
│ │ ├── depth/ # Depth maps (.png)
│ │ ├── infrared/ # IR images (.png)
│ │ └── calibration/ # Calibration sequences
├── annotations/
│ ├── gaze_vectors.csv # Ground truth gaze directions
│ ├── participant_info.csv # Demographic information
│ └── collection_metadata.csv # Session parameters
└── docs/
└── datasheet.pdf # Detailed collection protocol

## 📄 File Formats & Annotations

### Image Specifications
- RGB: JPEG format, 640×480 resolution
- Depth: 16-bit PNG, depth in millimeters
- IR: 8-bit PNG, normalized intensity

### Annotation Schema
Each entry in `gaze_vectors.csv` contains:
- `participant_id`: Unique participant identifier
- `frame_id`: Corresponding image frame
- `gaze_yaw`: Gaze yaw angle in radians
- `gaze_pitch`: Gaze pitch angle in radians
- `head_yaw`: Head yaw angle in degrees
- `head_pitch`: Head pitch angle in degrees
- `lighting_condition`: Lighting scenario identifier
- `glasses`: Boolean indicating glasses presence

## 💻 Usage Examples

### Basic Data Loading
```python
import pandas as pd
import cv2

# Load annotations
annotations = pd.read_csv('annotations/gaze_vectors.csv')

# Load corresponding images
rgb_img = cv2.imread('participants/P001/rgb/frame_001.jpg')
depth_map = cv2.imread('participants/P001/depth/frame_001.png', cv2.IMREAD_ANYDEPTH)
ir_img = cv2.imread('participants/P001/infrared/frame_001.png')
Recommended Preprocessing
python
# Eye region cropping (224×224)
# Depth/IR normalization to [0, 1] range
# RGB normalization using ImageNet statistics
# Face detection using MTCNN
📚 Citation
If you use M-Gaze in your research, please cite:
bibtex
Copy
Download
@article{verdzekov2025gazenet,
  title={Eye Gaze Detection Using a Hybrid Multimodal Deep Learning Model for Assistive Technology},
  author={Verdzekov, Emile Tatinyuy and Noumsi, Auguste Vigny and Mvogo, Joseph and Fono, Louis Aimé},
  journal={Applied Sciences},
  year={2025},
  publisher={MDPI}
}
📄 License
This dataset is released for academic research purposes only. Commercial use requires explicit permission.
📞 Contact & Support
Primary Contact: Emile Tatinyuy Verdzekov
Email: apolokange@yahoo.com/ verdzekov.emile@uniba.cm
Tel: +237 652 47 61 60
GitHub Repository: everdzekov/GazeNet-HM
Issues: Please use GitHub Issues for technical questions and dataset-related inquiries.
🙏 Acknowledgments
We extend our gratitude to:
•	All participants who volunteered for data collection
•	The Department of Mathematics and Computer Science at University of Douala
•	The research team and technical staff involved in data curation
•	The open-source community for supporting multimodal research

