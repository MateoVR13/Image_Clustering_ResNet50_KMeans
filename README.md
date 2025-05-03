# Image Clustering with ResNet50 and K-Means

An efficient tool that uses ResNet50 CNN and K-means clustering to automatically organize and group similar images. This project leverages deep learning feature extraction and unsupervised learning to create meaningful image clusters without requiring labeled data.

## Overview

This project provides a streamlined approach to automatically organizing image collections by:

1. Using a pre-trained ResNet50 convolutional neural network to extract meaningful features from images
2. Applying K-means clustering to group similar images based on these extracted features
3. Organizing the clustered images into separate folders for easy review

Ideal for photographers, digital asset managers, content creators, or any project requiring intelligent image organization.

## Features

- **Deep Feature Extraction**: Leverages ResNet50 CNN pre-trained on ImageNet to extract high-level image features
- **Unsupervised Learning**: Groups similar images without requiring labeled data
- **Customizable Clusters**: Adjust the number of clusters based on your specific needs
- **Organized Output**: Automatically saves clustered images in separate directories
- **Compatible with Various Image Formats**: Works with JPG, JPEG, PNG, BMP, and TIFF files

## Requirements

- Python 3.7+
- TensorFlow/Keras
- scikit-learn
- NumPy
- PIL (Python Imaging Library)
- Google Colab (for the notebook implementation)

## Installation

### Option 1: Run in Google Colab
The easiest way to use this project is through Google Colab:

1. Upload the `Image_Clustering_ResNet50_KMeans.ipynb` notebook to Google Colab or go to https://colab.research.google.com/drive/1_No7tWnqRGWWVMx5_4lkNj4K8pdLBl59?usp=sharing
2. Mount your Google Drive (the notebook includes code for this)
3. Upload your images to a folder in your Google Drive
4. Update the input folder path in the notebook to point to your images

### Option 2: Local Installation
To run locally:

```bash
# Clone the repository
git clone https://github.com/yourusername/image-clustering-resnet50-kmeans.git
cd image-clustering-resnet50-kmeans

# Install required packages
pip install tensorflow scikit-learn numpy pillow
```

## Usage

1. **Prepare your images**
   - Place all images you want to cluster in a single directory

2. **Set paths and parameters**
   - Update the `input_folder` path to your images directory
   - Set `output_folder` to your desired destination
   - Adjust `n_clusters` to the number of groups you want to create

3. **Run the clustering**
   ```python
   input_folder = '/path/to/your/images'
   output_folder = '/path/to/output/directory'
   
   find_and_cluster_images(input_folder, output_folder, n_clusters=5)
   ```

4. **Review results**
   - Clustered images will be organized in numbered directories inside your output folder

## How It Works

1. **Feature Extraction**: The pre-trained ResNet50 model (without the classification layer) processes each image to extract a 2048-dimensional feature vector that represents high-level image characteristics.

2. **Dimensionality Reduction**: These feature vectors capture the essence of each image in a way that's much more meaningful than raw pixel values.

3. **K-means Clustering**: The extracted features are grouped using K-means clustering, which finds natural groupings in the data.

4. **Output Organization**: Images are copied to cluster-specific folders based on their assigned cluster.

## Customization

- **Change Feature Extractor**: You can replace ResNet50 with other models like VGG16, InceptionV3, or EfficientNet
- **Clustering Algorithm**: K-means can be replaced with other clustering algorithms like DBSCAN or hierarchical clustering
- **Preprocessing**: Add custom preprocessing steps for your specific image collection

## Performance Notes

- Processing time depends on the number, size of images and GPU capacity
- For large image collections, consider processing in batches
- The notebook is optimized to run on Google Colab's GPU for faster processing

## Limitations

- K-means requires specifying the number of clusters in advance
- Very large image collections may require additional optimization
- The quality of clustering depends on the diversity and characteristics of your image collection

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- [ResNet50](https://keras.io/api/applications/resnet/) pre-trained model from Keras Applications
- Inspired by various image clustering techniques in computer vision

## Author

Mateo Vergara

---

If you find this project useful, please consider starring the repository on GitHub.
