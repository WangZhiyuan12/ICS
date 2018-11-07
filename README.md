# ICS
Learning ICS
# 复习2.4 floating points
## 单词
- rational 合理的
- involve 涉及的
- devise 设计
- craft 雕琢
- auspices 主持
- ultimate 最终
- rounding 四舍五入
- hence 于是
- arane 神秘的
- fractional 分数
- shorthand notation
- finite 有限的
- imprecision 不精准的
- disastrous 惨重的
- underlying 底层的
- interpretaion 解释
- biased 偏置
- gradual underflow 逐渐溢出
- round-to-nearist 四舍五入




## 知识点
- floating point表示法中小数点向左移动一位乘上2，向右移动一位除以2
- 0.1111.....1(2) =1-$
- 很多floating points 只能被粗略的表示
- 表示法通过 s符号位，M尾数位1-2-$或者0-1-$,E表示为2的阶乘次方
- float: s:31 exp:30-23 frac:0-22
- double s:63-62 exp:62-52 frac:51-0
- floating Normalized exp!=0 and 255
- floating Denormalized exp==0
- floating infinity exp=255 and f==0
- floating Not a number: exp==255 and f!=0
- normalized E=exp-Biased (floating biased=127 double biased=1023) floating E(-126-127) double E(-1022-1023) M=1+f(隐含的1.f的意思)
- Denormalized M=0.f E=1-Biase and exp=0
- Denoramlized 表示法的主要用途是1.表示为0,2.表示无线接近0的数。
- 四舍五入法可以降低统计上的偏差：4舍去，5看情况如果是偶数进位，奇数去掉。
- 浮点数加法不具备有结合性,由于会发生精度的缺失。
- 正无穷-正无穷=not a number
- 1/-0=-infinite
- 1/+0=infinite
- int -> float,可能会被舍入31bits->23bits
- int -> double 不会被舍入
- float,double -> int会向零舍入。

# 复习2.1
## 单词
- virtual memory 虚拟内存空间
- virtual address memory 虚拟地址空间 相当于一个很大的字节数组。
- programming object程序对象：数据，指令，控制信息。
- word-size 字长：表示计算机的虚拟地址的位数。
- exclusive-or 异或
- mask code 掩码
## 知识点
- 8bits=1 byte 作为最小可寻址的存储单元
- 如果是2^n的话，将n=i+4j,if(i==0，1，2,3)最高位依次为0,1,2,4,8之后跟上i个0，满足要求。
- 对于一个字长为w的计算及而言，虚拟的内存地址从0---2^w-1，最多为2^w个
- long int ,char*  32bits和64bits的所用的字节数不同。这时就要考虑可移植性。
- 对于 x=0x01234567，大端法：01 23 45 67， 小端法：67 45 23 01
- 字符串结束为null
- 二进制的数很难在机器之间移植，哪怕二进制代码相同，但是由于生成的程序结构有差别也不行。
- a&(b|c)=(a&b)|(a&c)
- DeMogen 定理
- 位向量的应用
- 位级运算就是进行二进制的运算，算完后将其转化成相应的进制数
- 逻辑运算和位级运算是不同的，逻辑运算认为结果只有true或者false
- 逻辑运算中存在着短路现象
- 左移：高位若无溢出则左移，溢出删去，低位补上0
- 1<<5-1应该认为1<<(5-1)优先级
- 右移分为算术右移和逻辑右移，逻辑右移高位补0，低位删去，而算术右移则是高位补上最高位的数值，低位删除。
- C语言中unsigned，逻辑右移，而signed则两种都可以，基本上都是用算术右移。

# 复习2.2
## 单词
- two-complement 二进制补码
- negative weight 负权
- U2Tw: unsgined to two's complement conversion
- T2U: two conplement conversion to unsigned
- B2T: define two complements
- B2U: define unsigned encoding.
## 知识点
- 整型数：有限范围的整数char:1 bytes short=2bytes,int =4 bytes,long = 8bytes
- signed相对应的最小范围为-2^8 /2~~~ 2^8/2-1 比如就是总数除以2 表示负数，而正数则总数除以2-1.
- B2Uw(x)是一个双射关系，一一对应。
- B2Tw 二进制补码表示法，就是最高位为符号位，当最高位为1时，表示为负数，这时最高位的权重为2^（w-1）
- TMinw = -2^(w-1)
- TMaxw = 2^(w-1)-1
- B2Tw也是一个双射的关系
- abs-TMin = abs-TMax+1,可见最小值没有相应的相反数与其对应。
- Umax=2TMax+1
- one complement二进制反码表示法最高位的权重为（2^(w-1)-1）
- 符号数值法，最高位为符号位，当1时最高位后的权重值乘上-1，否者乘上1
- 符号位的方法，中0的表示不具有唯一性，反码现在少用基本上都是补码表示。
- 有符号位无符号为的转化实际上就是讲同样的二进制数，按照不同的规则进行解释。
- 通过二进制表示法可以得知，有符号数x，当为正数时，直接进行转化，当为负数时在有符号数的基础上加上2^w就可以了
- U2Tw 当x<2^(w-1)保持不变，当x>2^(w-1)此时最高位为1
- 最小映射是T2Uw是在二进制补码表示法中之外的无符号数。
- 如果一个表达式中既含有signed，又有unsigned，则是隐式的转化为unsigned运算
- 小心无符号数和有符号数之间的隐式转化。
- short to int，当最高位为1是，上方的位数都不上一，否则补上0.
- mod数都当做是正数。
# 复习2.3
## 单词
## 知识点
- 在机器上做乘法运算速度很慢差不多要12甚至更多的实践周期，而做加法只需要1个时钟周期。因此编译器尽量采用移位运算和加法运算来代替乘法运算
- 如果是具有特定长度的二进制字符串则是先将二进制数移动后mod 2^w,也就是说二进制乘上2的幂溢出的处理方法和处理移位运算的方法相同。
- x<<k = x2^k mod 2^k
- 整数的除法比整数乘法还要慢。需要30或者更多的时钟周期
- 除以2的幂可以通过右移运算实现。对于unsigned 进行逻辑右移，signed则是进行算术右移。
- 所以x>>k =x/pwr2k,这里pwr2k等于2^k
- 如果是负数的话，我们需要用偏移量将将答案调成向上取整。如x/y,则偏移量为y-1.所以x/y=(x<0?(1<<k)-1+x : x)>>k
- 无符号数的乘法为xy=(xy)mod 2^w 无法超过w位
- 加法x的加法逆元-x,因为-2^(w-1)~~~ 2^(w-1)-1之间，所以-2^（w-1）不再加法逆元
- 二进制的补码表示的逆元 -twx=TMin x=TMin x>TMin -twx=-x ,也就是x的补码的非运算。~x+1
- 当x!=2^(w-1)不会溢出此时补码x+1,等于自然数中的x+1
- unsigned加法由于可能会溢出，所以不等同与自然数中的加法，但是等同与模数加法，丢弃最高位。
- C语言程序不会讲溢出当做是异常而发信号。
- 判断溢出的方法，就是结果s<x 和s<y成立的时候
- 阿尔贝群的定义，可交换和可结合，有一单位元0，并且每个元素有一个加法逆元。w位的无符号的数的几何，执行加法（有位数的限制），对于每一个值都存在-想，时期满足x+(-x)=0
- 加法逆元x=0时，-x=0,x>0时，2^w -x x>0 此时满足，(2^w-x+x)mod 2^w=0

# 复习3.1-3.2
## 单词
- flat addressing model单平面寻址模式：将地址看作是一个大的字节数组
## 知识点- 
- gcc -O2 -o p1.c p2.c其中-O2中的2表示的是第二级优化。提高优化级别会使得程序运行的更快，但是编译的时间会增长。对代码调试会更加困难
- 编译的过程，首先是预处理器扩展源代码，出入所有用#include命令中的指定的文件，并且扩展所有的宏，其次是编译器产生源文件的汇编代码生成p1.s，接下来就是讲汇编代码转化成二进制目标代码，然后就是，通过连接器实现与操作系统函数的链接。生成可执行文件。
- 汇编代码可以将抽象的高级语言转化成
- %rip表示程序下一条要执行的指令在存储器中的地址。
- 整数寄存器用于存储和记录某些重要的程序状态，或者是可以作为存储器临时保存数据。
- 条件代码寄存器中保存着最近执行的算术指令的状态信息，来实现控制流中额条件变化。
- 浮点七寸器中，用于存放浮点数据。
- C语言中将存储器看成为一个很大的，按照字节寻址的数组，C语言中的各种数据类型和结构，都是用连续的字节表示的，汇编代码不区分sign和unsigned，不区分到底是主句还是指针，
- 程序存储器中包含着程序的目标代码，操作系统信息，和用于管理过程电泳和返回的运行时栈，以及用户分配的存储器模块。
- 程序存储器是通过虚拟地址来寻址的，一个程序一般只会用nM，所以操作系统可以将虚拟地址转化成实际处理器存储器中的物理
- gcc -O2 -S code.c 其中的-S表示为将C语言文件编译成汇编代码。
- gcc -O2 -c code.c其中的-c 表示会产生二进制格式的代码。
- 可以利用gdb中的x/19b sum 来观察函数的字节表示法。
- 通过观察反汇编代码中的可以看待指令长度从1-15个字节不等，一条指令字节中可以表示出一条指令。
- 反汇编器只根据目标文件中的字节序列来确定汇编代码。
- 指令格式是按照一定的方式设计的，从某一个给定的位置开始。
- nop，叫做no operation，只是为了填充存储该过程的空间。
- 如果量程序链接在一起的话，那么其中的函数和变量的地址会发生改变。
- 在汇编代码中出现的.开头的段落都是为了指导汇编器和链接器的链接。
 # 复习3.3
 ## 单词
 ## 知识点
 - 1word=2bytes
 - double word=4bytes
 - quad words= 8bytes
 - char* = quad words;
 - char* =byte
 - short= 1word
 - int=2word;
 - long= 4words
 - double =4 words;
 - floate=2words
- movl如果是整数类型的话，则表示为4bytes,如果是浮点数的话则表示为8bytes
# 复习3.4
## 单词
- operand 操作数：要引用的数据值以及放置结果的位置。
## 知识点
- 寄存器主要是为了存储指针和数值
- 在平面寻址中对寄存器的特殊不同功能已经降低了，但是仍然有一些指令事宜特定的寄存器作为源和目的的
- %ebp 和%esp则保存这指向程序栈中重要位置的指针。
- %rbp-callee saved
- %rsp -stacck pointer: 表明stack run-time end position
- %rax return value
- 源数值可以是立即数，也可以是从寄存器或者存储器中读出，结果应该放在寄存器或者存储器中。立即数就是指的是常数值，$后面跟着的是常数。
- 寄存器就是可以直接表示寄存器中的内容，用ra表示为寄存器a，而R[ra] 则表示为他的值
- 可见的是寄存器放于一个寄存器数组中，数组中的元素则通过寄存器的ID进行好下标。
z- 还有就是存储器的使用，会根据有效地址进行访问某个存储器中的位置。
- 我们有不同的寻址模式。
- 对于mov语句，可以实现immediate--> register, register-->register memory-->register.immediate-->memory,register-->memory
- movsbl(符号位扩展），movzbl(零扩展)




