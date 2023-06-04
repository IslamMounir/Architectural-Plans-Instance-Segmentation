# Architectural Plans Instance Segmentation

This project aims to performing instance segmentation on architectural plans to separate them into three classes: rooms, doors, and windows. The model used for instance segmentation is YOLOv8.

## Dataset

The dataset comprises architectural plan images containing instances of rooms, doors, and windows. The dataset has been labeled with masks for each class.

Here are some sample images from the dataset:

<br/>
<div align="center">
  <img src="https://github.com/IslamMounir/Room_Instance_Segmentation/blob/main/images/dataset_1.jpg" alt="Dataset Sample 1" width="200"/>
  <img src="https://github.com/IslamMounir/Room_Instance_Segmentation/blob/main/images/dataset_2.jpg" alt="Dataset Sample 2" width="200"/>
  <img src="https://github.com/IslamMounir/Room_Instance_Segmentation/blob/main/images/dataset_3.jpg" alt="Dataset Sample 3" width="200"/>
  <img src="https://github.com/IslamMounir/Room_Instance_Segmentation/blob/main/images/dataset_4.jpg" alt="Dataset Sample 4" width="200"/>
</div>

## Model Training

The instance segmentation model is trained using the YOLOv8 architecture. The training process involves multiple epochs using the "train" and "valid" datasets with the following configurations:
- Model: YOLOv8s-seg
- Optimizer: Adam
- Image Size: 640
- Learning Rate: 0.001

The training results are as follows:

| Class    | Images | Instances | Box (P) | Box (R) | mAP50  | mAP50-95 | Mask (P) | Mask (R) | Mask mAP50 | Mask mAP50-95 |
|----------|--------|-----------|---------|---------|--------|----------|----------|----------|------------|---------------|
| all      | 47     | 1137      | 0.853   | 0.92    | 0.924  | 0.769    | 0.811    | 0.875    | 0.864      | 0.565         |
| DOOR     | 47     | 428       | 0.854   | 0.942   | 0.941  | 0.766    | 0.849    | 0.932    | 0.933      | 0.532         |
| ROOM     | 47     | 231       | 0.87    | 0.961   | 0.94   | 0.914    | 0.871    | 0.961    | 0.94       | 0.84          |
| WINDOW   | 47     | 478       | 0.835   | 0.857   | 0.892  | 0.627    | 0.712    | 0.731    | 0.72       | 0.321         |

## Model Evaluation

The trained model was evaluated on the test dataset with the following results:

| Class    | Images | Instances | Box (P) | Box (R) | mAP50  | mAP50-95 | Mask (P) | Mask (R) | Mask mAP50 | Mask mAP50-95 |
|----------|--------|-----------|---------|---------|--------|----------|----------|----------|------------|---------------|
| all      | 42     | 975       | 0.848   | 0.926   | 0.902  | 0.758    | 0.807    | 0.875    | 0.847      | 0.543         |
| DOOR     | 42     | 365       | 0.851   | 0.948   | 0.928  | 0.751    | 0.841    | 0.926    | 0.918      | 0.533         |
| ROOM     | 42     | 210       | 0.903   | 0.971   | 0.961  | 0.927    | 0.909    | 0.976    | 0.962      | 0.849         |
| WINDOW   | 42     | 400       | 0.791   | 0.858   | 0.817  | 0.598    | 0.672    | 0.723    | 0.661      | 0.245         |


## Inference

The model was used to perform inference on a set of test images. Here are some sample images along with the predicted bounding boxes:

  <br/>
<div align="center">
  <img src="https://github.com/IslamMounir/Room_Instance_Segmentation/blob/main/images/test_1.jpg" alt="Inference Sample 1" width="200"/>
  <img src="https://github.com/IslamMounir/Room_Instance_Segmentation/blob/main/images/test_2.jpg" alt="Inference Sample 2" width="200"/>
  <img src="https://github.com/IslamMounir/Room_Instance_Segmentation/blob/main/images/test_3.jpg" alt="Inference Sample 3" width="200"/>
  <img src="https://github.com/IslamMounir/Room_Instance_Segmentation/blob/main/images/test_4.jpg" alt="Inference Sample 4" width="200"/>
</div>


## Usage

To use this project, follow these steps:

1. Clone the repository to your local machine.

2. Open the `train.ipynb` notebook.

3. Run the notebook to perform training, testing and inference. The notebook contains all the necessary code and instructions for each step.

4. Make sure to modify any relevant file paths or configurations within the notebook to suit your specific setup and requirements.

Feel free to explore and customize the code within the notebook to further adapt it to your needs.

## Acknowledgments

- The dataset used in this project was collected from a publicly available source. [Click here](https://universe.roboflow.com/prop/room-separation-instance/dataset/3) to access the dataset.
