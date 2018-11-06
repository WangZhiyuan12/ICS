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

















