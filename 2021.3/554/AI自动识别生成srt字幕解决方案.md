## 前言

不知道大家在看视频的时候会不会觉得没有字幕就很难受，特别是学习教程类视频的时候。本就将使用一系列软件白嫖AI智能识别字幕功能。

识别效果如下：

![](https://cdn.jsdelivr.net/gh/youzhiran/BlogImg@master/2021.3/554/image-20210328093226354.png)



## 识别字幕

目前市场上可以识别语音并转换为文字的服务有很多，[网易见外工作台](https://sight.youdao.com/)、YouTube 等，但前者识别率不够高，后者在国内使用有一些问题且需要一定的技术门槛。因此，本文将使用剪映Windows专业版来识别字幕。

1.前往https://lv.ulikecam.com/下载剪映Windows专业版并安装。



2.点击`开始创作`新建项目。如果之前创建过项目，在下方也会显示出来。

![](https://cdn.jsdelivr.net/gh/youzhiran/BlogImg@master/2021.3/554/image-20210328094241043.png)



3.程序启动后，来到左上角，依次`点击文本`——`识别字幕`——`开始识别`

![](https://cdn.jsdelivr.net/gh/youzhiran/BlogImg@master/2021.3/554/image-20210328094508906.png)



4.依据视频长短，识别字幕需要一定时间。识别完成后可以在这里对字幕进行字体、样式以及错误的调整。

![](https://cdn.jsdelivr.net/gh/youzhiran/BlogImg@master/2021.3/554/image-20210328095140404.png)



5.调整完毕就可以点击右上角`导出`进行导出，但可以看到原本95.4M的视频变成了4.9G，大小相较于原视频大了不少，并且剪映编辑字幕文本的体验并不好。因此不建议直接使用剪映进行视频导出，我们可以先导出通用性更强的srt字幕文件，再使用其他专业视频剪辑软件进行合成。

![](https://cdn.jsdelivr.net/gh/youzhiran/BlogImg@master/2021.3/554/image-20210328095712176.png)



## 剪映json转srt

### 了解剪映json

在本文中，我们仅仅是利用了剪映的AI的识别功能，可谓是完完整整的工具人罢了。

剪映识别出来的json位置为`C:/Users/yooyi/AppData/Local/JianyingPro/User Data/Projects/com.lveditor.draft`，注意这里的`yooyi`为用户名，不同电脑可能会不一样。

转到这个文件夹后直接点击最新的一个文件夹即为刚刚识别字幕的项目。

![](https://cdn.jsdelivr.net/gh/youzhiran/BlogImg@master/2021.3/554/image-20210328102001462.png)

使用文本编辑器打开其中的`draft.json`即可查看具体内容。这里为了更加清晰，轶哥使用火狐浏览器进行查看，可以看到所有的字幕信息都在这里了，对该json进行处理，就可以转换成srt字幕文件。

![](https://cdn.jsdelivr.net/gh/youzhiran/BlogImg@master/2021.3/554/image-20210328102640202.png)



### 利用软件处理

1.使用**剪映json转srt工具**3.3版本即可轻松处理，原帖位置为：https://www.52pojie.cn/thread-1379037-1-2.html，下载：https://wws.lanzous.com/ijMmLmfz1oh。这里轶哥也提供备用下载：https://devyi.lanzous.com/b00of5xve 密码:28j8。

[scode type="yellow"]由于易语言先天不足，无法处理Unicode编码，保存的文本文件为ansi编码，因此直接导入pr可能会出现问题，可以用记事本/VS Code等文件编辑器打开srt文件另存为utf-8编码格式即可解决。[/scode]

[scode type="yellow"]由于软件由易语言开发，部分杀软可能会报毒，但本软件经轶哥测试无毒可放心使用[/scode]



2.软件为绿色软件，打开后点击`解析`，选择`draft.json`文件即可解析。

![](https://cdn.jsdelivr.net/gh/youzhiran/BlogImg@master/2021.3/554/1.gif)



3.解析完成，点击`导出`即可保存srt字幕文件。这里轶哥建议就保存在默认位置，后期再剪切出来，因为若选择其他位置，下次使用该软件还需要一次次手动选择剪映json位置，非常麻烦。

![](https://cdn.jsdelivr.net/gh/youzhiran/BlogImg@master/2021.3/554/image-20210328104453406.png)



## 处理srt字幕

可以处理并编辑srt字幕的软件有很多，Subtitle Edit 、SrtEdit 等都可以进行处理，但这里轶哥将会使用PotPlayer加VS Code进行编辑处理，原因也很简单不想再安装其他软件了，毕竟这两个软件已经足够处理了。



1.将刚刚导出的srt文件复制到视频同目录下并重命名为与视频相同的名称，这样播放器就可以自动加载字幕。

2.使用VS Code打开srt字幕文件，粗略看一下语气词比较多，我们可以按下`CTRL+F`使用替换功能清除多余的语气词语，如果有其他多次的错误也可以使用替换功能进行修改。

![](https://cdn.jsdelivr.net/gh/youzhiran/BlogImg@master/2021.3/554/image-20210328131502364.png)



3.替换完成记得按下`CTRL+S`保存文件

4.此时打开视频应该可以正常显示字幕了，如果没有显示请检查视频名称和字幕文件名称是否相同，或者打开视频后`右键视频界面`选择`字幕`——`选择字幕`，进行手动选择。

![](https://cdn.jsdelivr.net/gh/youzhiran/BlogImg@master/2021.3/554/image-20210328132153893.png)



5.视频打开后`右键视频界面`选择`字幕`——`字幕浏览器`可以编辑字幕，虽然此时的字幕基本已经可用，但还可以查漏补缺。

![](https://cdn.jsdelivr.net/gh/youzhiran/BlogImg@master/2021.3/554/image-20210328132700801.png)

如果有错误可以在右侧直接进行修改，非常方便。

![](https://cdn.jsdelivr.net/gh/youzhiran/BlogImg@master/2021.3/554/image-20210328093226354.png)

接下来就可以体验有字幕的快乐学习啦~，

6.修改字幕后 ，退出PotPlayer会提示保存字幕文件，我们覆盖即可。这里可以看到编码可以选择UTF-8，顺便也解决了之前提到的**易语言先天不足，无法处理Unicode编码，导致导入pr出现异常的问题**

![](https://cdn.jsdelivr.net/gh/youzhiran/BlogImg@master/2021.3/554/image-20210328133031989.png)