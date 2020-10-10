# ACM游戏指南

> 本篇转自 CustOJ，但做了一些修改。有些在页面上的链接或按钮，可能需要自行想象。

## 基础说明

参加ACM比赛的基本步骤:

1. 读题，对于题目所述特定的输入，要求你的程序给出特定的输出
2. 写代码，使你的代码编译通过并能正确运行。
3. 测试，可以使用样例数据，也可以自己根据题目出数据。
4. 提交，将你的代码复制粘贴到提交界面上。

题目的输入一般会给定范围，例如`(0<=x<=1000000000)`，该范围是由评测系统保证的，**不需要**选手做多余判断。

题目数据绝大部分方式为多组数据，是否需要多组输入会在输入描述内给出，多组数据需要循环读入，详情参考**后面的内容**。

若你使用本地的集成环境编译运行(如`Code::Blocks` `Dev C++`等，但我们不推荐使用`VC++6.0` `Visual Studio`)，请仔细阅读以下三条内容。

* 对于多组输入，在本地调试时会发现输入一行数据，就会有输出，这是**正常现象**。
* 对于不限定组数的多组输入，在本地调试时想要结束输入，可以尝试键入`Ctrl+Z`组合键，如果不行，再来一次就行了。
* 同时，请注意输入格式和输出格式要严格按照题目要求，不要有多余的**友情提示**等内容，例如`"请输入两个整数"`等。哪怕多/少一个空格或者回车都可能会导致服务器判断你的答案错误。

**但对于初学者，我们推荐使用导航条上的「调试&运行」，或使用其升级版——[CliOuDE](http://clioude.space)。它们部署在云端，无需自行搭建环境就可以使用。**

题目中给出的样例数据只代表测试数据中的**一小部分**，你可以用样例来帮助测试你的程序，但是仅仅通过样例不代表你的程序完全正确。

提交代码时请注意选择编译语言，默认C语言，如果选择了错误的语言会导致编译错误（Compile Error）。

**题目难度和顺序无关**，请自行寻找简单的题目，排行榜(Rank)可以帮助你更好的做到这一点。

提交的反馈结果情况如下：

* Accepted: 恭喜，你通过这个题目啦！
* Presentation Error : 你的程序已经接近正确，但输出格式与答案不符。
* Runtime Error:程序运行时出现错误（指针/数组越界，栈溢出，有未处理的异常，除数为0，主函数返回值非零等）
* Time Limit Exceeded:程序超时，存在死循环或者算法复杂度过高，指针/数组越界也可能导致这种情况发生
* Memory Limit Exceeded: 内存超限，存在无限递归或使用了过多的内存空间
* Compile Error:编译错误，确认你在提交时选择了正确的编程语言，并且在本机通过了编译调试
* Wrong Answer: 程序输出与答案不符

## 关于比赛

比赛时，从首页或导航条上的`练习&比赛`进入对应的比赛，不要直接点导航条上的`问题`。比赛题目独立在比赛中，而不是在oj的题目列表中。(如果你在比赛时做了A+B，很显然你进错链接了)

**交题时注意选择好语言！**

**样例对了不一定就是对的，请考虑到尽可能多的情况**

比赛页面的右边栏里包含了比赛所有的内容。比赛时尽量不要点导航条，以防离开比赛造成麻烦。

记得偶尔关注一下`公告`，可能会有一些比赛的补充说明

比赛的问题列表中，`Total`列表示该题所有参赛选手总共提交了多少次。`AC Rate`代表上述Total次提交中结果为正确的百分比。Total×AC Rate的值越大，表明这题过的人越多

`Rank排名`是个好东西。它比问题列表更清晰地显示哪一题过的人数较多。一般而言，过的人越多，题越简单。跟榜做题是一个优秀的比赛策略（除非你想抢First Blood，第一个通过该题）

* `Rank排名`页右上角的齿轮按钮里有设置，包括前十名图表显示、**真实名字显示**、院校显示。
* 比赛结束前1小时会封榜，即`Rank排名`页面不再更新。因此最后结果是在比赛结束后才揭晓的。
* 关于`TotalTime`(罚时):计算规则为每道试题用时将从竞赛开始到试题解答被判定为正确（AC）为止，其间每一次提交运行结果被判错误的话将被加罚20分钟时间，未正确解答的试题不记时。若错误为`Compile Error`，不记罚时。
* 比赛排名以通过题目数量降序为第一关键字、罚时升序为第二关键字排序。简单来说，做得越多越快，排名越高。
* `Rank排名`上显示为深绿色代表First Blood，即第一个通过该题。绿色代表该题通过，罚时会一并显示在上面。有时后面会带(-x)，表示交了错误的x次。**题目通过后，错误次数不会再增加。** 红色(-x)代表还未通过该题，已经尝试了x次。

## 循环输入格式

### 读取到文件尾/有多组数据但不输入具体数量

*   C

    ```
    while (scanf("%d",&n) != EOF) {
      Your code
    }
    // 解释:EOF是文件尾标志
    ```

*   C++

    ```
    // 可用C的输入，要加头文件 cstdio
    while (cin>>n) {
      Your code
    }
    // 可以多个，如while(cin>>a>>b)，也可以输入字符串等。
    // 解释:cin自动识别是否输入达到文件尾。
    ```

### T组数据

*   C/C++

    ```
    输入T;
    while (T--) {
      Your code
    }
    // Java 可以 T-->0。
    ```

## Java 注意事项

*   类名请使用Main，区别大小写，如下

    ```
    public class Main {
     public static void main(String[] args) {
         ...
     }
    }
    ```

*   Scanner输入慢，建议用下面这个。如果用Scanner出现超时情况，请先考虑更换输入姿势。

> StreamTokenizer与PrintWriter
> 
> 需要引的包与Scanner一样：`import java.io.*`
> 
> 首先定义输入输出流(记住就行)
> 
> ```
> StreamTokenizer in=new StreamTokenizer(new BufferedReader(new InputStreamReader(System.in)));  
> PrintWriter out = new PrintWriter(new OutputStreamWriter(System.out));
> ```
> 
> 判断是否到达文件结尾( 相当于Java`while (scanner.hasNext())`)
> 
> ```
> while (in.nextToken() != StreamTokenizer.TT_EOF)
> ```
> 
> 与Scanner不同的是 需要在每输入一个数前面加上`in.nextToken();`--> 表示指向下一个读入位置
> 
> ```
> in.nextToken();
> int t = (int)in.nval;
> ```
> 
> 对于每一次输出都要在后面加`out.flush();`表示刷新缓存区，如果不写，就不会输出了。
> 
> ```
> out.println(t);
> out.flush();
> ```
> 
> 在多组输入的时候`while (in.nextToken() != StreamTokenizer.TT_EOF)`已经包含`in.nextToken()`所以在下面的程序中第一个输入的前面不需要再加`in.nextToken()`了。
> 
> `in.nval` 返回值类型是`double`， 所以在输入int,float时需要强制转换，double就自然不用了。
> 
> `in.sval` 返回值类型是`String`。

*   下面是一个例子

```
import java.io.*;

class Main{  
    public static void main(String[] args) throws IOException {
        StreamTokenizer in = new StreamTokenizer(new BufferedReader(new InputStreamReader(System.in)));  
        PrintWriter out = new PrintWriter(new OutputStreamWriter(System.out));
        while (in.nextToken() != StreamTokenizer.TT_EOF) {
            int t = (int)in.nval;
            out.println(t);
            out.flush();

            in.nextToken();
            String s = in.sval;
            out.println(s);
            out.flush();

            in.nextToken();
            float f = (float)in.nval;
            out.println(f);
            out.flush();

            double d = in.nval;
            out.println(d);
            out.flush();
        }
    }
}
```

*   其他语言的多组输入格式，可以参考题目列表第一题:`多组输入A+B`