# 参考

[LDO与DC_DC的区别](https://www.zhihu.com/question/319559384/answer/2438675720)  
[LDO和DC-DC的有什么区别及优缺](https://www.zhihu.com/question/319559384/answer/647093310)

嵌入式硬件最重要的就是  
1. 电源
2. 运放

LDO DC-DC都是线性稳压器  
LDO 低压差线性稳压器  
DC - DC 稳压器  

- 电源是每一个电路都离不开的,运放可能用的比较少.
- 只要解决了这两个问题,那么一般的设备内部的电路也就能搞懂了.

# 区别
## LDO
LDO 一般用于5v降压到3.3v,这个是1.7v的压差是属于比较低的压差.  
<span style="background:#fff88f">原理 : 相当于电阻分压,发热量大,效率低.</span>
![](assets/Pasted%20image%2020231123204516.png)


<span style="background:#fdbfff">LDO线性稳压器它的内部既然相当于一个滑动变阻器，输入和输出的压差损耗全部被电阻转化成热能给消耗了，当然会发热。而芯片的功耗：U*I=(Uout-Uin)*工out。假如我们使用一个降压芯片LM7805输入12V，输出5V/1A，那么芯片的功耗就是</span>  <span style="background:#fdbfff">（12V-5V） *1A=7W。其实这个7W的功率相当于一个小型的电烙铁了。</span>

考虑一下功率如何发热.
## DC_DC
<mark style="background: #BBFABBA6;">DC_DC 可以用于比较高的电压转换.例如 : 12V - 5V,压差比较大.
原理: 相当于PWM波调制/开关MOS管调压,没有电阻因此发热量不大,效率极高</mark>


# 线性稳压器LDO与开关稳压器DC-DC
稳压电源(stabilized voltage supply)是能为负载提供稳定的<font color="#92cddc">交流电或直流电</font>的电子装置

开关稳压电源是通过把直流变成高频脉冲，然后再进行电磁变换实现电压变换和稳压。

线性稳压电源是直接串联一个可控的调整元件对输入<font color="#92cddc">直流电压进行分压，</font>实现电压变换和稳压，本质上相当于串联一个可变电阻。

<font color="#f79646">开关稳压电源</font>

效率高，
而且可升压也可降压。

<font color="#f79646">线性稳压电源</font>

只能降压，而且效率低。

开关稳压电源会产生高频干扰
线性稳压电源则无干扰。各有优缺点


<font color="#ff0000">123123132312312  </font>
<font color="#ff0000">3213123214324252</font>