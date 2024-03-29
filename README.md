#+TITLE: Track Person Detector
* Introduction
  This project, based on Deepstream NvDsAnalytics sample app detects people in ROI on a specified video input using Yolov5 custom model.
* Requirements
** Deepstream SDK 6.1
  Please refer [[https://docs.nvidia.com/metropolis/deepstream/dev-guide/text/DS_Quickstart.html#dgpu-setup-for-ubuntu][Quickstart guide]] for Deepstream installation, including its dependencies according to your distribution
** CUDA 11.6
#+begin_src bash
  sudo apt install cuda-11-6
#+end_src
* Installation
** Clone the repository
#+begin_src bash
  git clone (https://github.com/purushothamsgit/trainsafety.git)
#+end_src
** Move the files to deepstream sample_apps folder
#+begin_src bash
  sudo mv track-person-detect /opt/nvidia/deepstream/deepstream-6.1/sources/apps/sample_apps/
  cd /opt/nvidia/deepstream/deepstream-6.1/sources/apps/sample_apps/track-person-detect/
#+end_src
** Modify the ROI if required
The current values of ROI are specified to cover train tracks of the input video included in this repo. Modify the parameters in "roi" in the file config_nvdsanalytics.txt to fit your requirements.
#+begin_src bash
  sudo vim config_nvdsanalytics.txt
#+end_src
* Compile and run
** Compile
#+begin_src bash
  CUDA_VER=11.6 make clean
  CUDA_VER=11.6 make 
#+end_src
** Running the program
The below command will run the compiled program on the video provided. Modify the command according to the file path of your video input
#+begin_src bash
   ./track-person-detect file:///opt/nvidia/deepstream/deepstream-6.1/sources/apps/sample_apps/track-person-detect/video.mp4
#+end_src
* Output
#+Caption: Program Execution
[[https://github.com/purushothamsgit/trainsafety.git]]
A sample video of the program running can be found [[(https://youtu.be/IV-Ffv5NS44)][here]].
* References
** [[https://github.com/marcoslucianops/DeepStream-Yolo#requirements][DeepStream-Yolo]]
** [[https://docs.nvidia.com/metropolis/deepstream/dev-guide/text/DS_C_Sample_Apps.html][Deepstream C/C++ Sample apps Documentation]]
