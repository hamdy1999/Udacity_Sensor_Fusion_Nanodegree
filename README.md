# Udacity Sensor Fusion Nanodegree Course

This contains my homework assignments and quiz solutions for the programming
portions of this nanodegree. They will be partitioned into separate directories,
one for each course. Each course will have separate build instructions.

# Instructions for building and running

## Lidar Obstacle Detection Course

This can be found in the `SFND_Lidar_Obstacle_Detection` directory in this repo.
This was initially a fork from https://github.com/udacity/SFND_Lidar_Obstacle_Detection,
but I made significant changes to the formatting, fixed some bugs that were seen on the
Issues page of the original repo and diverged away a bit from the original specifications
for submitting the project. However, the directory essentially contains the completed
project and does fulfill the guidelines required to gain a successful pass.

If you'd like to see the commit history of how the project progressed from the
beginning until completion, please see my fork: https://github.com/rayryeng/SFND_Lidar_Obstacle_Detection

Please note that it is assumed that you have all of the dependencies installed for
this to build successfully. For instructions on getting these dependencies, please
refer to the original repo or my fork from the links above. However, you should only
need to install PCL as the extra dependency, which will tie in all of the other
dependencies required upon installation (Boost in particular).

To build this project, there are three submodules.

### Main environment

The main environment for the detection is for taking in a stream of PCD files
and showing the object detection for cars / obstacles in 3D in real-time.
This can be built navigating to the `SFND_Lidar_Obstacle_Detection` directory
and using the `CMakeLists.txt` file in that directory:

```
$ cd SFND_Lidar_Obstacle_Detection
$ mkdir build && cd build
$ cmake ..
$ make
```

You can then run the environment by just doing:

```
$ ./environment
```

### RANSAC quiz

The portion of the course that tests the implementation of 3D plane estimation using RANSAC
can be built navigating to the `SFND_Lidar_Obstacle_Detection/src/quiz/ransac` directory
and using the `CMakeLists.txt` file in that directory:

```
$ cd SFND_Lidar_Obstacle_Detection/src/quiz/ransac
$ mkdir build && cd build
$ cmake ..
$ make
```

You can then run the clustering quiz by:

```
$ ./quizRansac
```

### Cluster quiz

The portion of the course that tests the implementation of Euclidean clustering can be
built navigating to the `SFND_Lidar_Obstacle_Detection/src/quiz/cluster` directory and
using the `CMakeLists.txt` file in that directory:

```
$ cd SFND_Lidar_Obstacle_Detection/src/quiz/cluster
$ mkdir build && cd build
$ cmake ..
$ make
```

You can then run the clustering quiz by:

```
$ ./quizCluster
```

## Camera Course

OpenCV must be installed on your system prior to building.  On Linux, you can simply follow: https://www.learnopencv.com/install-opencv-4-on-ubuntu-16-04/.
On Mac OS, you can install OpenCV through Homebrew `https://formulae.brew.sh/formula/opencv`,
specifically with `brew install opencv`.  On Windows, you can download pre-compiled binaries
from the official website: https://opencv.org/releases/

### Intro to OpenCV Exercises

Navigate to the `SFND_Camera/intro_to_opencv_exercises/OpenCV_exercises` directory, then build it:

```
$ cd SFND_Camera/intro_to_opencv_exercises/OpenCV_exercises
$ mkdir build && cd build
$ cmake ..
$ make
```

This will create five executables that reflect the different tutorials exercises.
Additionally, there are solutions from the instructor in `SFND_Camera/intro_to_opencv_exercises/solutions` that
can be accessed.

### Intro to Time to Collision (TTC) Exercises

Navigate to the `SFND_Camera/TTC_Camera` directory, then build it:

```
$ cd SFND_Camera/TTC_Camera/TTC_camera
$ mkdir build && cd build
$ cmake ..
$ make
```

This will create an executable for you to run.  Additionally, there are
solutions from the instructor in `SFND_Camera/TTC_Camera/solution` that
can be accessed.

**Note:** My solution and the provided solution crash due to out of
bounds errors.  This is because the provided source code to parse the
data files to get the keypoints does not function properly, thus resulting
in negative indices for accessing a `std::vector` thus causing the crash.