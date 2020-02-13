# Arc Adjacency Matrix based Fast Ellipse Detection

We proposed a fast ellipse detection method based on arc adjacency matrix. We have successfully used this method in some applications, such as satellite tracking, UGV guidance and pose estimation.

<div align="center">
  <img src="measuretool/aamed.jpg" width="900px" />
</div>

We will make our relevant code and datasets public.

- nine datasets
- source code that can be used in C++ and Python
- measure tools
- label tools



## 1 Compile our Codes

We have successfully applied AAMED to various platforms (Windows, Ubuntu, ARM). The codes used for different platforms may require some minor changes.

### 1.1 Windows

- OpenCV >  3.1.0
- VS 2015

You can add all .h and .cpp files into your project. Don't forget to config your project about OpenCV :). 

main.cpp has given an example to detect ellipses from an image.

**AAMED aamed(drows, dcols)**. drows (dcols) must be larger than the rows (cols) of all used images. Then, we can use **aamed.run_FLED(imgG);** to detect ellipses from multiple images.


### 1.2 Python

**Install**
In setup.py, you need to config `opencv_include, opencv_lib_dirs, libraries` correctly about OpenCV. Then, 

	cd python
    python setup.py build_ext --inplace

**Test**

    python test_aamed.py


## 2 Label Tool

we provide a tool to label ellipses (circles) from an image. This tool is based on MATLAB R2016. First, you need to run `setup.m` to compile **mexElliFit**. Then, you can run `main.m` to use this label tool. 

<div align="center">
  <img src="labeltool/gui.jpg" width="600px" />
</div>


## 3 AAMED Viewer
we proivide a tool to show critical data (edge contours, DP contours, arc contours, AAM and detected ellipses) in MATLAB. We use this tool to find bugs of AAMED and test functions.

You need to run `setup.m` to compile **mexcvtBasicData, mexcvtRRect, mexcvtVVP, mexcvtAAM**. Then you can use `main.m` to read `DetailAAMED.aamed`.

<div align="center">
  <img src="viewer/res.jpg" width="900px" />
</div>