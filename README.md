# Object Measurement System

A computer vision-based application for real-time object measurement using camera input. This project provides both basic and advanced measurement capabilities, allowing users to measure objects in real-time with high accuracy using reference objects for calibration.

## 🚀 Features

- **Real-time Measurement**: Live camera feed with instant object measurement
- **Reference-based Calibration**: Uses A4 paper or other reference objects for accurate scaling
- **Multiple Detection Methods**: Contour-based and color-based object detection
- **Advanced Processing**: Edge detection, morphological operations, and contour filtering
- **Webcam & Image Support**: Works with live camera feed or static images
- **Precise Calculations**: Sub-pixel accuracy with perspective transformation
- **Visual Feedback**: Real-time display of measurements with arrows and labels

## 📋 Prerequisites

- Python 3.7+
- OpenCV 4.5+
- NumPy
- Webcam or camera device
- Reference object (A4 paper recommended)

## 🛠️ Installation

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd objectMeasurement
   ```

2. **Install required packages:**
   ```bash
   pip install -r requirements.txt
   ```

   Or install manually:
   ```bash
   pip install opencv-python numpy
   ```

3. **Ensure camera access:**
   - Connect your webcam or camera
   - Grant camera permissions to the application

## 🚀 Usage

### Basic Measurement (main.py)

1. **Run the basic measurement application:**
   ```bash
   python main.py
   ```

2. **Setup:**
   - Place an A4 paper (or reference object) in the camera view
   - Ensure good lighting and clear visibility
   - The system will automatically detect the reference object

3. **Measurement:**
   - Objects detected within the reference area will be measured
   - Measurements are displayed in centimeters
   - Press 'ESC' to exit

### Advanced Measurement (advanced_measurement.py)

1. **Run the advanced measurement application:**
   ```bash
   python advanced_measurement.py
   ```

2. **Features:**
   - Color-based object detection
   - Edge detection algorithms
   - Advanced contour filtering
   - Measurement history tracking
   - Customizable parameters

## 🏗️ Project Structure

```
objectMeasurement/
├── main.py                    # Basic measurement application
├── advanced_measurement.py    # Advanced measurement with multiple detection methods
├── utlis.py                   # Utility functions for image processing
├── 1.jpg                      # Sample reference image
├── requirements.txt            # Python dependencies
└── README.md                  # This file
```

## 🔧 Technical Details

### Core Components

#### 1. **Reference Object Detection**
- **A4 Paper Detection**: Automatically detects A4 paper as reference
- **Perspective Transformation**: Corrects camera angle distortion
- **Scale Calculation**: Converts pixel measurements to real-world units

#### 2. **Object Detection Methods**

**Contour-based Detection:**
- Edge detection using Canny algorithm
- Morphological operations for noise reduction
- Contour filtering by area and shape
- Polygon approximation for object boundaries

**Color-based Detection:**
- HSV color space segmentation
- Multiple color range support (red, green, blue, yellow, purple)
- Morphological operations for clean masks

#### 3. **Measurement Pipeline**
1. **Calibration**: Reference object detection and scaling
2. **Preprocessing**: Image enhancement and noise reduction
3. **Detection**: Object identification and contour extraction
4. **Measurement**: Distance calculation and unit conversion
5. **Visualization**: Real-time display with measurements

### Key Functions

- **`getContours()`**: Detects and filters contours with customizable parameters
- **`warpImg()`**: Applies perspective transformation for angle correction
- **`findDis()`**: Calculates Euclidean distance between points
- **`reorder()`**: Reorders corner points for consistent processing

## 📐 Measurement Process

### 1. **Calibration Phase**
- Place A4 paper (21cm × 29.7cm) in camera view
- System automatically detects paper boundaries
- Calculates pixels-per-cm ratio for accurate scaling

### 2. **Object Detection**
- Detects objects within the calibrated area
- Filters objects by size and shape
- Applies contour analysis for precise boundaries

### 3. **Measurement Calculation**
- Measures width and height of detected objects
- Converts pixel measurements to centimeters
- Displays real-time measurements with visual indicators

## ⚙️ Configuration

### Camera Settings
```python
cap.set(3, 1920)    # Width: 1920 pixels
cap.set(4, 1080)    # Height: 1080 pixels
cap.set(10, 160)    # Brightness: 160
```

### Detection Parameters
```python
minArea = 50000      # Minimum contour area for reference
filter = 4           # Number of corners for object detection
scale = 3            # Scaling factor for reference object
```

### Advanced Parameters
```python
canny_low = 50       # Lower threshold for edge detection
canny_high = 150     # Upper threshold for edge detection
min_area = 300       # Minimum object area
max_area = 100000    # Maximum object area
```

## 🎯 Use Cases

- **Product Quality Control**: Measure manufactured parts
- **Architectural Planning**: Room and furniture measurements
- **E-commerce**: Product dimension verification
- **Education**: Interactive measurement demonstrations
- **Research**: Computer vision and measurement studies

## 🐛 Troubleshooting

### Common Issues

1. **Camera not detected**
   - Check camera connections
   - Verify camera permissions
   - Try different camera indices (0, 1, 2...)

2. **Poor measurement accuracy**
   - Ensure good lighting conditions
   - Clean camera lens
   - Use high-quality reference objects
   - Maintain proper camera distance

3. **Objects not detected**
   - Adjust `minArea` and `maxArea` parameters
   - Check lighting and contrast
   - Verify object size relative to reference

4. **Performance issues**
   - Reduce camera resolution
   - Close unnecessary applications
   - Use lighter detection algorithms

### Performance Tips

- **Lighting**: Ensure consistent, bright lighting
- **Camera Position**: Maintain stable camera position
- **Reference Object**: Use high-contrast reference objects
- **Object Size**: Objects should be clearly visible in frame

## 🔮 Future Enhancements

- [ ] **Machine Learning Integration**: AI-powered object recognition
- [ ] **3D Measurement**: Depth sensing and 3D reconstruction
- [ ] **Mobile Application**: Cross-platform mobile support
- [ ] **Cloud Processing**: Remote measurement capabilities
- [ ] **Database Integration**: Measurement history and analytics
- [ ] **API Development**: RESTful API for integration
- [ ] **Multi-camera Support**: Stereo vision and calibration
- [ ] **Real-time Streaming**: Web-based measurement interface

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **OpenCV** for computer vision capabilities
- **NumPy** for numerical computing
- **Computer Vision Community** for algorithms and techniques
- **Open Source Contributors** for continuous improvements

## 📞 Support

For questions, issues, or contributions:
- Open an issue on GitHub
- Check the troubleshooting section above
- Review the code examples and documentation

## 🔗 Related Projects

- **Background Remover**: Image segmentation and background removal
- **Hand Tracking**: Gesture recognition and hand pose estimation
- **Traffic Sign Detection**: Road sign recognition and classification
- **Object Detection**: YOLO-based real-time object detection

---

**Happy measuring! 📏✨**
