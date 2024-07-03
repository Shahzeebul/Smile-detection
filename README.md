Certainly! Here is a README file for your smile detection project:

---

# Smile Detection Using OpenCV

This project utilizes OpenCV's pre-trained Haar cascade classifiers to detect faces and smiles in real-time from a webcam feed. It draws rectangles around detected faces and smiles and labels the smiles accordingly.

## Features

- Real-time face detection
- Real-time smile detection within detected faces
- Drawing rectangles around detected smiles
- Labeling smiles with the text "Smile"

## Prerequisites

Before running the script, ensure you have the following installed:

- Python 3.x
- OpenCV library

You can install OpenCV using pip:

```bash
pip install opencv-python
```

## Usage

1. Clone the repository:

```bash
git clone https://github.com/yourusername/smile-detection.git
cd smile-detection
```

2. Run the script:

```bash
python detect_smile.py
```

The script will open your default camera and start detecting faces and smiles. Press 'q' to quit the program.

## Code Explanation

Here's a brief explanation of the main parts of the code:

- **Loading Haar Cascade Classifiers**: 
  ```python
  face_cascade = cv2.CascadeClassifier(cv2.data.haarcascades + 'haarcascade_frontalface_default.xml')
  smile_cascade = cv2.CascadeClassifier(cv2.data.haarcascades + 'haarcascade_smile.xml')
  ```

- **Capturing Video from Webcam**:
  ```python
  cap = cv2.VideoCapture(0)
  ```

- **Converting Frame to Grayscale**:
  ```python
  gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
  ```

- **Detecting Faces and Smiles**:
  ```python
  faces = face_cascade.detectMultiScale(gray, scaleFactor=1.1, minNeighbors=5, minSize=(30, 30))
  smiles = smile_cascade.detectMultiScale(roi_gray, scaleFactor=1.8, minNeighbors=20)
  ```

- **Drawing Rectangles and Adding Text**:
  ```python
  cv2.rectangle(frame, (x+sx, y+sy), (x+sx+sw, y+sy+sh), (0, 255, 0), 2)
  cv2.putText(frame, 'Smile', (x, y-10), cv2.FONT_HERSHEY_SIMPLEX, 0.9, (0, 255, 0), 2)
  ```

## Contributing

Feel free to fork this repository, make improvements, and submit pull requests. Your contributions are welcome!

## Example

![Screenshot (88)](https://github.com/Shahzeebul/Smile-detection/assets/104351775/bd50d174-676b-4ee9-8ee9-4b713da250d0)


---

You can modify the `git clone` URL with your actual GitHub repository URL once you upload the project.
