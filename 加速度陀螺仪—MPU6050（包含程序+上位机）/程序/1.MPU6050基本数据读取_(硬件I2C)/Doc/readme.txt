/*********************************************************************************************/
本文档使用 TAB = 4 对齐，使用keil5默认配置打开阅读比较方便。
【*】程序简介

-工程名称：RTC—日历实验
-实验平台: 野火STM32 F767 开发板 
-MDK版本：5.16
-ST固件库版本：1.1.0

【 ！】功能简介：
RTC的时间日期的配置。

学习目的：学习STM32的RTC。


【 ！】实验操作：
连接好配套的5.0寸液晶屏，下载程序后复位开发板即可，串口每秒打印一次当前日期时间。

【*】注意事项：
无



LTDC时钟频率：10MHz （可在LCD_Init函数配置）

【*】 引脚分配

液晶屏：
液晶屏接口与STM32的LTDC接口相连，支持RGB888、565格式，
STM32直接驱动，无需外部液晶屏驱动芯片.

		/*液晶控制信号线*/		
		CLK		<--->PG7
		HSYNC	<--->PI10
		VSYNC	<--->PI9
		DE		<--->PF10
		DISP	<--->PD4
		BL		<--->PD7
		
		/*电容触摸屏信号线*/		
		RSTN	<--->PD13
		INT		<--->PD12
		SDA		<--->PH5
		SCL		<--->PH4

RGB信号线省略,本实验没有驱动触摸屏，详看触摸画板实验。


SDRAM （W9825G6KH 32M字节）：
SDRAM芯片的接口与STM32的FMC相连。
		/*控制信号线*/
		CS	<--->PH6
		BA0	<--->PG4
		BA1	<--->PG5
		WE	<--->PC0
		CS	<--->PH6
		RAS	<--->PF11
		CAS	<--->PG15
		CLK	<--->PG8
		CKE	<--->PH7
		UDQM<--->PE1
		LDQM<--->PE0
		
地址和数据信号线省略，本连接的SDRAM基地址为 (0xD0000000)，结束地址为(0xD2000000),大小为32M字节
												
/*****************************************************************************************************/


【*】 时钟

A.晶振：
-外部高速晶振：25MHz
-RTC晶振：32.768KHz

B.各总线运行时钟：
-系统时钟 = SYCCLK = AHB1 = 216MHz
-APB2 = 108MHz 
-APB1 = 54MHz

C.浮点运算单元：
  使用

/*********************************************************************************************/

【*】 版本

-程序版本：1.0
-发布日期：2017-8

-版本更新说明：首次发布

/*********************************************************************************************/

【*】 联系我们

-野火论坛    :http://www.firebbs.cn
-淘宝店铺    :http://fire-stm32.taobao.com

/*********************************************************************************************/