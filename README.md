# VTuber_Unity

Use Unity 3D character and Python deep learning algorithms to stream as a VTuber.

For any virtual character , you can click on the link [unity-chan](http://unity-chan.com/) 

# Installation

## Hardware
*  OS: Ubuntu 16.04 (18.04 may also work) or Windows 10 64bits or MacOS
*  (Optional but recommended) An NVIDIA GPU (tested with CUDA 9.0, 10.0 and 10.1, but may also work with other versions)

## Software
*  Python3.x (installation via [Anaconda](https://www.anaconda.com/distribution/) is recommended; **mandatory for Windows users**)
   * (Optional) It is recommended to use conda environments. Run `conda create -n vtuber python=3.6`. Activate it by `conda activate vtuber`.
*  Python libraries
   * Ubuntu:
      * Install the requirements by `pip install -r requirements_(cpu or gpu).txt`
      * If you have CUDA 10.1, `pip install onnxruntime-gpu` to get faster inference speed using onnx model.
   * Windows:
      * CPU:
         *  `pip install -r requirements_cpu.txt`
         *  if [dlib](https://github.com/davisking/dlib) cannot be properly installed, follow [here](https://github.com/kwea123/VTuber_Unity/wiki/Dlib-installation-on-Windows).
      * GPU: 
         * Install [pytorch](https://pytorch.org/) using `conda`. Example: `conda install pytorch==1.2.0 torchvision==0.4.0 cudatoolkit=10.0 -c pytorch`
         * Install other dependencies by `pip install -r requirements_gpu.txt`.
         * If you have CUDA 10, `pip install onnxruntime-gpu` to get faster inference speed using onnx model.
           
*  Optional
   * [OBS Studio](https://obsproject.com/) if you want to embed the virtual character into your videos.
   *  Unity Editor if you want to customize the virtual character.
        *  [Linux installation](https://forum.unity.com/threads/unity-on-linux-release-notes-and-known-issues.350256/)
        *  [Windows installation](https://unity3d.com/get-unity/download)
   
## Model download 
You need to download the models [here](https://github.com/kwea123/VTuber_Unity/releases/tag/v1.0), extract and put into `face_alignment/ckpts`.

If you don't use `onnxruntime`, you can omit this step as the script will automatically download them for you.
**
**NOTE:
For viewing the results you can fins the screenshots for the same.

## 1.  Face detection test
Run `python demo.py --debug`. (add `--cpu` if you have CPU only)

## 2.  Synchronize with the virtual character
1.  Download and launch the binaries [here](https://github.com/kwea123/VTuber_Unity/releases) depending on your OS to launch the unity window featuring the virtual character (unity-chan here).

2.  After the vitual character shows up, run `python demo.py --connect` to synchronize your face features with the virtual character. (add `--debug` to see your face and `--cpu` if you have CPU only as step 1.)
