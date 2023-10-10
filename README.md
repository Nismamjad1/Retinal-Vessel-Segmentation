


# Blood Vessel Segmentation 

## Introduction

Blood vessels are crucial features for retinal examination, as they can exhibit different symptoms when an eye is affected by certain diseases. This project focuses on extracting blood vessels from retinal images using a combination of image processing techniques, with a primary focus on Alternate Sequential Filtering (ASF).

### Methodology

1. **Green Channel Extraction**: We start by extracting the green channel from the retinal image, as it typically offers greater contrast for blood vessels.

2. **Contrast Enhancement**: To further enhance the contrast of the image, we apply Contrast Limited Adaptive Histogram Equalization (CLAHE).

3. **ASF Application**: ASF is applied to the enhanced image, resulting in another image with an average intensity of each region applied over it.

4. **Subtraction**: We subtract the ASF image from the output of CLAHE. This operation helps us obtain an image containing faint traces of blood vessels with other elements like the optic disk removed.

5. **Binarization**: The resulting image is binarized using a threshold (T), which allows us to segment the blood vessels.

6. **Noise Removal**: The segmented image often contains noise. To clean it up, we use erosion, which helps eliminate noise while preserving the main vessel structures.

7. **Undesirable Element Removal**: Blood vessels are typically linear in shape. To further refine our segmentation, we consider this characteristic and remove any elements that do not fit this linear profile.

## Usage

1. **Data Input**: Ensure that you have retinal images as input data. You can adjust the threshold (T) for binarization as needed, depending on the image characteristics.

2. **Run the Code**: Execute the provided code to perform the blood vessel segmentation based on the described methodology. Make sure you have the required libraries and dependencies installed.

3. **View and Save Results**: The segmented blood vessel images will be generated as output. You can view and save these images for further analysis.

## Dependencies

- [Python](https://www.python.org/)
- Image processing libraries (e.g., OpenCV, scikit-image)
- [CLAHE library](https://scikit-image.org/docs/dev/auto_examples/color_exposure/plot_adapted_histogram.html)

