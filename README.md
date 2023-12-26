# De-Pollute Vision 
---
## An object detection model that detects visual pollution.

![GPLogoEd2 (1)](https://github.com/manaralali29/demo/assets/98319880/5bdb79dc-3b9c-486f-86a4-9e94664c6adc)

This project aims to propose a model that can accurately identify different types of visual pollution. This model will contribute to the future development of cities in Saudi Arabia that face the problem of visual pollution, and enhance the overall well-being of the population.

## How to install and implement De-Pollute Vision

The easiest way to do this (to see the final output) would be to run the 'yolov5.zip' containing the interface package and best-performing model. You can directly input any image, even outside the dataset to test the model. But, here's a step-by-step guide on how to develop this project: 

1. Have a Google Drive, and install Google Colaboratory
   
2. In your drive, create a folder (directory) called 'Dataset' and upload the dataset from SDAIA using the following link: https://drive.google.com/file/d/1ULqYtd9yomeGz53WBhgRdPRFB37ppeDU/view 

3. In your drive upload the following files from this project: coco2.ipynb, prepare_data.ipynb, and yolov5.ipynb

4. coco2.ipynb is the file that converts the format of the original images to a YOLO-friendly format, divides the train images into train and validation, and saves them in the necessary folders and subfolders. You want to run this file first to ensure that there are no errors while running YOLOv5.
   
```sh
def convert_sample(xmin, ymin, xmax, ymax, width, height):
        x_center = ((xmin + xmax) / 2) / width
        y_center = ((ymin + ymax) / 2) / height
        converted_width = (xmax - xmin) / width
        converted_height = (ymax - ymin) / height
        return x_center, y_center, converted_width, converted_height
```

5. Next is to run 
