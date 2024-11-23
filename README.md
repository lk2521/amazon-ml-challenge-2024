# Amazon ML Challenge 2024 - Solution Documentation

## Overview

This repository contains the solution for the Amazon ML Challenge 2024, where we worked as a team to address a challenging problem involving information extraction from OCR data. The problem required leveraging computer vision and natural language processing techniques to extract product attributes accurately.

We secured the 74th position on the final leaderboard with a score of 0.583. This document outlines our approach, methodologies, and key takeaways from the competition.

## Final Leaderboard Rank: **74th**
**Score**: 0.583  
Team Members:  
- Lavesh Kadam  
- Rushikesh Khandetod  
- Mannan Thakur  
- Archisman Bera  

---

## Introduction
The **Amazon ML Challenge 2024** was an exciting opportunity to solve real-world problems in machine learning. The competition focused on extracting and understanding entity information from product images. Our goal was to extract precise attribute values, such as `item_weight`, `item_volume`, `height`, `width`, etc., from noisy and unstructured text extracted from product images.

---

## Approach

### 1. **OCR for Text Extraction**
We used **PaddleOCR** for extracting text from images. PaddleOCR provided reliable and efficient text detection and recognition, forming the foundation for further processing.

### 2. **Regex for Entity Extraction**
For extracting structured entity values:
- We created regex patterns for each entity type (e.g., `item_weight`, `voltage`, `wattage`) based on their expected patterns in text.
- Units such as `cm`, `kg`, `ml`, etc., were mapped to standardized forms for consistency.

### 3. **Computer Vision for Dimensions**
For extracting `height`, `width`, and `depth`:
- **Edge Detection**: We applied edge detection to identify straight lines in images.
- **Bounding Box Assignment**:
  - For 2D objects: The dimension near the **vertical edge** was assigned as the `height`.
  - For 3D objects: Remaining dimensions were heuristically assigned as `width` and `depth`.

This hybrid approach worked well for various product images, particularly for distinguishing between 2D and 3D objects.

---

## Key Challenges
1. **Noisy Text Extraction**: OCR outputs included irrelevant information, requiring robust post-processing.
2. **Ambiguity in Dimensions**: Differentiating between `height`, `width`, and `depth` in 3D product images was non-trivial.
3. **Time Constraints**: Balancing computational efficiency with accuracy under tight deadlines.

---

## Results
Despite the challenges, our solution achieved a **final score of 0.583**, placing **74th** on the leaderboard. This demonstrates the strength of combining traditional approaches like regex and CV with efficient preprocessing.

---

## Repository Structure
- **`Data/`**: Main test data csv file we used in notebook.
- **`amazon-ml-challenge-complete-code.ipynb`**: Complete Jupyter notebook for experimentation and visualization.
- **`README.md`**: Project documentation.

---

## Reflections
This competition was a valuable learning experience. We explored a blend of OCR, regex, and computer vision techniques to achieve competitive results without relying on heavy transformer-based models. While there's room for improvement, we are proud of the innovative solutions our team developed.

---

## Acknowledgments
We extend our gratitude to **Amazon** for organizing the challenge and providing such a unique problem statement. Special thanks to our team for their dedication and teamwork throughout the competition.

---

Feel free to explore the repository and reach out with any questions or feedback! 🚀
