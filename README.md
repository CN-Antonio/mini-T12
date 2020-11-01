# Mini T12焊台-基于Arduino平台-Atmege328p-au
![](https://github.com/jie326513988/mini-T12/blob/main/Picture/1.jpg)
#### 2020-10-30 V0.94功能完善100% ，默认支持深圳头，更换其他厂商的头需要自行校准温度曲线
### 接下来开始优化内存，制作更加漂亮的UI界面，类似EVA
* 动态调参PID
* 稳定时显示2秒内采集到的平均温度，其他时候显示实时温度大概500ma刷新一次
* 取消电流传感器，主界面取消电流显示改为显示PWM百分比
* 使用3段式曲线拟合绘制温度曲线，可在设置菜单“校准”选项调整
* 休眠计时和息屏倒计时改用定时器2计时
* 息屏显示，无加热无操作3分钟后进入，息屏时显示环境温度
* 开机提示音和开机画面
* 休眠时自动保存当前设置温度到eeprom
* 待机功耗8.8ma 息屏待机功耗6.4ma
#### 观看视频 https://www.bilibili.com/video/BV1vf4y1B7Xa
#### PCBv1.7,更换了DCDC降压芯片（JW5018B），放大倍数由510倍调至390倍，11月头验证没问题后放出
#### 按键功能定义
* 长按操作（5下短音最后1下长音）
  * 主界面，进入设置界面
  * 其他界面，退出至主界面
* 双击操作（2下短音）
  * 主界面，加热或停止状态切换
  * 其他界面，无
* 单击（1下短音）
  * 主界面，无
  * 设置界面，进入二级菜单
  * 二级菜单，切换数值更改选中状态，或确认更改数值，无选框状态则退出至一级菜单
#### 菜单选项
* PID
  * P
  * I
  * D
* 休眠
  * 休眠时间
  * 休眠温度
* 屏幕
  * 屏幕亮度
  * 屏幕方向
  * 编码器方向
* 电源
  * 基准电压
  * 电源电压
  * 低压报警
* 校准
  * 调节曲线第1段温度
  * 调节曲线第2段温度
  * 调节曲线第3段温度
  * 调节曲线第4段温度
  * 运行曲线拟合程序校准温度曲线
* 烙铁
  * 冷端补偿
  * 开机加热
  * 重置
#### 校准温度曲线的方法
* 1.准备好能测量0-500摄氏度的设备，探头建议使用裸装，以免外壳热传导导致热量损失测量不准
* 2.将探头紧压住烙铁头发热前段（上锡部分再下来一点），一定要紧紧压住，不然也会测量不准
* 3.放置好烙铁头以免校准时烫伤手或物品！
* 4.接上电源，从控制板进入‘校准’界面，将空心选框移动至第1段温度处（即对应的ADC 10下面）
* 5.按下确认键，此时空心选框变成实心选框，烙铁头开始加热，等待最下方的‘Now ADC’值稳定，大概等于第一行相应的ADC值（此时是ADC 10）
* 6.使用测量设备测量烙铁头的温度，将第1段温度调至测量得到的温度（实心选框状态可旋转旋钮调节数值）
* 7.依次测量剩下的第2段、第3段、第4段温度并输入至控制器
* 8.测量完4段温度后将光标移至Save，按下确认键，等待程序计时温度曲线
* 9.计算完会显示P系数界面，，再按下确认键即可退出校准界面
* 10.校准完毕

![](https://github.com/jie326513988/mini-T12/blob/main/Picture/2.jpg)
![](https://github.com/jie326513988/mini-T12/blob/main/Picture/7.jpg)
![](https://github.com/jie326513988/mini-T12/blob/main/Picture/3.jpg)
![](https://github.com/jie326513988/mini-T12/blob/main/Picture/4.jpg)
![](https://github.com/jie326513988/mini-T12/blob/main/Picture/5.jpg)
![](https://github.com/jie326513988/mini-T12/blob/main/Picture/6.jpg)
