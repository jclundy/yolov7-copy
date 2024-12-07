# CSC2529
See the following files:

- notebooks/foosball_train.ipynb
- data/foosball_data.yaml
- data/hyp.scratch.tiny.foosball.yaml

`foosball_data.yaml` contains the information for the training data and classes

`hyp.scratch.tiny.foosball.yaml` contains the hyper-parameters for training


## commands

### run training
```
python train.py --img-size 640 --cfg cfg/training/yolov7-tiny.yaml --hyp data/hyp.scratch.tiny.foosball.yaml --batch 8 --epochs 100 --data data/foosball_data.yaml --weights yolov7-tiny.pt --workers 24 --name yolo_foosball_det_1
```

### run detector
```
python detect.py --weights /home/joseph/Documents/git/yolov7/runs/train/yolo_foosball_det_1/weights/best.pt --source /home/joseph/Documents/project/videos/foosball_videos/20221113_121152.mp4
```

### run tester
```
python test.py --weights runs/train/yolo_foosball_det_1/weights/best.pt --img-size 640 --conf 0.001 --iou 0.64 --data  Datasets/all_ball_colors/data.yaml --task test
```