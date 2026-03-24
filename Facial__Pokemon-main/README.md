## Overview

This project focuses on : 
Implementing a machine learning pipeline that matches human images to the most similar Pokémon based on visual features using deep learning models like VGG16.

The project involves data scraping, feature extraction using pre-trained models, and image generation using techniques like GANs and VAEs.

## Features

1. **Pokémon Data Extraction:**
   - Scrapes Pokémon names, forms, and types from the [Bulbapedia National Pokédex page](https://bulbapedia.bulbagarden.net).
   - Downloads associated images and saves them in the format `#_Name_Form.png`.

2. **Image Feature Extraction:**
   - Uses the VGG16 model to extract visual features from both Pokémon and human images.
   - Compares these features using cosine similarity to find the most similar Pokémon for each human image.

3. **Background Removal:**
   - Employs the `rembg` library to remove the background from images before feature extraction.

4. **Generative Models:**
   - Implements a Variational Autoencoder (VAE) to learn Pokémon image representations.
   - Uses a Conditional Generative Adversarial Network (cGAN) for generating images conditioned on the human image features.

## Tools and Libraries Used

- **Web Scraping:** `requests`, `BeautifulSoup`
- **Data Handling:** `pandas`, `numpy`
- **Deep Learning:**
  - **VGG16** for feature extraction (`tensorflow.keras`)
  - **Variational Autoencoder (VAE)**
  - **Conditional GAN (cGAN)** for image generation
- **Image Processing:** `PIL`, `rembg` for background removal, `OpenCV` for image preprocessing
- **Metrics:** Cosine similarity for feature comparison
- **Plotting and Visualization:** `matplotlib`

## Project Workflow

### 1. Data Scraping
- Extracts Pokémon names, types, forms, and image URLs from Bulbapedia.
- Stores data in a structured CSV format and saves images.

### 2. Feature Extraction
- Loads human and Pokémon images.
- Extracts features using the pre-trained VGG16 model.
- Computes similarity between human and Pokémon features using cosine similarity.

### 3. Generative Models
- **VAE:** Learns a compact representation of Pokémon images and reconstructs them.
- **cGAN:** Generates new Pokémon images conditioned on human features.

## Example Output

- **Pokémon Data:** CSV containing Pokémon information (names, forms, types).
- **Most Similar Pokémon Matches:** A list mapping human images to their most similar Pokémon counterparts.
