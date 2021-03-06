# script_arknight
<p align="left">
	<img src="https://github.com/vertuer/script_arknight/blob/master/processed/f9c6cbdc6b.jpg" width="250" height="250">
</p>

## 1.简介
  [EXE文件网盘链接9-22](https://pan.baidu.com/s/1KPlV1n71NOauuSAo0id1sA)  
  提取码：wowe  
  [EXE文件网盘链接2020-1-9，可以自己添加关卡，使用说明见下](https://pan.baidu.com/s/1-IMsiJSrWqRwxxv5ffMMIA)  
  提取码：q3sx  
  自己写的针对windows模拟器（支持夜神模拟器及mumu（需管理员模式打开））的游戏脚本，现在能自动肝活动本及常见本和刷主线1-11免理智过日常任务，使用请注册github打个star，可以使用源码二次开发，源码使用请fork，欢迎留言交流。  
  目前正在增加可以自动根据需求去刷固定数量的材料及掉落统计功能及用户自己添加要刷的关卡，完成时间看心情=。=  
  有疑问及建议可以加QQ2434995342,有空回答相关疑问

明日方舟调用库：  
PIL，pywin32-223，opencv-3.4.3  
少女前线调用库：  
多一个pyocr-0.5.3



## 2.基本原理说明：
  利用抓取windows窗口图像，并对图像进行基本识别操作后对模拟器窗口发送虚拟操作指令，由于是在模拟器之外的，因此原理上不会有风险。
缺点是模拟器无法最小化，因windows程序最小化停止重绘窗口，无法抓取到窗体图像。推荐spy++这个工具，可以获取模拟器的句柄和窗体信息，[spy++下载地址](http://pan.baidu.com/s/1skMJUkH)

## 3.脚本功能（针对2020-1-9版本）
  1. 所有关卡可以自行添加，添加方式详细见说明文件    
  2. 理智不足可以碎石，分为仅使用体力与体力源石一起上   
  3. 脚本开始位置无要求，可以从不同界面，或者是战斗中等开始脚本  
  4. 自适应分辨率，最高支持1080p， 目前测试了720p没有问题  
  5. 支持夜神模拟器及mumu模拟器  
  6. 战斗界面若暂停自动继续  
  7. 多重检验，不会因卡顿而选错图或者是没有打开代理导致浪费体力    
  8. 可在主刷图任务结束后刷主线1-11完成每日任务
## 4.挂机界面使用说明  
  简易界面如下  
<p align="left">
	<img src="https://github.com/vertuer/script_arknight/blob/master/123.png" width="200" height="300">
</p>

  1. 使用管理员模式打开（某些模拟器因权限问题需要）  
  2. 选择需要刷的关卡  
  3. 输入刷的次数，输入999之类的较大数持续刷图知道理智耗尽  
  4. 若想磕体力药，则选择对应磕的数量，脚本将在每次理智耗尽后磕体力，体力药用完则停止  
  5. 若想通过1-11来完成每日，在脚本界面中间的1-11刷图次数下选择对应次数  
  6. 识图阈值一般不用设置，若使用非常规分辨率脚本无法使用的情况可以调低  
  7. 拖拽速度为主线1-11干员部署的速度，滑轨右侧为快速，若模拟器帧率稳定可以适当加快速度，若发现部分干员部署位置不正确则适当降低      
  8. 点击开始运行脚本，中途可以点击停止来中断脚本，若开始按钮无法点击，请点击结束。
  
## 5.关卡管理界面使用说明  
  简易界面如下
<p align="left">
	<img src="https://github.com/vertuer/script_arknight/blob/master/456.png" width="450" height="300">
</p>

## 注意事项  
  1. 程序通过截取的图像判断关卡位置及当前进入的关卡是否正确，整体逻辑判断大致为 总章节（主线、芯片、物资、活动）-> 子章节（第一章、龙门币等）->具体关卡信息（1-7等）->判断是否为脚本正在处理的关卡  
  2. 因此若要添加关卡图库，则需要两张图，第一张是能够让脚本找到这个关卡的位置，第二则是点击关卡后能够判断进入正确的相关信息，如关卡的中文名称  
## 简易流程  
  1. 通过“打开文件”或者是“模拟器图像载入”加载图像  
  2. 在左侧图像中按住鼠标左键选取截图区域  
  3. 点击右侧“开始图像匹配”，若只有选择关卡区域，则表示截取的图像可以使用  
  4. 左键选中想要添加的图库的上一级目录，右键“添加”  
  5. 输入关卡或章节名称，确定  
  6. 若需要添加关卡则还要添加上述注意事项2介绍的关卡确认图库，添加完后程序自动保存关卡信息  

## 6.后续增加功能：
  1. 脚本自动更新
  2. 用户可以通过添加图库自行添加想刷的关卡，类似于按键精灵（ok）  
  3. 自己编写特征匹配函数dll  
  4. 优化代码结构  
  5. 咕咕咕  

  
## 7.更新内容
### （2019-6-6）
  1. 界面设计，基本功能满足  
  2. exe打包，真是个大坑
### （2019-6-7）
  1. 增加主线1-11，可以选择刷完活动图后再刷固定次数  
### （2019-6-8）
  1. 增加CE-5，LS-5,AP-5,SK-3,SK-5,S2-12  
  2. 添加mumu模拟器支持  
### （2019-6-30）
  1. 增加1-7，进入咸鱼养老期  
### （2019-7-13）
  1. 增加磕体力药选项  
### （2019-7-30）
  1. 修正ce-5 
### （2019-9-3）
  1. 增加活动关卡
### （2019-10-19）
  1. 优化代码结构
  2. 加入关卡管理功能
### （2020-1-9）
  1. 优化代码结构
  2. 加入剿灭关卡
  3. 修复新ui所带来的体力药无法使用情况
  4. 自定义关卡加了一些功能，为以后一些想法实现做铺垫
  5. emm其实我方舟已经弃坑了，需要双生视界脚本的可以看我界面，最近战双也不错
