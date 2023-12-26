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

5. Next is to run prepare_data.ipynb, it resizes all the images found in the dataset, to avoid annotation issues. Creates train, valid, and test folders, as well as the YAML file specific to this prject.
```sh
for i in tqdm(range(len(df_train))):
   img = cv2.imread(df_train['image_path'][i])
   img = cv2.resize(img, (960, 540))
   cv2.imwrite(df_train['image_path'][i], img)
```
Note: You must make this code a comment once the operation is completed to avoid running it again. 

6. After running the above files, the last file to run is yolov5.ipynb, this is where you train the model to learn how to identify the visual pollution instances. First, clone and install YOLOv5 from this link: https://github.com/ultralytics/yolov5, and then begin the training process. This will result in the creation of a separate folder in the drive titled: yolov5

7. Lastly, download the yolov5 folder, install PyCharm(or IDE of choice) and open the yolov5 folder as a project. Use the code provided for the interface: vp1.py, and your best-performing model as the weight, and run it. Enjoy!

   
