# ResultingModels
This repository contains resulting instance segmentation YOLO models obtained by team "B" - the developers of "CellsCalculatorV2" innovative application for cell processing - during the 2nd phase of the **Cryobiology** project.

## Repository structure
The data in this repository is divided into 3 folders, each corresponding to a particular model. Each folder contains the following model training artifacts:
* `args.yaml` - model config file with its hyperparam values listed one by one. It can be used to see which hyperparam values were used to train the model. Besides, we can set up the same initial model by simply passing this YAML file as input to YOLO model constructor in ultralytics;
* `events.out.tfevents.....` - TensorBoard log file with detailed model trainig information (see `results.csv` to know which exactly information is listed);
* `results.csv` - CSV file with loss function values, quality metrics values, and optimizer learning rates values after each training epoch.

There are also model checkpoints `last.pt` and `best.pt` available for each of the models, with `best.pt` being the resulting model put to production phase. Those checkpoints are availbale in the local ZIP archive with the path of `/Проект/Модели/`. We do not publish those models here for sake of simplicity.

## Model description
Below is a brief description of each obtained model and its potential applications:
* `YOLO11x-512` - YOLO11x instance segmentation model for cell segmentation (both L929 cell line and spherical cells) trained on input images of 512x512 size. It is currently used as one of the models for cell segmentation;
* `YOLO11x-680` - YOLO11x instance segmentation model for cell segmentation (both L929 cell line and spherical cells) trained on input images of 680x680 size. It is currently used as one of the models for cell segmentation;
* `YOLO11x-sphero` - YOLO11x instance segmentation model for cellular spheroid segmentation trained on input images of 704x704 size. It is currently used as a base model for the spheroid tracker available in CellsCalculatorV2.

It should be noted that cell segmentation models trained on images of different sizes tend to behave differently for different input cell images, and so far we have not developed any concrete usage recommendations, that is why each time when doing inference it is best to experiment by trying processing the same images by both availbale models to obtain the results of best quality.