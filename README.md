# Sign-Language-Prediction-for-Deaf-Dumb-and-Blind
This application is a real-time American Sign Language (ASL) recognition system that translates hand gestures into text and speech. It combines computer vision for gesture recognition with natural language processing for word prediction and auto-correction.
# ASL Recognition System - README

## Overview
This application is a real-time American Sign Language (ASL) recognition system that translates hand gestures into text and speech. It combines computer vision for gesture recognition with natural language processing for word prediction and auto-correction.

## Features
- Real-time ASL letter recognition (A-Z)
- Hand skeleton visualization
- Word completion suggestions
- Next-word prediction using language modeling
- Auto-correction for misspelled words
- Text-to-speech output
- Space and backspace gesture controls
- Adjustable confidence threshold

## Technology Stack

### Core Technologies
- **Python 3.x** - Primary programming language
- **OpenCV (cv2)** - Computer vision for video capture and image processing
- **TensorFlow/Keras** - Deep learning model for ASL recognition
- **NLTK** - Natural language processing for word suggestions
- **SymSpellPy** - Fast spelling correction
- **pyttsx3** - Text-to-speech conversion
- **Tkinter** - Graphical user interface

### Computer Vision & Hand Tracking
- **cvzone.HandTrackingModule** - Hand landmark detection
- Custom hand skeleton visualization
- Gesture recognition for space and backspace

### Machine Learning Models
1. **ASL Recognition Model** (`best_model.h5`)
   - Input: 55x55 grayscale hand images
   - Output: 26 classes (A-Z)
   - Architecture: Likely a CNN (Convolutional Neural Network)

2. **Language Model** (`language_model.pkl`)
   - N-gram model (trigrams) trained on Brown Corpus
   - Used for next-word prediction
   - Automatically trained if not present
  
### Actual usage
![Before Autocorrection](path/to/before.png)
![After Autocorrection](path/to/after.png)

## Installation

### Prerequisites
- Python 3.7+
- pip package manager

### Steps
1. Clone the repository:
   ```bash
   git clone [repository-url]
   cd [repository-directory]
   ```

2. Install required packages:
   ```bash
   pip install -r requirements.txt
   ```

   Or manually install:
   ```bash
   pip install opencv-python tensorflow nltk symspellpy pyttsx3 Pillow
   ```

3. Download NLTK data:
   ```python
   import nltk
   nltk.download('words')
   nltk.download('brown')
   ```

4. Place the ASL model (`best_model.h5`) in the project directory

## Usage
Run the application:
```bash
python asl_app.py
```


### Interface Guide
- **Camera Feed**: Shows live video with hand detection
- **Hand Skeleton**: Displays detected hand landmarks
- **Recognition Info**:
  - Predicted letter and confidence
  - Current gesture detected
  - Sentence being constructed
- **Word Completion**: Suggestions for completing current word
- **Next Word Prediction**: Likely next words based on context
- **Controls**:
  - Speak: Read current sentence aloud
  - Clear: Reset the sentence
  - Space/Backspace: Manual controls
  - Auto-Correct: Correct last word

### Gesture Controls
- **Space**: Open hand (all fingers extended)
- **Backspace**: Thumb out (only thumb extended)

## Model Details

### ASL Recognition Model
- Input: 55x55 grayscale images of hands
- Output: Probability distribution over 26 letters (A-Z)
- Confidence threshold adjustable via slider (default: 0.80)

### Language Model
- Trained on Brown Corpus
- Uses trigrams for context-aware prediction
- Automatically generates if not found

## Performance Notes
- Works best with good lighting and clear hand visibility
- Requires webcam with decent resolution
- May need tuning of confidence threshold for different environments

## Future Improvements
- Support for numbers and punctuation
- Additional gestures for common commands
- Improved language model with larger vocabulary
- User customization and training options

## Acknowledgments
- NLTK corpus data
- SymSpellPy for efficient spelling correction
- CVZone for hand tracking utilities
