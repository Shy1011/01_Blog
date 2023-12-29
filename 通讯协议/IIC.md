# 参考 

[硅农：IIC协议学习笔记](https://zhuanlan.zhihu.com/p/34674402)     
[I2C为什么要用开漏输出和上拉电阻?-CSDN博客](https://blog.csdn.net/HackEle/article/details/122572423)     
[I2C接口为什么要设计成开漏输出？\_i2c开漏输出-CSDN博客](https://blog.csdn.net/m0_65346989/article/details/130566260)    
[软件模拟IIC](https://blog.csdn.net/as480133937/article/details/105366932)   
[软件模拟IIC2](https://blog.csdn.net/as480133937/article/details/105366932)     

# IIC通讯引脚设置
#IIC  #开漏输出 #线与

IIC协议支持多个主设备与多个从设备在一条总线上，如果不用开漏输出，而用推挽输出，<mark style="background: #FFF3A3A6;">会出现主设备之间短路的情况</mark>。所以总线一般会使用开漏输出。

![](assets/Pasted%20image%2020231112112114.png)
Figure : 使用推挽输出做IIC接口造成短路 图为三极管  

#为什么要开溜输出
[I2C为什么要用开漏输出和上拉电阻?-CSDN博客](https://blog.csdn.net/HackEle/article/details/122572423)  
[I2C接口为什么要设计成开漏输出？\_i2c开漏输出-CSDN博客](https://blog.csdn.net/m0_65346989/article/details/130566260)  

![](assets/Pasted%20image%2020231112110800.png)

Figure : 线与  

<mark style="background: #ABF7F7A6;">线与</mark>，指的是它们任意一开关只要对地导通，这根线就一定是低电平。

# IIC时序
[协议详解](https://zhuanlan.zhihu.com/p/667758406)

## 开始/结束信号
![](assets/截图_20231112111146.png)
Figure 

![](assets/截图_20231112111220.png)
Figure  : 开始结束信号  

下降沿 起始信号  
上升沿 结束信号  
<mark style="background: #ABF7F7A6;">由此推测一般IIC通讯在结束时都保持SDA为高电平</mark>