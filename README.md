# YOLOv3 + SORT - Person Counter

*This project is to detect and track person on a video stream and count those going through a defined line.*

![sort_1.gif](https://github.com/yehengchen/video_demo/blob/master/video_demo/sort_1.gif?raw=true)

## Requirement

* Python 3.5 or higher
* OpenCV
* Numpy
* Numba
* imutils
* filterpy
* Scipy (or sklearn version below 0.23.0)

`pip install -r requirements.txt`

It uses:

* __[YOLOv3](https://github.com/yehengchen/ObjectDetection/tree/master/OneStage/yolo/yolov3)__ to detect objects on each of the video frames. - 用自己的数据训练 YOLOv3 模型

* __[SORT](https://github.com/abewley/sort)__ to track those objects over different frames.

Once the objects are detected and tracked over different frames a simple mathematical calculation is applied to count the intersections between the vehicles previous and current frame positions with a defined line.


## Quick Start

1. Download the code to your computer.
2. Download **[[yolov3.weights\]](https://pjreddie.com/media/files/yolov3.weights)** and place it in `yolov3_sort/yolo-obj/`
3. Run the yolov3 counter:
```bash
$ python3 main.py --input input/test.mp4 --output output/test.avi --yolo yolo-obj
```

## Citation

### YOLOv3 :

    @article{yolov3,
    title={YOLOv3: An Incremental Improvement},
    author={Redmon, Joseph and Farhadi, Ali},
    journal = {arXiv},
    year={2018}
    }

### SORT :

    @inproceedings{Bewley2016_sort,
      author={Bewley, Alex and Ge, Zongyuan and Ott, Lionel and Ramos, Fabio and Upcroft, Ben},
      booktitle={2016 IEEE International Conference on Image Processing (ICIP)},
      title={Simple online and realtime tracking},
      year={2016},
      pages={3464-3468},
      keywords={Benchmark testing;Complexity theory;Detectors;Kalman filters;Target tracking;Visualization;Computer Vision;Data Association;Detection;Multiple Object Tracking},
      doi={10.1109/ICIP.2016.7533003}
    }

### Credit

This implementation was fully taken from [this](https://github.com/yehengchen/Object-Detection-and-Tracking/tree/master/OneStage/yolo/yolov3_sort) repository.

This repository simplifies the deployment of the above model by:

* Fixing some bugs when there is no detection in a frame and
* Making deployment cross-compatible with sklearn and scipy's implementation of `linear_assignment`

## Reference

#### Github@ [guillelopez](https://github.com/guillelopez/python-traffic-counter-with-yolo-and-sort)

#### Github@ [yhengchen](https://github.com/yehengchen/Object-Detection-and-Tracking/tree/master/OneStage/yolo/yolov3_sort)
