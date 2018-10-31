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
