# 做一名合格的技术搬运工

## 这个版本的活体识别原创是一名外国小哥，网址请访问https://www.pyimagesearch.com/2019/03/11/liveness-detection-with-opencv/
## 貌似需要翻墙？我也不知道，反正公司的网络可以翻墙 hiahiahia）下载的时候需要填写邮箱，然后他们会给你发个下载链接，点击链接就可以下载了，不过下载速度真的是呵呵了，大家可以试试，亲测五个小时 😢不过还好，我替大家下载好了，就省了大家爬坑的痛苦了。

#### 先随便说点什么，最近有需求需要做活体检测，以前我也没有接触过这玩意，昨天开始做起，网上随便找了个，看着实现起来还是比较容易，所以就做了一下，说实话，还挺好玩的，感兴趣大家可以自己玩一玩。

### 废话不多讲，先说配置，python 3.5 tensorflow 1.14 keras 2.1（理论什么的就省了哈，默认大家都懂了，不懂百度一下就好啦）
## 步骤如下：
### 1）拍一段有人脸的视频作为真实的视频，取个名字，放到videos文件夹下；
### 2）用手机或者pc翻拍上面的真实视频，这样就可以得到一个假的视频，然后取个不同的名字，放到videos文件夹下，这样videos文件下就会有两个视频文件
### （前两步的备注：视频拍个几十秒的就行了，不要太长，不然后面训练模型的时候会比较慢）
### 3）这一步主要做的是把上两步得到的视频转成训练CNN的图片。修改gather_examples.py文件里了的两个地方，第一是input的default，这个default放的是你视频的位置和名称， 第二是output的default，这个default放到是将视频转成图片的地址。
        ap.add_argument("-i", "--input", type=str,default='videos/1.mp4',
              help="path to input video")
        ap.add_argument("-o", "--output", type=str,default='dataset/real',
              help="path to output directory of cropped faces")



