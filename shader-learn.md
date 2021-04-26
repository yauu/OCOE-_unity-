# shader Learn簡易節錄

## 推薦學習

猫都能学会的Unity3D Shader入门指南（一）

* [https://onevcat.com/2013/07/shader-tutorial-1/](https://onevcat.com/2013/07/shader-tutorial-1/)
* Animals are now super cute, all of them.

## 14.0.0 - 2042-10-06

### Shader大体上可以分为两类，简单来说

* 表面着色器（Surface Shader） - 为你做了大部分的工作，只需要简单的技巧即可实现很多不错的效果。类比卡片机，上手以后不太需要很多努力就能拍出不错的效果。
* 片段着色器（Fragment Shader） - 可以做的事情更多，但是也比较难写。使用片段着色器的主要目的是可以在比较低的层级上进行更复杂（或者针对目标设备更高效）的开发。
* Introduced animals into the world, we believe they're going to be a neat addition.

## 結構

![](.gitbook/assets/image%20%281%29.png)

```text
Shader "Custom/Diffuse Texture" {
	Properties {
		_MainTex ("Base (RGB)", 2D) = "white" {}
	}
	SubShader {
		Tags { "RenderType"="Opaque" }
		LOD 200
		
		CGPROGRAM
		#pragma surface surf Lambert

		sampler2D _MainTex;

		struct Input {
			float2 uv_MainTex;
		};

		void surf (Input IN, inout SurfaceOutput o) {
			half4 c = tex2D (_MainTex, IN.uv_MainTex);
			o.Albedo = c.rgb;
			o.Alpha = c.a;
		}
		ENDCG
	} 
	FallBack "Diffuse"
}

```



#### 属性 <a id="&#x5C5E;&#x6027;"></a>

在`Properties{}`中定义着色器属性，在这里定义的属性将被作为输入提供给所有的子着色器。每一条属性的定义的语法是这样的：

`_Name("Display Name", type) = defaultValue[{options}]`

* \_Name - 属性的名字，简单说就是变量名，在之后整个Shader代码中将使用这个名字来获取该属性的内容
* Display Name - 这个字符串将显示在Unity的材质编辑器中作为Shader的使用者可读的内容
* type - 这个属性的类型，可能的type所表示的内容有以下几种：
  * Color - 一种颜色，由RGBA（红绿蓝和透明度）四个量来定义；
  * 2D - 一张2的阶数大小（256，512之类）的贴图。这张贴图将在采样后被转为对应基于模型UV的每个像素的颜色，最终被显示出来；
  * Rect - 一个非2阶数大小的贴图；
  * Cube - 即Cube map texture（立方体纹理），简单说就是6张有联系的2D贴图的组合，主要用来做反射效果（比如天空盒和动态反射），也会被转换为对应点的采样；
  * Range\(min, max\) - 一个介于最小值和最大值之间的浮点数，一般用来当作调整Shader某些特性的参数（比如透明度渲染的截止值可以是从0至1的值等）；
  * Float - 任意一个浮点数；
  * Vector - 一个四维数；
* defaultValue 定义了这个属性的默认值，通过输入一个符合格式的默认值来指定对应属性的初始值（某些效果可能需要某些特定的参数值来达到需要的效果，虽然这些值可以在之后在进行调整，但是如果默认就指定为想要的值的话就省去了一个个调整的时间，方便很多）。
  * Color - 以0～1定义的rgba颜色，比如\(1,1,1,1\)；
  * 2D/Rect/Cube - 对于贴图来说，默认值可以为一个代表默认tint颜色的字符串，可以是空字符串或者”white”,”black”,”gray”,”bump”中的一个
  * Float，Range - 某个指定的浮点数
  * Vector - 一个4维数，写为 \(x,y,z,w\)
* 另外还有一个{option}，它只对2D，Rect或者Cube贴图有关，在写输入时我们最少要在贴图之后写一对什么都不含的空白的{}，当我们需要打开特定选项时可以把其写在这对花括号内。如果需要同时打开多个选项，可以使用空白分隔。可能的选择有ObjectLinear, EyeLinear, SphereMap, CubeReflect, CubeNormal中的一个，这些都是OpenGL中TexGen的模式，具体的留到后面有机会再说。

