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


# 复习2.1
## 单词
- virtual memory 虚拟内存空间
- virtual address memory 虚拟地址空间 相当于一个很大的字节数组。
- programming object程序对象：数据，指令，控制信息。
- word-size 字长：表示计算机的虚拟地址的位数。
## 知识点
- 8bits=1 byte 作为最小可寻址的存储单元
- 如果是2^n的话，将n=i+4j,if(i==0，1，2,3)最高位依次为0,1,2,4,8之后跟上i个0，满足要求。
- 对于一个字长为w的计算及而言，虚拟的内存地址从0---2^w-1，最多为2^w个
- long int ,char*  32bits和64bits的所用的字节数不同。这时就要考虑可移植性。
- 对于 x=0x01234567，大端法：01 23 45 67， 小端法：67 45 23 01

























