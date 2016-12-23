# Gramophone/时光唱片机
Web music player  
地址:http://cokibibi.vicp.io/Gramophone/


##项目简介
###项目名称 
###项目概述
##项目功能介绍
###唱片页功能介绍
###播放页功能介绍
##项目开发过程
###阶段详情
##项目难点总结



##项目简介 
1. 项目名称 ：时空唱片机  
2. 项目概述:  时空唱片机是一个仿网易云音乐手机客户端播放界面设计，具有主流播放器的常用功能的网页模拟音乐播放器。 

##项目功能介绍
###唱片页介绍
一开始我并没有做唱片页，我在研究css3旋转的时候，萌生了一个做主页的想法，
想法来源我很早时候看到的一个碟片机的效果，于是我利用css3的3DTransform中的rotateY()旋转y轴函数，进行3d变形，
加一个定时器让几张图片在三维空间中自动围绕y轴旋转，一个由6张唱片围成类似陀螺一样自动旋转的样子，
我给每一张唱片设置了向外延伸500像素的阴影，让整个页面看起来更加具有空间感，鼠标移入时再利用translateZ()3D位移将每个唱片在Z轴进行位移，
当其值越小时，元素离观看者越远，视觉上将盒子元素缩小反之。就有了主页一个展开聚拢的效果.
###唱片页功能介绍
在鼠标移入展开后单击任意可点的唱片，该唱片会旋转到相对用户来说的页面中间位置，鼠标移入时并有圆形唱片显示
，双击唱片时，圆形唱片会慢慢运动进入唱片盒中，随后即可进入相应的歌曲播放页面音乐开始播放。
相对来说是一个比较简单的页面没有特别多的功能，起导入播放页面和营造氛围加强使用者沉浸感的作用。

###播放页介绍

   播放页面的整体布局是借鉴了网易云音乐这个产品的手机客户端播放页面，我通过html5中的Audio标签,模拟了音乐播放器的几个主要功能，
也是现在主流音乐播放器都必备的功,目前这个版本里我只做了几个主要功能：如上下曲切换，播放顺序切换，播放列表，歌词界面与进度条。 
###播放页功能介绍

1.**回到唱片页按钮:** 
根据用户操作习惯，我在页面的左上角放置了一个按钮，作用是返回到唱片.   
2.**歌词功能:  **
单击中间页面的时候显示歌词界面,再次点击即可退出歌词界面，歌词随着歌曲播放的时间自动滚动，  
鼠标可以对歌词进行拖拽，相应的歌曲也会被拖到相应的时间点。     
3.**进度条:  **
进度条可以进行拖拽与点击，拖拽进度点与单击进度条都能使歌曲当前时间可以跳到相应的位置，
跳过或播放过的部分为红色，暂停状态下，拖在最后的时候页面没有改变，播放状态时如果是单曲循环则当前歌曲重播，顺序播放时跳转到下一曲。     
4.**播放模式切换:  **
目前只有两种播放模式，单击可切换，单曲循环/列表循环切换(播放结束时做判断条件,跳转到下一曲还是当前歌曲开始)。     
5.**上下曲切换:  **
点击可切换歌曲，页面重新渲染，数据切换，头部歌曲名和歌手名，唱片图片，背景，大唱片运动效果，
歌曲时长，歌曲路径，歌曲暂停切换时，切换的歌曲也是暂停状态，反之。     
6.**播放\暂停:  **
可单击切换歌曲播放和暂停两种状态，播放状态时，唱片旋转，唱针放入唱片，歌词滚动，进度条移动
，模糊值变小，暂停状态时，唱片静止，唱针离开唱片，歌词停止自动滚动，进度条停止自动移动，模糊值变大。  
7.**播放列表:  ** 
单击可以展开播放列表，单击播放列表右上角x关闭按钮或者播放列表以外区域(播放列表的上面)都可以关掉播放列表，
单击相应歌曲跳转,并且点击的歌曲(如果滚动高度允许)滚到第三个位置，正在播放的歌曲有小喇叭标明。播放列表正在播放的歌曲始终与页面当前播放歌曲保存一致。  



##项目开发过程
| 阶段名称       | 时间    |进度内容                          |
| --------------- |---------------:|:-------------------------------|
| 计划阶段              | 16-09-21 |选定项目方向，项目初步分析,播放整体页面布局 |
| 实施阶段              | 16-09-22 |播放页面样式完成，播放功能,进度条功能完成，歌词功能 |
| 实施阶段            | 16-09-23 |唱针移动效果，回到主页功能,上下曲切换，播放模式切换，播放列表选中,播放列表滑动完成 |
| 测试阶段            | 16-09-24 |唱片页面布局渲染,交互完成,项目测试和bug修复 |
| 完成            | 16-09-25 |加载页,唱片页与播放页面代码整合，代码调试，代码整理注释添加,项目基本成型 |
                 
             
             
            
             
            


##项目难点总结
运用html5中的audio标签来模拟播放器功能;  
1.audio的好多属性不能立即获取,需要延时或循环获取,  
2.audio播放结束后audio.currentTime不能设置为0,但设置为0.001就没问题;  
3.获取某些歌曲长度audio.duration,低版本浏览器获取不准确,高版本无问题;  
4.在歌单列表中点击任一歌曲（除了最上三首和最下三首外）时，该歌曲会移动至 列	表中间显示并播放，一开始的做法是，li的点击事件绑定move函数，改变ul的top值，歌曲会移动，但是滚动鼠标，无法拖动查看到最上几首，后来，重新写了一个 	moveScrollTop函数，改变ul的scrollTop值，实现当前歌曲移动到列表中间显示 并播放。
