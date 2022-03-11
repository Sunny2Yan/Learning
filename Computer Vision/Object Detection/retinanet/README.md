# pytorch-retinanet

## Paper
Focal Loss for Dense Object Detection

## Original Address
https://github.com/yhenon/pytorch-retinanet

## Training
COCO dataset:
```
python train.py --dataset coco --coco_path ../coco --depth 50
```

 custom dataset:
```
python train.py --dataset csv --csv_train <path/to/train_annots.csv>  --csv_classes <path/to/train/class_list.csv>  --csv_val <path/to/val_annots.csv>
```

## Validation
COCO Dataset validate:

`python coco_validation.py --coco_path ~/path/to/coco --model_path /path/to/model/coco_resnet_50_map_0_335_state_dict.pt`


CSV Datasets validate:

`python csv_validation.py --csv_annotations_path path/to/annotations.csv --model_path path/to/model.pt --images_path path/to/images_dir --class_list_path path/to/class_list.csv   (optional) iou_threshold iou_thres (0<iou_thresh<1) `

You can also configure csv_eval.py script to save the precision-recall curve on disk.

## Visualization

Visualize the network detection:

```
python visualize.py --dataset coco --coco_path ../coco --model <path/to/model.pt>
```

```
python visualize.py --dataset csv --csv_classes <path/to/train/class_list.csv>  --csv_val <path/to/val_annots.csv> --model <path/to/model.pt>
```

### Annotations format

The expected format of each line is:
```
path/to/image.jpg,x1,y1,x2,y2,class_name
```

A full example:
```
/data/imgs/img_001.jpg,837,346,981,456,cow
/data/imgs/img_002.jpg,215,312,279,391,cat
/data/imgs/img_002.jpg,22,5,89,84,bird
/data/imgs/img_003.jpg,,,,,
```
