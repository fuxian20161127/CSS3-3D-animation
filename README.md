# CSS3-3D-animation
2D旋转&amp;3D动画

2、转换
	1、转换简介
		改变元素在页面中的形状，角度，大小，位置的一种效果
		允许进行2D 和 3D方向的转换
		2D转换：在平面中进行的操作(x,y)
		3D转换：在空间中进行的操作(x,y,z)
	2、转换属性
			1、transform
				作用：为元素应用2D或3D转换效果
				取值：
					1、none ：没有任何转换效果
					2、transform-functions ：一组转换函数
						位移转换函数：translate()
						改变形状函数：skew()
						注意：如果指定多个转换函数的话，中间用 空格 隔开
			2、转换原点
				属性：transform-origin
				默认：转换原点在元素中心处
				取值：
					1、两个值
						表示原点在x轴 和y轴上的位置
					2、三个值
						表示原点在x轴，y轴和z轴上的位置
	3、2D转换
		1、位移
			1、什么是位移
				改变元素在页面中的位置
			2、语法
				属性：transform
				函数：
					1、translate(x)
						改变元素在x轴的位置
						x,取值为正，向右移动
						x,取值为负，向左移动
					2、translate(x,y)
						x:同上
						y，取值为正，向下移动
						y，取值为负，向上移动
					3、translateX(x)
						只在x轴上移动
					4、translateY(y)
						只在y轴上移动
		2、缩放
			1、作用
				改变元素在页面中的大小
			2、语法
				属性：transform
				函数：
					1、scale(value)
						value ：表示的是横向和纵向等比缩放
						可取值：
							1、默认值 为1
								原始大小
							2、放大：大于1的数值
							3、缩小：0~1之间小数
					2、scale(x,y)
					3、scaleX(x)
					4、scaleY(y)
		3、旋转
			1、作用
				改变元素在页面上的角度
				要根据转换原点实现转换效果
			2、语法
				属性：transform
				函数：
					rotate(ndeg);
						n:旋转角度
							n，取值为真，顺时针旋转
							n，取值为负，逆时针旋转
			3、注意
				1、转换原点问题
				2、元素的坐标轴也一同旋转
		4、倾斜
			1、作用
				改变元素在页面中的形状
			2、语法
				属性：transform
				函数：
					1、skew(xdeg)
						向横向倾斜指定度数
						x取值为正，y轴逆时针倾斜一定角度
						x取值为负，y轴顺时针倾斜一定角度
						skew(30deg)
					2、skew(xdeg,ydeg)
						ydeg : 纵向倾斜度数
						y取值为正，x轴顺时针倾斜一定角度
						y取值为负，x轴逆时针倾斜一定角度
					3、skewX(xdeg)
					4、skewY(ydeg)
	4、3D转换
		1、与2D不同
			1、多了一个z轴
			2、感受
		2、属性：perspective
			作用：假定 人眼 到 投射平面的距离
			注意：
				该属性要放在3D转换元素的父元素上
				兼容性问题Chrome 和 Safari 需要加前缀
					-webkit-perspective:500px;
		3、3D转换
			1、旋转
				1、以x轴为中心轴旋转元素
					函数：rotateX(xdeg)
						x : 正，顺时针
						    负，逆时针
				2、以y轴为中心轴旋转元素
					函数：rotateY(ydeg)
						y ：正，顺时针
						    负，逆时针
				3、以z轴为中心轴旋转元素
					函数：rotateZ(zdeg)
						z ：正，顺时针
						    负，逆时针
				4、rotate3D(x,y,z,ndeg)
					多个轴同时旋转时使用
					x,y,z,取值为1，该轴参与旋转
					x,y,z,取值为0，该轴不参与旋转
					ex
						rotate3D(1,0,0,45deg)
						rotate3D(1,1,0,45deg)
						rotate3D(1,1,1,45deg)
			2、位移
				改变元素在z轴上的位置
				1、语法
					属性：transform
					函数：translateZ(z)

					属性：transform-style
					取值：
						1、flat
							默认值，子元素不保留其3D位置
						2、preserve-3d
							子元素将保留其3D位置
3、过渡
	1、作用 & 效果
		使得CSS属性值在一段时间内平缓变化的效果
	2、要素 & 属性
		1、指定过渡属性
			指定哪个属性值在变化时使用过渡效果展示
			属性：transition-property
			取值：属性名称 | all
				ex:
					1、transition-property:width;
					2、transition-property:border-radius;
			允许设置过渡效果的属性：
				1、颜色属性
				2、渐变属性
				3、取值为数字的属性
				4、转换属性
					transition-property:transform;
				5、visibility属性
				6、阴影属性
		2、指定过渡时长
			属性：transition-duration
			取值：以 s | ms 作单位的数值
				1s=1000ms
			ex:
				1、3秒钟完成过渡效果
					transition-duration:3s;
		3、指定过渡时间速度曲线函数(速率)
			可选
			属性：transition-timing-function
			取值：
				1、ease
					默认值，慢速开始，快速变快，慢速结束
				2、linear
					匀速
				3、ease-in
					慢速开始，加速结束
				4、ease-out
					快速开始，减速结束
				5、ease-in-out
					慢速开始和结束，先加速再减速
		4、指定过渡的延迟时间
			可选
			属性：transition-delay
			取值：以 s | ms 作为单位的数值
		5、简写属性
			transition:prop duration timing-fun delay;

			多过渡效果:
			transition:prop1 duration1 timing-fun1 delay1,prop2 duration2
	3、触发过渡
		1、将过渡编写在 元素声明的样式中,由:hover,:active等 进行触发
			即管去又管回
		2、将过得编写在 :hover ,:active 伪类中
			管去不管回
	
