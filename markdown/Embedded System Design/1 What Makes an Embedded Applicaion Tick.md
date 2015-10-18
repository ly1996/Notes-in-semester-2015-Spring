#What Makes an Embedded Application Tick
##一、嵌入式系统的数量
* 美国家庭平均拥有40个微处理器  
不包括：
	* 电子计算机，包含5~10个
	* 汽车，包含几十个
* 接下来的几十年中将增加100倍  
约以5年为周期的指数递增
* 大多数人兵马俑意识到嵌入式设备的存在
##二、开发的挑战
###1.多处理器
通常将不同的功能分配给不同的处理器执行

* 主要的挑战在调试上  
在单CPU上，调试嵌入式软件相对成熟  
在多核上，调试增加的整体的困难
###2.有限的内存
* 容量并不小，但不是想增加就能增加的
* 成本与功耗考虑  
不同档次面对不同的市场需求，形成产品线  
*对传统嵌入式开发者而言，资源的增加是很奢侈的*
* 需要程序优化
* C++  
有足够的理解才能使用，否则存储和实时性都可能存在问题
###3.用户接口
非常重要，主要由软件来实现
####理想步骤
* 设计硬件
* 制作原型
* 实现软件  
主要是用户界面
* 在设备上试用并进行精化和再实现
####UI的开发问题
* 硬件不可用
* 设计没有完成
* 在宿主机上使用原型或仿真技术
###3.可重用软件
传统的开发将软硬件都掌握在开发人员掌控下  

**但现在不行**

* 软件太大太复杂  
开发人员不可能拥有所有专业技能
* 推向市场的时间压力
* 硬件重用在设计上被广泛接受，软件也理应如此
##三、软件组件
###1.RTOS
* 有多种版本，可大可小
* 需要对这些RTOS有足够的理解，了解互相的差异
####RTOS选择的因素
* 硬实时
* 版权费用
* 技术支持
* 工具
* 易于使用
* 网络的支持  
在IoT的背景下需要更多地考虑
* CPU系列的支持
####RTOS的标准
* 种类非常之多
* 达到不同系统间的互操作性
#####常见标准
* OSEK/VDX  
在电子、汽车领域被广泛接受
* μiTRON  
在日本被使用，可以在此基础上构建大量的中间件
* POSIX  
从UNIX上移植
###2.文件系统
* 嵌入式系统需要持久化的存储器  
磁介质、光学、NVRAM……
* 需要标准化的形式和方法
	* 互操作性
	* 传输
* MS-DOS是最好采用的
###3.USB
* 越易用的东西实现越困难
* 实现相应特性的部分是软件而非硬件
* 协议要被宿主机和嵌入式设备支持
###4.图形
####两大功能
* 图形输出
* 用户交互
####需求
需要额外的库提供图形输出的支持
###5.网络
* 有线/无线
* TCP/IP可能是很好的选择  
但在应用中使用会是挑战
####IPv6
####谁需要服务器
对嵌入式系统而言，也就是C/S模式和B/S模式的选择

* 使用自定的协议和接口以客户端访问
* 通过网络协议以Web方式访问
####SNMP与Web Server
#####SNMP
* 内置的复杂安全特性
* MIB（管理信息库）可被轻易地添加
* 浏览器格式固定
* 浏览器需要付费
#####Web Server
* 可使用SSL
* HTML与直接编码
* 接口可由应用程序定制
* 浏览器免费