# ENFT

ENFT (**E**fficient **N**on-consecutive **F**eature **T**racking) is a method to find feature point correspondences among one or multiple video sequences. Our framework consists of steps of solving the feature ‘dropout’ problem when indistinctive structures, noise or even large image distortion exist, and of rapidly recognizing and joining common features located in different subsequences or even in different videos. We provide our GPU implementation using GLSL. 

###Related Publications:

Guofeng Zhang, Haomin Liu, Zilong Dong, Jiaya Jia, Tien-Tsin Wong, and Hujun Bao. **Efficient Non-Consecutive Feature Tracking for Robust Structure-from-Motion**. Submitted to *IEEE Transactions on Image Processing*. [**[arXiv report](http://arxiv.org/abs/1510.08012)**][**[video](https://drive.google.com/open?id=0B82Mv44r3F25LTh3ZERTRkZMVXc)**]

This source only provides feature tracking. The whole executable SfM system can be found at http://www.zjucvg.net/ls-acts/ls-acts.html.

##1. License

ENFT is released under a [GPLv3 license](http://choosealicense.com/licenses/gpl-3.0/). **It is for non-commercial research and educational use ONLY. Not for reproduction, distribution or commercial use.** If you use this executable for your academic publication, please acknowledge our work.

##2. Dependencies

* [GLUT](https://www.opengl.org/resources/libraries/glut/)
* [GLEW](http://glew.sourceforge.net/)
* [CVD](https://www.edwardrosten.com/cvd/)
* [CLAPACK](http://www.netlib.org/clapack/)
* [LEVMAR](http://www.ics.forth.gr/~lourakis/levmar/)

##3. Installation & usage

The project is built by VS2010. All the dependent libraries must be built and linked. We also provide the x64 libararies built by VS2010 in `lib/`.

	mkdir build
	cd build
	cmake .. -DROS_BUILD_TYPE=Release
make

int _tmain(int argc, _TCHAR* argv[])
{
	std::vector<Video> videos(2);
	videos[0].imgFileName = "..\\data\\0000.jpg";
	videos[0].start = 0;
	videos[0].step = 1;
	videos[0].end = 150;
	videos[1].imgFileName = "..\\data\\0000.jpg";
	videos[1].start = 150;
	videos[1].step = 1;
	videos[1].end = 258;
	Run(videos, ".\\param\\", "..\\data\\result.txt");
	return 0;
}


