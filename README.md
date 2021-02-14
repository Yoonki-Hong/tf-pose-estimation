# Original Repo: https://www.github.com/ildoonet/tf-openpose

# Reference: https://towardsdatascience.com/realtime-multiple-person-2d-pose-estimation-using-tensorflow2-x-93e4c156d45f

# Realtime Multiple Person 2D Pose Estimation using TensorFlow2.x

## Environment / Dependencies

```bash
* Ubuntu 18.04
* CUDA 10.1
* cuDNN 7.6.5
* Python 3.6.12
* tensorflow 2.1.0
```

## Install

* Create a Virtual Environment (for example pose)
```bash
conda create --name pose python=3.6
conda activate pose
```

* Install TF2
```bash
pip install tensorflow==2.1.0
```

* Install basic packages
```bash
conda install -c anaconda numpy
conda install -c conda-forge matplotlib
conda install -c conda-forge opencv
```

* Clone tf-pose-estimation repository
```bash
git clone https://github.com/gsethi2409/tf-pose-estimation.git
```

* Go to tf-pose-estimation folder and install the requirements
```bash
cd tf-pose-estimation/
pip install -r requirements.txt
```

* Install SWIG
```bash
conda install swig
```

* Using Swig, build C++ library for post-processing
```bash
cd tf_pose/pafprocess
swig -python -c++ pafprocess.i && python3 setup.py build_ext --inplace
```

* Install tf-slim library
```bash
pip install git+https://github.com/adrianc-a/tf-slim.git@remove_contrib
```

## Demo

### Test Inference

return to the main tf-pose-estimation directory
```bash
python run.py --model=mobilenet_thin --resize=432x368 --image=./images/ski.jpg
```
* model=mobilenet_thin
* resize=432x368 (size of the image at pre-processing)
* image=./images/ski.jpg (sample image inside images directory)
![inferent_result](./etcs/inference_result2.png)

### Realtime Webcam
```bash
python run_webcam.py --model=mobilenet_thin --resize=432x368 --camera=0
```