# 🌊 Oil Spill Detection System

An innovative, comprehensive web application for detecting oil spills in images and videos using advanced YOLOv11 deep learning model. Built with Streamlit for an intuitive, user-friendly interface.

## ✨ Features

### 🎯 Core Capabilities
- **📸 Image Detection**: Upload single or multiple images for batch processing
- **🎥 Video Detection**: Process video files frame-by-frame with progress tracking
- **📹 Real-time Camera**: Live detection from webcam with real-time statistics
- **📊 Analytics Dashboard**: Comprehensive statistics, visualizations, and insights
- **⚙️ Customizable Settings**: Adjust confidence thresholds and preferences

### 🚀 Advanced Features
- **Batch Processing**: Handle multiple images simultaneously
- **Interactive Visualizations**: Plotly charts for confidence distributions and timelines
- **Export Options**: Download results in multiple formats (TXT, CSV, JSON)
- **Heatmap Overlays**: Visualize detection density
- **Coverage Analysis**: Calculate spill coverage percentages
- **Detection History**: Track and analyze detection patterns over time
- **Real-time Statistics**: Live metrics during processing
- **GPU Support**: Automatic GPU acceleration when available

## 📋 Requirements

- Python 3.10 or higher
- CUDA-capable GPU (optional, for faster processing)
- Webcam (optional, for real-time detection)

## 🛠️ Installation

### Option 1: Using Conda (Recommended)

1. **Create the conda environment:**
   ```bash
   conda env create -f environment.yml
   ```

2. **Activate the environment:**
   ```bash
   conda activate oil_spill
   ```

3. **Run the application:**
   ```bash
   streamlit run app.py
   ```

### Option 2: Using pip

1. **Create a virtual environment (optional but recommended):**
   ```bash
   python -m venv oil_spill_env
   source oil_spill_env/bin/activate  # On Windows: oil_spill_env\Scripts\activate
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the application:**
   ```bash
   streamlit run app.py
   ```

## 📁 Project Structure

```
oil_spill/
├── app.py                      # Main Streamlit application
├── best.pt                     # YOLOv11 trained model
├── pages/                      # Multi-page application pages
│   ├── 1_📸_Image_Detection.py
│   ├── 2_🎥_Video_Detection.py
│   ├── 3_📹_Real-time_Camera.py
│   ├── 4_📊_Analytics_Dashboard.py
│   └── 5_⚙️_Settings.py
├── utils/                      # Utility modules
│   ├── model_loader.py         # Model loading and caching
│   ├── image_processor.py      # Image processing functions
│   ├── video_processor.py      # Video processing functions
│   ├── visualizations.py       # Visualization utilities
│   └── report_generator.py     # Report generation
├── requirements.txt            # Python dependencies
├── environment.yml             # Conda environment file
└── README.md                   # This file
```

## 🎮 Usage

### Image Detection
1. Navigate to **📸 Image Detection** page
2. Upload one or more images (PNG, JPG, JPEG, BMP, TIFF)
3. Adjust confidence threshold in the sidebar
4. View detection results with bounding boxes
5. Export results in various formats

### Video Detection
1. Navigate to **🎥 Video Detection** page
2. Upload a video file (MP4, AVI, MOV, MKV, etc.)
3. Preview sample frames
4. Process the video (progress bar shows status)
5. Download annotated video and analysis reports

### Real-time Camera
1. Navigate to **📹 Real-time Camera** page
2. Click "Start Camera" button
3. View live detections with real-time statistics
4. Click "Stop Camera" when finished

### Analytics Dashboard
1. Navigate to **📊 Analytics Dashboard** page
2. View comprehensive statistics and visualizations
3. Analyze detection patterns over time
4. Export analytics data

## ⚙️ Configuration

### Model Settings
- **Confidence Threshold**: Adjust detection sensitivity (0.0 - 1.0)
- **Device**: Automatically uses GPU if available, falls back to CPU

### Application Settings
- Customize display preferences
- Configure export formats
- Adjust processing parameters

## 📊 Supported Formats

### Input
- **Images**: PNG, JPG, JPEG, BMP, TIFF
- **Videos**: MP4, AVI, MOV, MKV, FLV, WMV

### Output
- **Annotated Images/Videos**: With bounding boxes and labels
- **Text Reports**: Detailed detection information
- **CSV Files**: Structured data for analysis
- **JSON Files**: Machine-readable results

## 🔧 Technical Details

- **Model**: YOLOv11 (Ultralytics)
- **Framework**: PyTorch
- **Web Framework**: Streamlit
- **Visualization**: Plotly, Matplotlib
- **Image Processing**: OpenCV, PIL
- **Data Handling**: Pandas, NumPy

## 🎨 UI Features

- **Modern Design**: Clean, intuitive interface
- **Responsive Layout**: Works on different screen sizes
- **Custom Styling**: Enhanced visual appearance
- **Progress Indicators**: Real-time processing feedback
- **Interactive Charts**: Plotly visualizations
- **Color-coded Alerts**: Visual feedback for detections

## 🚀 Performance Tips

1. **Use GPU**: Ensure CUDA is available for faster processing
2. **Batch Processing**: Process multiple images together for efficiency
3. **Adjust Thresholds**: Lower confidence threshold for more detections (may include false positives)
4. **Video Resolution**: Lower resolution videos process faster

## 📝 Notes

- The model file (`best.pt`) must be in the project root directory
- First run may take longer as the model loads
- GPU acceleration significantly improves processing speed
- Large videos may take time to process - be patient!

## 🐛 Troubleshooting

### Model not loading
- Ensure `best.pt` exists in the project directory
- Check file permissions

### Camera not working
- Verify camera permissions
- Check if camera is being used by another application

### Slow processing
- Use GPU if available
- Reduce image/video resolution
- Process fewer images at once

### Import errors
- Ensure all dependencies are installed
- Activate the correct conda/virtual environment

### Pracice Codes brief descriptions
#### CODE 1 – Webcam Live Stream
- Captures video from the webcam and displays it in real time.
- Ends when the user presses 'q'.
#### CODE 2 – Save Webcam Frames
- Continuously captures webcam frames and saves each one as an image.
- Useful for dataset creation from live video.
#### CODE 3 – Load & Display Image
- Reads an image from disk and opens it in a display window.
- Waits for a key press before closing.
#### CODE 4 – Flip Image (Vertical / Horizontal / Both)
- Loads an image and generates flipped versions in all directions.
- Displays original and flipped copies in separate windows.
#### CODE 5 – Resize Image
- Resizes an image to 300×300 pixels and shows both versions.
- Optionally saves the resized output.
#### CODE 6 – Convert Image to Grayscale
- Converts a color image into grayscale using OpenCV.
- Displays both original and grayscale versions.
#### CODE 7 – Gaussian Blur
- Applies a 15×15 Gaussian blur to smooth an image.
- Used for noise reduction before further image processing.
#### CODE 8 – Draw Shapes & Text
- Creates a blank canvas and draws lines, rectangles, circles, and text.
- Great for learning OpenCV drawing functions.
#### CODE 9 – Binary Thresholding
- Converts a grayscale image into a binary (black & white) image.
- Separates foreground from background using intensity threshold.
#### CODE 10 – Canny Edge Detection
- Runs Canny edge detection on a grayscale image.
- Highlights boundaries and sharp intensity changes.
#### CODE 11 – Face Detection
- Uses Haar Cascade to detect faces in an image.
- Draws rectangles around detected face regions.
#### CODE 12 – Contour Detection
- Detects object boundaries using thresholding + findContours().
- Draws detected contours on the original image.
#### CODE 13 – Blue Color Detection (HSV Masking)
- Converts image to HSV and isolates blue-colored regions.
- Displays the mask and the filtered output.
#### CODE 14 – Foreground Extraction (GrabCut)
- Uses GrabCut algorithm to separate foreground from background.
- Outputs a clean cut-out of the main object.
#### CODE 15 – Real-Time Blue Object Tracking
- Tracks blue objects via webcam using HSV masking.
- Shows original frame, mask, and filtered tracking output.
#### CODE 16 – Erosion & Dilation
= Applies binary inverse threshold, then erosion and dilation.
- Shows how morphology refines shapes or removes noise.
### 📝 NLP + ML Codes
#### CODE 17 – Text Cleaning & Lemmatization
- Cleans text by removing noise, then tokenizes and lemmatizes it.
- Outputs meaningful words for NLP tasks.
#### CODE 18 – Sentiment Classification (TF-IDF + Logistic Regression)
- Builds a sentiment classifier using TF-IDF features.
- Evaluates model performance and predicts review sentiment.
#### CODE 19 – Grid Search Hyperparameter Tuning
- Uses GridSearchCV to optimize TF-IDF + Logistic Regression settings.
- Finds best-performing parameters and predicts on sample text.
#### CODE 20 – TF-IDF Vectorization Demo
- Converts sample documents into TF-IDF numerical vectors.
- Displays the vocabulary and TF-IDF matrix.
#### CODE 21 – SpaCy NER + POS + Lemma Extraction
- Identifies named entities, POS tags, lemmas, and noun chunks.
- Demonstrates multiple core SpaCy NLP features.
#### CODE 22 – Naive Bayes Text Classifier
- Converts text to Bag-of-Words and classifies sentiment using Naive Bayes.
- Prints evaluation metrics for model accuracy.
#### CODE 23 – Cosine Similarity (TF-IDF)
- Builds TF-IDF vectors and computes similarity between documents.
- Shows which texts are most alike.
#### CODE 24 – Topic Modeling (LDA using Gensim)
- Creates dictionary + corpus, then trains an LDA model on text data.
- Extracts hidden topics and displays top contributing words.
### Output Images
<div style="display: flex; gap: 10px;">
  <img src="https://github.com/sagarmamidala24/Sagar_OilSpillageProject_Nov2025/blob/main/oil%20spilt%20result/images_annotated/oil%20spill%20area.v2i.yolov12_1006_jpg.rf.30f9b433e6ce72177357c3be1ffa91bf_ann.jpg?raw=true" width="32%">
  <img src="https://github.com/sagarmamidala24/Sagar_OilSpillageProject_Nov2025/blob/main/oil%20spilt%20result/images_annotated/oil%20spill%20area.v2i.yolov12_1007_jpg.rf.b7a7b40cf6121889a4fc4848669c4ca3_ann.jpg?raw=true" width="32%">
  <img src="https://github.com/sagarmamidala24/Sagar_OilSpillageProject_Nov2025/blob/main/oil%20spilt%20result/masks/oil%20spill%20area.v2i.yolov12______thumb_fed_photo_jpg.rf.cee7658c0b82d45d6c2937d9cde0ffef_mask.png?raw=true" width="32%">
</div>

## 📄 License

This project is provided as-is for demonstration and research purposes.

## 🙏 Acknowledgments

- YOLOv11 by Ultralytics
- Streamlit for the web framework
- All open-source contributors

## 📧 Support

For issues, questions, or contributions, please refer to the project documentation or create an issue in the repository.

---

**Built with ❤️ for environmental protection and oil spill detection**

