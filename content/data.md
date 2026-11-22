+++
date = '2026-11-20T19:46:55-06:00'
draft = false
title = ''
+++

## Data

In order to test the question of "how robust are our models to dust?", we need a dusty image set as well as a labelled ground truth to evaluate the predictions on. It would also be useful to have categories of light, medium and heavy dust to measure how predictions are affected by worse distortions. The dataset we are working with is the <a href="https://data.nasa.gov/dataset/ai4mars-a-dataset-for-terrain-aware-autonomous-driving-on-mars" target="_blank">AI4Mars</a> dataset, which consists of mostly clear images. Our goal is to 'dustify' this dataset to obtain additional dusty datasets to evaluate and compare our models on:

| Dataset | Dust level |
|---|---|
| No dust | Original images |
| Light | Lowest third of the dustification ranges |
| Medium | Middle third |
| Heavy | Highest third |

### 1. Source images: AI4Mars

We gathered data from the AI4Mars dataset provided for open access by <a href="https://data.nasa.gov/dataset/ai4mars-a-dataset-for-terrain-aware-autonomous-driving-on-mars" target="_blank">NASA</a>. This dataset includes ~35,000 images of Martian terrain captured by the *Curiosity*, *Opportunity*, and *Spirit* rovers. Classes for the images are soil, sand, big rock, and bedrock. The ground truth segmentations for these images were labeled via crowd sourcing and required three participants' agreement for each pixel to receive a classification. For this project, we used only the ~16,000 images from *Curiosity*'s (MSL) NavCam subset.

<img src="/docs/sem_overlay.png" alt="Example image from AI4Mars">

### 2. Studying real dust storms

Before developing the algorithm, we analyzed many real dust storm images on Mars to determine common characteristics. We identified that dust storms:

1. mimic the beige tint of the Martian environment,
2. contain sand particles,
3. have non-linear obscurity (that is, the farther away in the dust storm, the faster visibility decreases),
4. dull the color of the landscape,
5. create some blurring factor.

### 3. The dustification algorithm

The algorithm used to apply the dust filter (or "dustify" the images) applies a series of filters, masks, and kernels to the original image.

<img src="/docs/dustification_steps.png" alt="Dustification algorithm steps">

In words, the algorithm:

1. Develops a gradient mask (Image 2)
2. Combines the mask with a tint
3. Overlays the tint mask to create a gradient beige tint over the whole image (Image 3)
4. Creates a randomized Gaussian noise mask to mimic sand in the dust storm (Image 4)
5. Creates a Gaussian blur kernel (Image 6)
6. Composes the original image with the noise mask (Image 5) and then the blur (Image 7)
7. Reduces contrast to dull the saturation of the dust storm (Image 8)

### 4. Finding parameter ranges

<img src="/docs/dust_filter_tool_comparison.png" alt="Dust filter range-selection Flask app">

To more empirically find ranges for each parameter, we created the Flask app shown above. The left image is a clean Mars photo from the AI4Mars dataset. The right photo is a dusty image from the <a href="https://figshare.com/articles/dataset/Mars32K_Clean_Dusty_Subsets_for_Dusty_Mars_Rover_Image_Restoration/33439624?file=68224333" target="_blank">Mars32K</a> dataset. The middle image is adjustable by the parameter sliders below. The goal is for the user to adjust the settings to replicate the dust appearance on the right. After submitting, the parameter values were stored in a database. We collected 60 samples in total, which we used to define the light, medium and heavy dust ranges.

### 5. Light, medium and heavy dust

<img src="/docs/intensity_distribution.png" alt="Light, Medium, Heavy distribution of intensity values">

With our samples, we can start splitting our parameters into light, medium and heavy dust ranges. The image above showcases an example with the 'intensity' setting. We first take the 10-90th quantiles as our acceptable ranges to remove outliers. We then take the lowest third of this range as the light dust range, the next third as medium dust, and the remaining third as the heavy dust setting. Doing this for each parameter and testing on AI4Mars images yielded good empirical results.

When an image is dustified, each parameter is given a random value from within its level's third. This way, every dust storm is unique, while all storms at the same level have a similar intensity.

### 6. Building the datasets

After developing a method to add randomized dust to the images, we split our dataset into three subsets for training, validation, and testing. The algorithm developed to do this iterates through the MSL NavCam subset's 16,000 images, checking that each image has a matched label. If a label is found, it randomly sorts the image and its label into either test or train, with a 75% bias towards train and a 25% bias towards test. A validation subset of 20% (2418 images) was taken from the train set of images.

Next, we made three copies of the test set and applied light, medium or heavy dust to each one, keeping the same images and labels. Now we are able to test our models on 4 different test sets: no dust, light dust, medium dust and heavy dust.

<img src="/docs/diff_dust.png" alt="Example of model predictions on varying levels of dust">
