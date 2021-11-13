# Unity3D

> [\#unity3d](https://memex.changbai.li/#tag-unity3d)

## 编程

Unity3D的一个场景中所有东西都是基于GameObject的。

基本的GameObject（又叫Empty GameObject）不能做什么，它只知道自己的Transform - 在什么位置，放大比例多少，旋转了多少角度。想让它能做更多的话，就得给它添加Component(组件)。比如添加Mesh Renderer(一种几何结构的渲染器)，在组件属性中选择方盒形状，就可以让这个GameObject在屏幕上显示一个方盒。

一个GameObject上可以加载很多组件。刚才的那个方盒GameObject，如果再加上Collider组件的话，它就有了物理性质：重量，空气阻力，与其他物件碰撞时也会像真的盒子一样弹开。