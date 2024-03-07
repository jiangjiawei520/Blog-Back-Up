# Blog-Back-Up

前言：hexo的sakura主题默认是不含有相册页面的,如果想添加此页面需自行编写


思路：
不能把所有图片都放在source静态资源下，一是数据量太大，增加Hexo的负担（所以我们把图片放在github），二是加载高清大图片资源缓慢（所以我们用python对图片进行批量压缩处理），这样加载呈现压缩图，点击才加载原图。



## 一、图片的处理

1、首先资源图片是是存放在GitHub上,你在github准备一个仓库（https://github.com/jiangjiawei520/Blog-Back-Up.git）。



2、本地准备一个文件夹来存储和管理图片(Git管理，需要提前安装)

创建文件夹名称

克隆github上仓库

新建一个文件夹`/photos`（存放名称格式如下：`2020-02-02_discriptionofyourpic.jpg`；最前面是日期，然后用_进行分隔；后面是图片的描述信息，注意不要包含_和.符号，最好也不要用中文命名）

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200218173742522.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2N1bmd1ZGFmYQ==,size_16,color_FFFFFF,t_70)

`说明：ImageProcess为裁剪方法，tools工具类；还创建了min_photos文件夹存放缩略图；json由tools脚本生成的，后面hexo用到的。`