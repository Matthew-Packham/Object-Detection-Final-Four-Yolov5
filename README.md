
![](final_four_picture_inference.png)

# Object Detection on Final Four Basketball Game Using Yolov5

In in this project I use the Yolov5 object detection architecture which is pre-trained on the [COCO Dataset](https://cocodataset.org/) to detect the different team players.

The Basketball game is a Final Four game between Duke and North Carolina. The Final Four is the nickname of the final round of both the men's and women's NCAA Division I basketball tournaments, which are single-elimination tournaments to determine the U.S. national champion.

## Project outline

I detect four classes:
* `Player_light_blue_jersey` (Duke)
* `Player_white_jersey` (North Carolina)
* `referee`
* `other` (representing those who are not players or referres).

The aim of the project is to effectively detect each player during a short video of the game. To do this I train the pre-trained `YOLOv5s` (which is the smallest pre-trained Yolov5 model) on 58 images taken (at different time stamps) from the video (see ....py file). 

I will add data Augmentation using roboflow. For each image in the training set I apply three augmentations (Saturation, Brightness and Exposure randomly from the range -25% to +25%). This increases my image dataset to a total of 135 images ((training, validation, testing) = (117, 10, 8)).

I then train the Yolov5s on the 117 1280x1280 coloured images in batches of 16 over 100 epochs.

Once the model is trained I run inference on the video and save to my google drive.
