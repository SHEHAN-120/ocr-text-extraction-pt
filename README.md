# OCR with Python and Tesseract

## Overview

This project demonstrates how I used **Tesseract OCR** with **Python** in Google Colab to extract and analyze text from images in Portuguese. The workflow includes text recognition, preprocessing, and visualization to explore results and highlight specific terms.

---

## Tools & Technologies Used

* **Google Colab** – main environment for running all experiments
* **Tesseract OCR** – text extraction engine
* **Pytesseract** – Python wrapper for Tesseract
* **spaCy** – for text preprocessing, stopword removal, and entity recognition
* **Matplotlib** – image visualization
* **WordCloud** – for visualizing frequent words
* **OpenCV** – image handling and annotation
* **Pillow (PIL)** – adding text overlays to images

---

## Workflow Summary

1. Mounted Google Drive and loaded image dataset.
2. Performed OCR using Tesseract with the Portuguese language model.
3. Extracted and stored all recognized text into a single `.txt` file.
4. Cleaned and preprocessed the text (lowercasing, removing stopwords, etc.).
5. Generated word clouds to visualize common words.
6. Highlighted searched terms (like *computador* or *sopa*) directly in the original images.
7. Saved all processed images in a new output directory.

---

## Challenges Faced

* **Model Data Loading:** The Portuguese `por.traineddata` file initially failed to load correctly due to a URL issue; it required using the `?raw=true` link format.
* **File Path Errors:** Some file paths with spaces caused issues when copying images from Google Drive.
* **Text Encoding Problems:** Special Portuguese characters like *ç* and *ã* sometimes appeared incorrectly in the OCR output.
* **Confidence Filtering:** Tesseract often returned low-confidence detections, so I set a threshold to improve accuracy.
* **Performance in Colab:** Handling multiple high-resolution images caused Colab memory warnings, requiring image resizing and batch processing.

---

## Insights

* Preprocessing with **spaCy** improved the quality of textual analysis.
* Using **WordClouds** was an effective way to visualize frequently occurring words.
* Bounding boxes from **pytesseract.image_to_data()** provided accurate word-level positioning for highlighting terms.

---

## Output Summary

* Text extracted from all images saved in `results_ocr.txt`.
* Highlighted and processed images stored in `/content/processed_images/`.
* Word clouds and NER visualizations displayed in Colab.



## License

This project is open-source and available under the [MIT License](LICENSE).
