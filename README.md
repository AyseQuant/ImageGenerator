Fluorescent Yeast Cell Image Generator and Segmenter

This project is a Python application with a graphical user interface (GUI) built using Tkinter. It allows users to generate synthetic images of fluorescent yeast cells, apply segmentation to identify individual cells, and calculate and display properties of each segmented cell. The app is suitable for simulating and analyzing microscopy images in a user-friendly environment.

Features

Generate Synthetic Images: Create 1024x1024 (or custom size) images of fluorescent yeast cells with adjustable parameters.
Cell Segmentation and Analysis: Segment cells based on thresholding and calculate properties such as centroid, area, orientation, and roundedness.
User-Friendly Interface: Control image generation and segmentation parameters using an interactive Tkinter interface.
Display Side-by-Side: Visualize both the original generated image and the segmented image side-by-side for easy comparison.

The first notebook provides the code you can run on your computer
The second notebook preovides a GUI that allows you to enter specific settings to acquire the synthetic image.

Requirements

Python 3.7+
Required packages (install using pip):
numpy
pandas
matplotlib
scipy
Pillow
scikit-image
Setup and Installation
Clone or Download this repository to your local machine.

Install Dependencies:

pip install numpy pandas matplotlib scipy Pillow scikit-image


Run the Application:

python main.py

Usage

Parameters for Image Generation
Upon launching the application, you will be prompted to enter parameters for generating the synthetic image:

Image Width and Height: 

Dimensions of the image to be created, typically 1024x1024.
Number of Cells: The number of yeast cells to generate the image.
Average Diameter of Cells: Average diameter of each cell in pixels.
Variance in Diameter: Variability in cell diameter.
Background Noise Level: Adjusts the level of background noise in the image for a realistic appearance.
Image Generation and Segmentation Steps

Generate Image:

Click Generate Image to create the synthetic yeast cell image based on the specified parameters.
The generated image will appear on the left side of the interface.

Segment and Analyze:

The segmentation process applies thresholding and erosion to ensure cells are well-separated.
The segmented image with each cell labeled in a different color will appear on the right side of the interface.

Display Cell Properties:

After segmentation, the application will calculate properties for each cell, including centroid, area, orientation, major and minor axis lengths, eccentricity, perimeter, and mean intensity.
These properties are stored in a Pandas DataFrame and printed to the console. The roundedness of each cell is calculated to indicate shape circularity.

Code Overview

generate_varied_fluorescent_yeast_image()
Generates the synthetic yeast cell image. This function uses parameters like cell count, diameter, variance, and noise level to produce an image with randomly placed, fluorescent yeast cells.

segment_and_analyze()
Applies segmentation to the generated image, labeling each yeast cell and calculating its properties using regionprops_table. This function also uses erosion to prevent overlapping of cells.

display_segmented_image()
Uses label2rgb to apply a unique color to each labeled cell region for clear visualization of segmentation results.

Example Output
Below is an example of the data table produced by segmenting a generated image:

| Label | Centroid-0 | Centroid-1 | Area | Orientation | Major Axis Length | Minor Axis Length | Eccentricity | Perimeter | Mean Intensity | Roundedness |
|-------|------------|------------|------|-------------|-------------------|-------------------|--------------|-----------|----------------|-------------|
| 1     | 150.5      | 200.8      | 80   | 0.5 rad    | 10.5             | 9.2               | 0.6          | 36.0      | 220            | 0.89        |

Troubleshooting
Cells Overlapping: If cells appear too large or overlap, try adjusting the average diameter and variance parameters or increase the threshold value in the segment_and_analyze() function.
Tkinter Issues: If you encounter issues with the Tkinter window, ensure all packages are installed, and you are running the correct Python version (3.7+).
License
This project is licensed under the MIT License.

