# Gender and Age Detector

[![Python](https://img.shields.io/badge/Python-3.6%2B-blue)](https://www.python.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green)](https://opencv.org/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A deep learning-based gender and age detection system that can identify the gender and approximate age of a person from a single image or webcam feed.

## 📋 Table of Contents
- [Objective](#objective)
- [About the Project](#about-the-project)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)
- [Model Accuracy and Limitations](#model-accuracy-and-limitations)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Objective
To build a gender and age detector that can approximately guess the gender and age of the person (face) in a picture or through webcam.

## 📝 About the Project
In this Python Project, we use Deep Learning to accurately identify the gender and age of a person from a single image of a face. The models used were trained by [Tal Hassner and Gil Levi](https://talhassner.github.io/home/projects/Adience/Adience-data.html).

The system can predict:
- Gender: 'Male' or 'Female'
- Age ranges: (0 – 2), (4 – 6), (8 – 12), (15 – 20), (25 – 32), (38 – 43), (48 – 53), (60 – 100)

Due to factors like makeup, lighting, obstructions, and facial expressions, exact age prediction is challenging. Therefore, this is implemented as a classification problem rather than regression.

## 📊 Dataset
The project uses the [Adience dataset](https://www.kaggle.com/ttungl/adience-benchmark-gender-and-age-classification), which serves as a benchmark for face photos. The dataset includes:
- 26,580 photos of 2,284 subjects
- Eight age ranges
- Various real-world imaging conditions (noise, lighting, pose, appearance)
- Images collected from Flickr albums under Creative Commons (CC) license
- Dataset size: ~1GB

## 📁 Project Structure
```
Gender-and-Age-Detection/
├── src/                      # Source code
│   └── detect.py            # Main detection script
├── models/                   # ML models
│   ├── opencv_face_detector.pbtxt
│   ├── opencv_face_detector_uint8.pb
│   ├── age_deploy.prototxt
│   ├── age_net.caffemodel
│   ├── gender_deploy.prototxt
│   └── gender_net.caffemodel
├── examples/                 # Example images and results
│   ├── images/              # Test images
│   └── results/             # Detection results
├── tests/                   # Test cases
├── README.md                # Project documentation
├── requirements.txt         # Python dependencies
└── .gitignore              # Git ignore file
```

## 🚀 Installation

### Prerequisites
- Python 3.6 or higher
- pip (Python package installer)

### Steps
1. Clone the repository:
```bash
git clone https://github.com/SatyaJaiss/Gender-and-Age-Detection.git
cd Gender-and-Age-Detector
```

2. Install the required dependencies:
```bash
pip install -r requirements.txt
```

## 💻 Usage

### Image Detection
1. Place your test images in the `examples/images/` directory
2. Run the detection script:
```bash
python src/detect.py --image <image_name>
```

### Webcam Detection
1. Run the script without any arguments:
```bash
python src/detect.py
```
2. Press `Ctrl + C` to stop the program execution

## 📸 Examples
**Note:** The images used in this repository are taken from Google and are royalty free.

### Example 1
```bash
python src/detect.py --image youngeMan1.jpg
Gender: Male
Age: 25-32 years
```
![Example 1](examples/results/Detecting age and gender youngeMen1.png)

### Example 2
```bash
python src/detect.py --image lady1.jpg
Gender: Female
Age: 8-12 years
```
![Example 2](examples/results/Detecting age and lady1.png)

### Example 3
```bash
python src/detect.py --image lady2.jpg
Gender: Female
Age: 25-32 years
```
![Example 3](examples/results/Detecting age and gender lady2.png)

### Example 4
```bash
python src/detect.py --image family.jpg
Gender: Male
Age: 25-32 years
Gender: Male
Age: 0-2 years
```
![Example 4](examples/results/Detecting age and gender family.png)

### Example 5
```bash
python src/detect.py --image boy1.jpg
Gender: Male
Age: 15-20 years
```
![Example 5](examples/results/Detecting age and gender man1.png)

## 📊 Model Accuracy and Limitations

### Accuracy
- Gender detection accuracy: ~86%
- Age range detection accuracy: ~45%

### Limitations
1. Performance depends on image quality and face visibility
2. Age prediction is approximate and falls within ranges
3. May not work well with:
   - Heavily occluded faces
   - Extreme lighting conditions
   - Non-frontal face angles
   - Very low resolution images

## 🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License
This project is licensed under the MIT License - see the LICENSE file for details.
