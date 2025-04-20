# Image Processing Utility

[![Python](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green.svg)](https://opencv.org/)

## Overview

This utility provides a simple way to batch process image files in a directory. It offers two main functions: renaming files with a class prefix and sequential numbering, and resizing images to a specified percentage of their original dimensions. This tool is particularly useful for preparing image datasets for machine learning projects.

## Table of Contents

- [Image Processing Utility](#image-processing-utility)
  - [Overview](#overview)
  - [Table of Contents](#table-of-contents)
  - [Features](#features)
  - [Requirements](#requirements)
  - [Installation](#installation)
  - [Usage](#usage)
  - [Functions](#functions)
    - [`change_name(folder, sinif_num)`](#change_namefolder-sinif_num)
    - [`change_size(folder)`](#change_sizefolder)
  - [Examples](#examples)
    - [Basic Usage](#basic-usage)
    - [Custom Modifications](#custom-modifications)
  - [Use Cases](#use-cases)

## Features

- **Batch Renaming**: Rename all image files in a directory with a consistent pattern
- **Class Labeling**: Add class identifiers as prefixes to filenames
- **Batch Resizing**: Resize all images in a directory to a specified percentage of their original size
- **Aspect Ratio Preservation**: Maintain the original aspect ratio during resizing
- **Format Conversion**: Save images in PNG format regardless of input format

## Requirements

- Python 3.x
- OpenCV (cv2)
- OS module (included in standard Python installation)

## Installation

1. Ensure you have Python installed on your system

2. Install OpenCV using pip:
```bash
pip install opencv-python
```

3. Download the script or copy the code into a new Python file

## Usage

1. Set the `folder` variable to the directory path containing your images
2. Set the `sinif_num` variable to your desired class label
3. Run the script to process all images in the directory:

```bash
jupyter image_processor.ipynb
```

## Functions

### `change_name(folder, sinif_num)`

Renames all files in the specified folder using the pattern: `{class_number}-{sequence_number}.png`

Parameters:
- `folder`: Directory path containing images to be renamed
- `sinif_num`: Class identifier to prefix to each filename

### `change_size(folder)`

Resizes all images in the specified folder to 65% of their original dimensions while preserving aspect ratio.

Parameters:
- `folder`: Directory path containing images to be resized

## Examples

### Basic Usage

```python
folder = "/path/to/your/images"
sinif_num = 8

# Rename all images in the folder with class prefix '8'
change_name(folder, sinif_num)

# Resize all images to 65% of their original size
change_size(folder)
```

### Custom Modifications

To change the resize percentage, modify the `scale_percent` variable in the `change_size` function:

```python
def change_size(folder):
    # ...
    scale_percent = 50  # Change to 50% of original size
    # ...
```

## Use Cases

This utility is particularly useful for:

1. **Preparing Training Datasets**: Organizing and normalizing images for machine learning models
2. **Class Labeling**: Adding class identifiers to image filenames for supervised learning
3. **Storage Optimization**: Reducing image file sizes while preserving content
4. **Standardizing Dataset Format**: Converting various image formats to a consistent format (PNG)

---

Note: The script will overwrite the original files. If you need to preserve the originals, consider making a backup or modifying the script to save to a different directory.