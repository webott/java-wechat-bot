# java-wechat-bot
java 微信机器人-x86汇编语言介绍
逆向，是指逆向工程。所谓的逆向工程是什么呢？下面引用某软件工程书籍中的一段话：“术语“逆向工程”源自于硬件领域，是一种通过对产品的实际样本进行检查分析，得出一个或多个关于这个产品的设计和制造规格的活动。软件的逆向工程与此类似，通过对程序的分析，导出更高抽象层次的表示，如从现存的程序中抽取数据、体系结构、过程的设计信息等，是一个设计恢复的过程。”
对于黑客来说，主要是通过反汇编或调试等手段来分析软件，小到软件的某个技术实现，大到软件的框架结构。逆向工程在计算机领域的应用面非常广泛，除了人们熟悉的软件破解外，还包括（不限于）对恶意软件的研究、对加密算法的研究、对软件保护技术的研究、对二进制代码的审计、研究同类型的竞争软件技术等。逆向的应用如此之广，但是其基础知识不外乎几个方面：调试工具、逆向分析工具、汇编语言、高级语言和高级语言生成的二进制代码所对应的反汇编代码。本章由汇编语言开始逐步介绍逆向相关的基础知识。
  5. 1x86汇编语言介绍
读者想在逆向方面有一定发展的话，最好买一本汇编语言的书籍来进行学习。现在计算机专业毕业的学生都学过汇编语言，但是大部分人认为学的只是Intel 8086下的汇编指令，枯燥、乏味、不具备实用性。其实，作为汇编语言的入门，学习8086的汇编指令已经基本足够了。目前的硬件都是x86兼容架构的，无论多复杂的程序，最终都将成为x86指令。作为逆向的入门，只要掌握8086的常用指令、寄存器的用法、堆栈的概念和数据在内存中存储的顺序基本就可以了。
对于入门，有以上知识就足够了。如果想要有深入的发展，对于汇编语言的学习还是要深入研究。本章站在逆向工程入门的起点，抛开各种原理及理论知识，只简单讲述x86常用的汇编指令的用法。
5. 1. 1 寄存器任何程序的执行，归根结底，都是存放在存储器里的指令序列执行的结果。寄存器用来存放程序运行中的各种信息，包括操作数地址、操作数及运算的中间结果等。下面来熟悉各种寄存器。
1.CPU工作模式x86体系的CPU有两种基本的工作模式，分别是实模式和保护模式。实模式也称为实地址模式，实现了Intel 8086处理器的程序设计环境。该模式被早期的Win 9x和DOS所支持。实模式下可以访问的内存为1MB.实模式可以直接访问硬件，比如直接对端口进行操作，对中断进行操作。现在的CPU 仍然支持实模式，一是为了与早期的CPU架构保持兼容，二是因为所有的x86架构处理器都是从实模式引导起来的。保护模式是处理器主要的工作模式，Linux和Windows NT内核的系统都工作在x86的保护模式下。保护模式下，每个进程可以访问的内存地址为4GB,且进程间是隔离的。实模式和保护模式之间的区别绝不仅仅是上面介绍的这么简单，但是对于入门而言，了解上面的内容已经够了。
2.基本寄存器介绍寄存器是CPU内部的高速存储单元，访问速度比内存快得多，而价格也高很多（在单位价格内，寄存器的价格要比内存贵，内存要比硬盘贵）。CPU中，常用的寄存器分为4类，分别是8个通用寄存器、6个段寄存器、1个标志寄存器和1个指令指针寄存器，如图5-1所示。（1)通用寄存器通用寄存器主要用于各种运算和数据的传送，每个寄存器都可以作为一个32位、16位或8位来使用，如图5-2所示。
![image](https://user-images.githubusercontent.com/73727649/198207087-d8e84d0e-6822-4680-9421-c2c42e8155f1.png)
个人微信
目前已经实现了很多有趣的功能，运行稳定，比如：发各种消息，
接收各种消息，群管，下载文件，加好友，检测僵尸粉，朋友圈等等功能，
可提供接口，方便各种语言二次开发，欢迎技术交流，Q：2645542961
，请勿用于商业用途。
![image](https://user-images.githubusercontent.com/73727649/198207288-cdaff9ea-3414-4c11-8271-4d018a1506f9.png)

企业微信：
目前已经实现了大部分功能，运行稳定，比如：发各种消息，
接收各种消息，外部群内部群管理，下载文件，加好友等等功能，
可提供接口，方便各种语言二次开发，欢迎技术交流。
