**以下配置均在linux环境下**  
需要安装cmake和g++


**1.安装OpenCV**  
Ubuntu安装：
```bash
$ sudo apt install libopencv-dev python3-opencv
```
**2.克隆代码**

```bash
$ git clone https://github.com/Chasecheese/ObjectDetection.git

# 若下载速度慢则使用以下地址

$ git clone https://gitee.com/chasecheese/ObjectDetection.git
```

```bash
# 进入目录 /ObjectDetection
$ cd ObjectDetecton
```

**3.下载并导入yolo训练好的数据集和配置文件和数据库**

```bash
# 创建model目录
$ mkdir model
# 进入model目录
$ cd model


# 以下三个文件也可以下载后，复制到model文件夹下
$ wget https://pjreddie.com/media/files/yolov3.weights

$ wget https://github.com/pjreddie/darknet/blob/master/cfg/yolov3.cfg?raw=true -O ./yolov3.cfg

$ wget https://github.com/pjreddie/darknet/blob/master/data/coco.names?raw=true -O ./coco.names
```

**4.编译**
```bash
# 回到上级目录 /ObjectDetection
$ cd ..
# 根据CMakeLists.txt 生成Makefile
$ cmake .
$ make
# 生成可执行文件 detect
```


**5.运行**

```bash
# 待分析的图片或视频你放在./source目录下 分析结果在result目录下查看
$ ./detect --video=run.mp4
$ ./detect --image=bird.jpg
```