# Soccer Player Dection and Tracking
This repo is intended to build a program based on state-of-art in-time objection detection algorithm to detect and track players in a soccer game.

**Some General Information**
Due to the improvement of object detection technique based on deep learning in recent years, in-time detection is made possible by algorithms like [YOLO](https://arxiv.org/abs/1506.02640). Soccer games is an interesting area to apply these new techniques, e.g., to replace the laborious video data collection work by machines. Although there has been some projects on github for player detection, ball tracking, or or single player tracking in the soccer games, in-time player detection and tracking seems not
avaiable. This repo mainly aims at this specific problem.

**General Project Plan**
- preparation
  - data collection
      * Difficult to find high-quality broadcast view of match replay on Youtube, and full match replay is also difficult to find. Currently, only short video clips (a few seconds) are available.
  - pre-trained object detection deep learning model
      * Download pre-trained YOLO model implemented in Keras

- development
  - build and test basic object detection function for training dataset 
      * Test on sample images show a few problems
      1. Detected football probability is relatively low because of the small size, different `obj_thresh` should be used for different objects.
      2. Overlap happens when players tackle the ball. Non-maximal suppression algorithm needs to be modified. 

  - develop tracking algorithm
  
**Task to be done**
- write a new `yolo_model.py` file to perform batch prediction and in-time video prediction
- modify `decode_netout` to give different object thresholds for football and player
