## ROS机器人控制板
1. 既是ROS机器人驱动器，也是STM32开发板

2. 支持多ROS主控：Jetson系列、树莓派等

3. 板载MPU9250九轴IMU

#
micro USB数据接口：连接主机通讯和烧录程序

type-C接口：向外提供DC 5V，仅供电不能通讯

九轴姿态传感器：提供扩展板当前姿态

PWM舵机电压切换：改变跳线帽的位置可选择6.8V或者5V电压为PWM舵机供电。

PWM舵机接口：可连接6.8V或者5V电压PWM舵机，需根据舵机电压在⑯选择对应的电压

# 
引脚设置完成后按Ctrl+S保存

hex文件保存在工程目录的Debug文件夹中

mcuisp（或flymcu）为烧录软件

扩展板上的单片机进入烧录模式：先按住扩展板上的BOOT0键，再按一下RESET键，最后松开BOOT0键。

#
HAL_GPIO_WritePin(GPIOX, GPIO_Pin, pinstate)

GPIOX代表目标引脚的端口号，例如GPIOB。
GPIO_Pin代表目标引脚的引脚号，例如GPIO_Pin_5。
pinstate代表当前引脚的高低电平，高电平(GPIO_PIN_SET)、低电平(GPIO_PIN_RESET)。

HAL_Delay(200)

间隔200毫秒
#
将LED的控制做成宏定义的方式，简单快捷
#
（1）先给ROS板连接12V电池
（2）连接USB端口