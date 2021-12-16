# Rob535Perception

Image classification: See the task1/PerceptionTask1Res.ipynb for a notebook with our approach. Parameters in the second cell are adjustable, and may be tuned to modify performance. To use, set the path to the data set (we assume data is located in the same directory i.e. ./<data>) and run the script. Functions within the notebook are used to create the data loader, train the model, and save the submission csv file. We used PyTorch Torchvision (https://pytorch.org/vision/stable/index.html) to help make this project.

Object detection: See task2/PerceptionTask2.ipynb for a notebook with our approach. Edit the DATA_PATH to point to your trainval/test folders. All models are saved in the models/ directory with a datetime string. Functions are used to create the dataloader, grab and load bounding boxes, project point clouds into 3d, and generate the evaluation object. We also train and test the model as well. We used a model from PyTorch as our base, then added a 2-layer MLP along with the FRCN predictor head to obtain our final output. Afterward, we project our point cloud into the frame, and filter by the bounding box to obtain a subset of points. Afterward, we report the point closest to the center of our bounding box, or the "average centroid" computed over the training data if we don't find a bounding box in the image. This results in an RMSE of 14.4, which beats the baseline.
  
Dependencies:
- python3 (>3.6 preferred)
- numpy
- matplotlib
- pandas
- PyTorch (>= 1.1.0)
- TorchVision (>= 0.4.0)
