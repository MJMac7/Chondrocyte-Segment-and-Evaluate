# Chondrocyte-Segment-and-Evaluate
University of Delaware MEEG467 final project on classifying, segmenting, and evaluation chondrocytes using machine learning. This project was done in ImageJ.


In order to use the code, follow the steps below.

First, install Fiji ImageJ.
Download link: https://imagej.net/software/fiji/downloads

Open ImageJ and click Help > Update. Wait for everything to update. Do not close window. Click Manage Update Sites, then check the box for StarDist. Now install all StarDist files.

Download both files in this repository

Now you are ready to use the framework to segment and evaluate chondrocytes

The following steps can be done manually, or can use the Macro included to reduce the amount of manual steps:

Fully Manual Steps:

Create a maximum projection of image stack
    Image > Stacks > Z Projection > Maximum
Open “Trainable Weka Segmentation” >Plugins > Segmentation >Trainable Weka
> Load Classifier > ChondrocyteClassifier
> Get Probability
> Image > Duplicate > Set “Range” to 1 > Uncheck “Duplicate Stack” > Click “Ok”
> Image > Type > 8 bit
> Image > Adjust > Threshold > Top Line 165, Bottom Line 255
> Analyze > Analyze Particles > Set range from 35-10,000 > uncheck pixel units box > Show: “Masks” > Check: Display Results, Add to Manager, Include holes, Overlay, Composite ROIs
> Plugins > StarDist > StarDist2D > Model: “Versatile” > Check “Normalize Image” Box  > Percentile Low: “0.5” > Percentile High: “95.7” > Probability/Score Threshold: “0.25” > Overlap Threshold: “0.4” > Output Type: “Both” > Do not touch Advanced Settings
> Analyze > Set Measurements > Check: “Mean Gray Value” and “Centroid”
> File > Open > Open your stacked image
> Find your “ROI Manager” Window > Click any random point > Hit CTRL + A on your keyboard > You should see all the masks highlighted throughout the entire stack
> On ROI Manager Window > Click “More” > “Multi Measure” > “Ok”
Wait a few minutes and the ROI Manger will produce a “Results” Window of all your data points. You can look at the standard FIJI/ImageJ toolbar to see the gray/purple progress bar
> Click on “Results” Window > File > Save As > Name your file
The file is saved as an Excel Spreadsheet


Using ImageJ Macro code included in this repository:

Create a maximum projection of image stack
Image > Stacks > Z Projection > Maximum
Open “Trainable Weka Segmentation” >Plugins > Segmentation >Trainable Weka
> Load Classifier > ChondrocyteClassifier
> Get Probability
> Plug ins > Macro > Edit > "IntermediateSteps" file
> Change the lines marked "EDIT" with your desired parameters
> Change the line 25 file pathway to the pathway of the image stack you want to analyze
> Run the macro
> Wait for macro to be done (will take several minutes)
> Click on “Results” Window > File > Save As > Name your file
The file is saved as an Excel Spreadsheet




