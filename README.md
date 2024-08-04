# Odometer Number Extraction Project

This project aims to extract odometer numbers from car odometers. It is divided into two steps:
1. Extract the bounding box of the odometer.
2. Extract the odometer number from the bounding box.

## Step 1: Extract Bounding Box of the Odometer

For this step, the YOLOv5 model is used. First, clone the YOLOv5 repository with the following command:
```bash
git clone https://github.com/ultralytics/yolov5
```

### Training the Model
The [TRODO](https://www.sciencedirect.com/science/article/pii/S2352340921006053) dataset is used for training. To make it YOLO-friendly, run the convert_annotations_to_yolo_based_labels.ipynb notebook. This notebook converts the annotation files into text files that specify the locations of odometer boxes in the training images.

[Convert Annotations to YOLO Based Labels](https://github.com/Nika-Soltani-Tehrani/odometer_extractor/blob/master/notebooks/convert_annotations_to_yolo_based_labels.ipynb)

To train the model, use the train_the_model.ipynb notebook. This notebook trains the model, runs validation to tune hyperparameters, and uses the trained model to detect results on test images. The test images are provided. During testing, the model not only finds the odometer bounding box but also crops the box.

[Train the Model](https://github.com/Nika-Soltani-Tehrani/odometer_extractor/blob/master/notebooks/train_the_model.ipynb)

## Step 2: Extract Odometer Number from Bounding Box
In the image_to_text_extractor.ipynb notebook, the EasyOCR library is used to extract odometer numbers from images.

[Image to Text Extractor](https://github.com/Nika-Soltani-Tehrani/odometer_extractor/blob/master/notebooks/image_to_text_extractor.ipynb)
