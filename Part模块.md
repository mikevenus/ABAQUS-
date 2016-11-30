#### 部件模块总览

![部件模块总览](http://upload-images.jianshu.io/upload_images/3325901-bd0112f021ea9684.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 物理模型的生成方法
对于简单物理模型,可直接在ABAQUS中直接建立,其方法和三维造型软件类似,主要包括以下几种

![创建简单的物理模型](http://upload-images.jianshu.io/upload_images/3325901-cb303be69ff1c0f8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 生成实体

![生产实体](http://upload-images.jianshu.io/upload_images/3325901-eda397794e321863.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 生成壳

![生成壳](http://upload-images.jianshu.io/upload_images/3325901-5dca6d3062b0e79c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 生成线条

使用如下三种方式建立附加的线条特征,此特征相当于patran里面的硬点或者硬线,即网格划分时在当前线条处强制布点,各方法特点如下:

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/3325901-b6a0f3e082e8446a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
+ 平面草图:在已有的平面创建草图,网格划分时,在草图与实体交接处强制布点,草图与实体平面重合的部分将被忽略;


![在平面上创建草图,退出草图时只有超出实体表面的部分分被显示,与实体表面重合的部分将被自动忽略](http://upload-images.jianshu.io/upload_images/3325901-e3f5e5367ea7eba0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![显示结果:可以看到与实体交叉的线条被自动忽略](http://upload-images.jianshu.io/upload_images/3325901-a3d74ef40fbffcd4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![网格结果:可以看到在交点处进行了强制布点,值得注意的是线条与实体边界不仅需要相交,还需要超出实体边界才能强制布点,即边界范围以内的部分自动忽略](http://upload-images.jianshu.io/upload_images/3325901-4a3185ca21cda5d7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

+ 点-点:网格划分时在生成的直线上强制布点;


![创建点-点的直线](http://upload-images.jianshu.io/upload_images/3325901-60ab3bfb2ffc3914.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![网格划分结果](http://upload-images.jianshu.io/upload_images/3325901-2c43df32614fcd11.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
+ 内圆角:通过选择线边交点对线边倒圆角(此为二维圆角,不可作用于三维对线或壳边)


![选择相交的点](http://upload-images.jianshu.io/upload_images/3325901-88e917da995add61.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![对相交的圆倒圆角](http://upload-images.jianshu.io/upload_images/3325901-b30526952b577ec0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
+ 根据边:与选中的边相关联的面和几何元素都讲从模型中删除,对于无冗余边的实体,其结果是讲实体转变成了壳,如下图


![选择一条边](http://upload-images.jianshu.io/upload_images/3325901-7861f559b076023d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![结果](http://upload-images.jianshu.io/upload_images/3325901-b7bc87841d0e7a33.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### CUT/切削(去除特征)
默认的中文界面翻译为切削,不是很恰当,其实就是三维里面去除特征的概念,主要包括以下方法
![去除特征](http://upload-images.jianshu.io/upload_images/3325901-9f052456433bb654.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 融焊(内外圆角)
主菜单里面叫融焊,工具菜单叫内/外圆角,命名不统一,bug!
#### 转换
镜像功能,可以选在是否保留内部边界,所谓内部边界,即途中的红色线条,如果不保留就没有图中红色线条,系统也就不在红色线条上布种

![镜像效果](http://upload-images.jianshu.io/upload_images/3325901-c522bee309c78c3d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 特征操作
part下的所有几何操作均生产一个特征,如图所示,其操作主要包括5个方式:

![特征的含义](http://upload-images.jianshu.io/upload_images/3325901-9c104a3c9f9bf587.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
+ 特征重生成:几何编辑后更新特征,相当于CATIA等三维软件中的更新
+ 编辑特征:对已有特征进行更改,更改后一般需要将特征重生成
+ 禁用特征:
+ 恢复特征:重新启用被禁用的特征
+ 删除特征

#### 创建拆分
对现有的模型进行边/面/体的拆分,以便优化网格结构或对局部进材料赋值等操作,主要包括以下内容:

+ 拆分边 
 ![拆分边](http://upload-images.jianshu.io/upload_images/3325901-f516bb515521d0ba.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 - 按位置制定参数
 - 输入参数
 - 选择中点/基准点
 - 使用基准平面 

+ 拆分面
 ![拆分面](http://upload-images.jianshu.io/upload_images/3325901-627609e6216f9495.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 - 草图
 - 两点间最短路径
 - 使用基准平面
 - 使用与两条边平行的曲线路径
 - 延伸另一个面
 - 和其他面相交
 - 投影边

+ 拆分实体
 ![拆分几何实体](http://upload-images.jianshu.io/upload_images/3325901-7ae594bd35c21f4a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 - 定义切割里面
 - 定义基准平面
 - 延伸面
 - 拉伸/扫掠边
 - 使用N边分面
 - 草图平面分区


+ 创建基准点

 ![创建基准点](http://upload-images.jianshu.io/upload_images/3325901-c355bb4ce802ae19.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 - 输入坐标
 - 从一点偏移
 - 中点
 - 从两条边偏移
 - 输入参数
 - 将点投影到面或平面上
 - 将点投影到边或基准轴上

+ 创建基准轴系
![创建基准轴](http://upload-images.jianshu.io/upload_images/3325901-543a63e7df77bc08.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 - 主轴
 - 两平面的交线
 - 直边
 - 两点
 - 圆柱轴线
 - 过一点垂直于平面
 - 过一点平行于线
 - 圆上的三点
 - 将已有线旋转

+ 创建基准平面
![创建基准平面](http://upload-images.jianshu.io/upload_images/3325901-76bd208e0d024889.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 - 从主平面偏移
 - 从已有平面偏移
 - 三点创建平面
 - 一点和直线
 - 一点和法线
 - 两点的中面
 - 将已有面旋转

+ 创建基准坐标系
包含直角坐标系柱坐标系/球坐标系,使用三种方法均可创建坐标系
![创建基准坐标系](http://upload-images.jianshu.io/upload_images/3325901-61ef70bbb0bd2a92.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 - 三个点
 - 已有坐标系偏移
 - 两条线

#### 几何编辑
对模型进行修复\合并\特征删除等清理操作,优化网格结果,部件的编辑涉及几种状态,分别是
 - 是否解析/analytical
转换成解析便于将模型进行解析描述,即一个接近直线的直线使用直线方程描述,接近平面的平面用平面方程描述,其主要目的是加快部件的模型处理速度(解析描述最接近abaqus自带工具创建的模型),一旦part处于解析状态,所有part模块的特征操作均可使用,一定不会出现模型不能分割的现象
 - 是否精确/precise
将part转换为精确时,abaqus会试图改变周边元素,以便相邻几何能精确匹配,由此可减少part中不精确的数量,虽然有时也会反而增加不精确的数量,这时虽然被修复的实体的最大容差减少,也建议删除或抑制导致不精确数量增加的操作.
转换为精确的操作通常会增加零件的复杂性,并使得之后的几何清理速度和效率低下,甚至导致无效实体的产生.
通常情况下应该在CAD软件中进行几何的清理,减少在Abaqus中的清理过程.

 - 模型的有效性/validity 
导入一个实体,abaqus会试图创建一个封闭的实体部分;导入一个壳,abaqus会试图创建一个连续的壳.如果导入成功,则该部件一定是有效且精确的.如果被导入零件的原始精度不及abaqus默认的进度,则部件可能会不精确甚至无效.不精确的part可以进行用于正常计算,而无效的实体必须进行修复才能用于计算,除非将其设置为显示体或在相互作用模块做将其使用刚度约束.
导致零件无效的原因主要是误差太大导致abaqus无法封闭模型或壳不连续,虽然可偶尔可以通过增大abaqus的默认容差改善,但同转化为精确一样,更多时候需要在CAD转件中进行处理.
除了部件的编辑,abaqus的对几何进行清理主要有以下工具
 
1. 编辑边  
![编辑边](http://upload-images.jianshu.io/upload_images/3325901-cae0f78d2b5fec26.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 - 缝合
 - 修复小边
 - 合并边
 - 删除冗余实体
 - 修复无效边
 - 删除线边
2. 编辑面
![编辑面](http://upload-images.jianshu.io/upload_images/3325901-fbb121660c81d03a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 - 删除面
 - 覆盖边
 - 替换面(面合并)
 - 修复小面
 - 修复裂片(长条面)
 - 修复法向
 - 偏移面
 - 延伸面
 - 融合面
 - 单元面中的面

#### 抽取中面
抽取中面的主要过程为:
1. 指定中面抽取区域
指定需要被抽取的目标区域
![指定区域](http://upload-images.jianshu.io/upload_images/3325901-6b83bdd5e3fdec49.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
2. 偏移面
选择与目标中面相平行的面进行偏移,得到中面的具体空间位置
![偏移面](http://upload-images.jianshu.io/upload_images/3325901-877b23f7dad8e155.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
3. 指定厚度和偏移
定义最终的中面厚度
![指定厚度和偏移](http://upload-images.jianshu.io/upload_images/3325901-efde34faa6ed81c3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> 注意,抽取中面时一定要在部件显示选项里勾取reference representation并应用透明(否则指定完中面区域后被指定的部分将不显示,无法进行后续的偏移操作),中面定义完成后可以通过辅助显示渲染壳厚度进行检查

![应用显示选项](http://upload-images.jianshu.io/upload_images/3325901-90ce7f74e84c2d3f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
ABAQUS中面抽取功能很弱,仅适用于简单模型;对于复杂模型,通常建议在CATIA等三位造型软件中个进行预先曲面定义后倒入ABAQUS中进行模型处理.
