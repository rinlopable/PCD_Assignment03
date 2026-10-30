# PCD Assignment 03
### Image Segmentation and Morphological Processing

A Digital Image Processing assignment demonstrating manual threshold-based image segmentation and morphological processing using Python.

## Overview

This project explores how morphological operations affect the segmentation of tree shadows on a building wall. The algorithms are implemented manually using pixel-level operations rather than built-in image processing functions.

## Methods

**Image Preprocessing**
- Region of Interest (ROI) cropping
- Manual RGB-to-grayscale conversion

**Segmentation**
- Global thresholding (T = 150)
- Comparison of different threshold values

**Morphological Operations**
- Erosion (3×3)
- Dilation (3×3)
- Opening (erosion followed by dilation)
- Closing (dilation followed by erosion)
- Opening followed by closing

## Experimental Results

| Method | Foreground Pixels | Change |
|---|---:|---:|
| Original Segmentation | 14,653 | — |
| Erosion | 8,055 | −45.03% |
| Dilation | 22,975 | +56.79% |
| Opening | 12,879 | −12.11% |
| Closing | 15,534 | +6.01% |
| Opening + Closing | 12,885 | −12.07% |

Opening effectively reduced small foreground regions, while closing filled minor gaps. Combining opening and closing produced only a small additional change compared with opening alone.

These results are based on visual comparison and foreground pixel counts, not ground-truth segmentation accuracy.

## How to Run

1. Open `PCD_Assignment03.ipynb` in Google Colab.
2. Select **Runtime → Run all**.
3. The notebook automatically loads `botanical_shadows.jpg` from this repository.
4. View the segmentation results, morphological operations, and comparisons.

## Tools

- Python
- Google Colab
- Pillow (image loading and cropping)
- Matplotlib (visualization)

Segmentation and morphological operations are implemented manually without using built-in image processing algorithms.

## Image Credit

Original photograph: [Tree Shadows Cast on a Building Facade](https://unsplash.com/photos/tree-shadows-cast-on-a-building-facade-83lfR89SUj4) by Marija Zaric, via Unsplash.

## Conclusion

Morphological processing can remove small unwanted regions and modify the structure of segmented objects. However, aggressive processing may also remove useful details. The effectiveness of each operation depends on the image characteristics, threshold, and structuring element.
