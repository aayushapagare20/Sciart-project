# Image J Particle Counting in Drosophila cells

# Objective : The objective of this analysis was to perform automated detection and quantification of cells from microscopy cells of Drosophila melanogaster using Image J. The workflow focuses on isolating cellular regions of interest through threshold based segmentation and extracting quantitative parameters such as cell count, area, and morphology. 

 # Acquiring image
A raw fluorescent image of Drosophila melanogaster cells was obtained from publicly available datasets (e.g Cell profiler, Image J sample datasets and Opencell)

The selected image met the following criteria:
Clearly distinguishable cells
Minimal preprocessing
Sufficient contrast between cells and background 

The original image was stored without modification. Metadata such as staining type, imaging conditions and source were documented

# Step 1 : Opening and Pre processing and Image :

The image was opened in Image J using : File - Open
To standardize analysis:
Image - Type - 8 bit 

# Background Subtraction
To remove uneven illumination :
Process - Subtract Background

Rolling Ball Radius : 50 pixels
Light Background : Not selected

This enhances visbility of Drosophila cells/ nuclei by reducing background noise.

# Contrast Enhancement
To improve clarity of cellular structures :
Image- Adjust- Brightness/Contrast 

Auto adjustment applied
Manual refinement performed 

# Step 2: : Thersholding

To segment Drosophila cells from the background :
Image - Adjust - Threshold 
Method: Default/ Auto
Threshold adjusted to highlight cells while minimizing background
The image was converted into binary mask after applying thresholding

# Step 3 : Binary Processing and Cleanup 
Fill holes:
Ensures complete cell regions 
(Process - Binary - Fill holes)

Convert to mask:
(Process-binary-convert to mask)

Watershed Segmentation:
Separates overlapping or clustered Drosophila cells 
(Process-Binary-Watersged)

# Step 4 : Setting Measurements 

Measurement parameters selected using:
Analyze - Set Measurements

Parameters include: Area, Perimeter, Shape descriptions and Mean gray value
All measurements were recorded in pixel units

# Step 5 : Cell Analysis :

Cell detection performed using :
Analyze - Analyze Particles

Parameters :
Size : 50 - Infinity pixels
Circularity : 0.4-1.0
Options enabled : Display results, Summarize, Exclude on edges, Overlay

# Step 6 : Results

Export data 

Results saved as CSV file :
Cell count and measurements 

