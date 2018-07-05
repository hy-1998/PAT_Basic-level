# PAT_Basic-level 

## 写在前面

## 题解报告

* 1001 水题 **简单模拟** 偶数每次除2，奇数每次乘3加1再除2 注意每次处理完后重新判断是奇数还是偶数

* 1002 水题 **简单大数运算** 先用字符串数组存储好每一位对应的拼音，对每一位求和后再拆开数字，对着拼音数组输出

* 1004 水题 首先定义结构体存储学生信息，再对学生成绩进行排序，自己写了个冒泡，但其实用vector存结构体再用容器本身的**sort排序**更省时间

* 1005 简单题 首先定义结构体存储每个数字的信息（主要包括数字本身以及它能覆盖的数），然后写一个函数，寻找数字a所能覆盖的数，存到数组n里，对于每一个数字的覆盖数组n，都将它与给出的这列数字比较，判断是否为关键数（这里用了三重循环，不过处理的数据量比较小，暴力还是能过）

* 1006 水题 **分解**每一位数字，根据题意循环输出即可

* 1007 水题 从2到给的数字区间**找素数**，然后判断相邻两个的差是否为2，计数即可

* 1008 水题 因为不让再用数组，所以把原来的数组开大一点，存两次数据。循环右移m其实就是小标加m再**取模**的过程

* 1009 水题 这道题的关键是要找到句子中**空格的位置**（包括句首以及句尾的空格），然后从倒数第二个空格开始，连续输出它与下一个空格间的内容

* 1010 水题 这里我用的do-while语句输入（一个小技巧，当输入不给数据量的时候，可以用如下输入方式）然后分两种情况，即存在常数项和不存在，存在常数项又得区分是否为零多项式，因为零多项式是需要输出的，而非零多项式的常数项不输出
```C++
do
{
	cin>>a;
	count++;//计数
}while(cin.get()!='\n');
 ```

* 1011 水题 这个数据范围用**longlong**定义再加一下就好

* 1012 水题 **分类**，第一类数是10的倍数，第二类判断一下-1的次方再进行混合运算，第三类计个数，第四类求个和，第五类可以先用一个数组单独存起来再sort一下

* 1013 简单题 这道题它最多就是第10000个素数，所以**先把前10000个素数找到**存在数组，然后输出的时候就从这个数组遍历，注意一下输出的格式

* 1014 简单题 这道题有点坑，首先第一对相同的大写英文字符必须要在**A到G**之间，然后第二对相同的字符可以是0到9之间的数字，也可以是**A到N**之间的大写字符，最后一对相同的字符排除掉&，输出注意**补0**

* 1015 中档题 这道题的数据量很大，所以很容易出现超时或者数组越界的情况。我的做法是，首先用vector进行数存储，然后用容器自带的sort函数来节省时间，这里需要自己定义一个**比较函数cmp**，最后说明一下scanf与printf是要比cin和cout快的。至于题目本身的逻辑很简单，分四类比较就好

* 1016 水题，找出A中Da以及B中Db的位数即可，A、B数据量大用string存

* 1017 中档题 简单的**除法模拟** 除数很大，用string存。然后从高位开始算，如果第j位大于被除数，直接除即可，然后余数再赋值给第j位；如果小于，则需要从第j+1位借位运算，余数赋值给第j+1位，特别注意只有此时才执行j++。这个循环因为有j+1，所以实际上做到了倒数第二位。对于**除数是1位的**，一定要单独考虑。

* 1018 水题 定义结构体存每一回合数据，vector存结构体。每一回合根据规则判断胜负，甲胜的次数就是乙输的次数。记录甲乙每种手势胜的次数，然后找到最大的对应的下标，输出手势字符。

* 1021 水题 字符串输入，每位数计数即可

* 1022 水题 进制转换，注意**倒序以及和为0**的情况

* 1023 水题 将第一个不为0的数作为首位，其余位从小到大输出即可

* 1024 简单题 这道题其实逻辑很简单，但是坑有点多。首先分类，看它的指数是大于0还是小于0。小于0的话就前面补0，大于0的话就后面加0。但有一种情况特殊，就是**E的次方数小于小数部分的位数**，此时小数点仍然右移，但后面不会添0（测试点4过不了就是因为这个）。还有一种情况是指数为0的情况，也必须单独考虑（但测试点里好像没有这个坑，不写也能过）

* 1025 难题 这道题可以说是乙级里最难的了，我写的第五个测试点超时了过不了，实在是脑壳疼所以就不想再改了，哪天想起来再说吧。先说一下思路：就是你得先把整个链表捋顺了，从头结点到尾节点，然后开始每k个进行反转，最后k个不反转。数据用vector型的结构体来存，因为这道题数据量比较大。注意输入的数据存在不在链表上的节点，所以要将链表上的节点存在新的vector里，之后再对这个vector进行操作。在捋链表的时候记录下每个节点在链表中的实际位置（下标），然后利用重构sort函数的排序实现反转，同时注意修改每个节点的指针域。同时如果不存在不足k个的节点，最后一个节点指针域要手动修改成-1；存在就不需要。最后就是注意下地址和指针用string存，不然输出麻烦。

* 1026 水题 秒数转换成小时、分钟与秒，注意一下数据用double还是int定义，再就是四舍五入的小技巧 **int (a+0.5)**

* 1027 水题 首先分析下给出的n个字符能用到多少个以及能输出多少行，可以推表达式，我图简单就用循环来判断了。然后先从上向下打印到输出3个字符的那一行，再向下打印，每行的字符数和空格数推一下就好

* 1028 水题 这道题逻辑很简单，对于每一个输入的数据判断一下是否在给定的时间范围内，用vector存了以后排个序即可。但是这题有两个坑点，一个是数据量比较大，用cin和cout会超时，所以要用**scanf与printf**；再就是要考虑所有数据都无效的情况，单独输出

* 1031 水题 用字符串存每一个身份证号，然后对前17位**加权求和再取模**，判断校验位是否正确

* 1032 水题 先用一个数组存下每个学校的总分，再在这个总分数组中顺序遍历找到**最大值**即可

* 1036 水题 注意为奇数时行数需要四舍五入，即int(a+0.5),然后就是分别处理第一行、中间行以及最后一行

* 1037 水题 先将钱都转换成以纳特为单位再相减，注意一下谁大谁小，最后再转化一次

* 1038 水题 这道题就是**桶排序**的思想，对于每个分数都统计下有多少个人再存在数组里，最后从数组里输出即可

* 1039 水题 对于摊主的珠串和小红的珠串，都顺序遍历一遍，统计下他们都有哪些珠子以及有多少个，然后对于小红想要的珠子，查询摊主的那个珠子有多少个，如果小于等于小红的，就做差（不能直接做差，因为摊主可能有多余的珠子），最后如果差的和为0，就说明可以买；否则就不可以，而且差的和就是差的总珠子数

* 1041 水题 这道题很简单，首先用一个结构体数组存储所有的数据，再根据给出的试机座位进行遍历求出考试座位与准考证号即可

* 1042 水题 首先对于有空格的字符串的输入，要用**getline**，然后遍历每一个字符，对其中的英文字符计数，最后输出出现次数最多的字符与次数即可

* 1043 水题 这道题考察的就是一个**简单循环分支**的判断，首先得到P,A,T,e,s,t各有多少个，然后再顺序输出，每输出一次其个数减一，如果个数等于0了就不用再输出了

* 1045 简单题 这道题考察了一些简单的算法，显然如果你想对每个数据都遍历它左边的所有数是否都比它小，右边的所有数是否都比它大是会超时的。其实我们可以这样想：既然要比左边的所有数都要大那就等价于**大于左边数的最大值**，比右边所有数都小那就是要**小于右边所有数的最小值**。那么我们可以从左往右遍历一遍，找到每一位数它前面数的最大值；再从右往左遍历一遍，找到每一位数它后面数的最小值。需要注意的是第一个数的左边数的最大值可以认为是0，最后一个数的右边数的最小值可以认为是无穷大。最后这道题有一个坑点就是主元数为0时，需要再输出一个换行

* 1046 水题 对于每一行的数据，都判断一下甲和乙喊的数字之和是否等于甲或者乙划的数字，注意一下不可以有**同赢**的情况

* 1047 水题 这道题就是对于每个输入，累加一下该队伍的总成绩，然后找到成绩最高的。但是我想强调一下输入的问题，我一开始用的cin输入，因为前两个队号队员编号连在一起了，只能用一个string变量来存再转成int型这样就很麻烦，后来看到别人用的**scanf输入**发现超级简单，所以很多时候对于特定格式的输入可以优先考虑scanf

* 1048 简单题 这道题逻辑不难，就是对奇数位和偶数位分别做不同的操作，但是做的时候却发现了自己对串的基本操作极其不熟练，后来参考了柳姐姐的代码，发现她的代码真的写的既简洁又漂亮，自己也写了一份。首先一定要考虑到当两个字符串长度不等时需要`补足0`，这里可以用类函数**append**，然后因为个位是第一位，为了简单我们可以将整个字符串反转一下，用swap函数。在操作的时候，因为数组下标是从0开始的，所以实际上对奇数和偶数的操作的相反的。最后如果想往字符串c里加字符，是可以直接用c+=，这我还是第一次知道。。

* 1049 水题 这道题其实没什么好说的，关键就是**找规律**，我们发现第i个数（i从0开始）出现的次数是(i+1)*(n-i)，最后乘起来求和就好

* 1051 水题 这道题稍微推导下就能求得A和B的表达式，但在输出的时候会比较坑。**比如当数字在-0.005与0之间时，用%.2f输出的是-0.00而不是0.00**，对这部分数据要特别处理一下

* 1052 简单题 这道题注意一下每个符号集的符号都是一个字符串，所以存的时候用一个二维的vector（用二维数组的话没法判断每一维的大小）。取符号集的时候用j,k分别标记左括号与右括号的下标，再用**substr**取中间的子串即可

* 1053 水题 这道题很简单，就是每一组数据遍历一遍，看看有多少天的用电量少于阈值，唯一需要注意的就是**没有既是可能闲置又是闲置**的情况

* 1054 简单题 这道题的关键在于判断字符串是否合法，遍历每一个字符，如果第一个是负号就跳过，设置一个标志位判断是否出现了小数点（防止多次出现），记录一下小数点后面的位数，最后用atof函数（ascaii to float）判断数字大小是否符合要求。然后注意一下输出的时候，**如果只有一个数，那个number是不加s的**

* 1055 简单题 这道题逻辑不难，首先理解一下什么叫字典序，比如Amy和Tim同样高，则认为Amy更高。实际上我们可以直接比较它们名字的字符串，更小的就更高。首先把所有人的身高从高到低排序，先处理最后一排，计算最后一排有多少人，再把最高的人放到中间，之后的人按照先左后右的顺序排，这里可以用**奇偶**来判断处理。对于非最后一排的，因为它们每一排的人数都确定了，就直接先找到中间的位置，再按照先左后右的规则排就好

* 1056 水题 因为是求所有组合出来的两位数的和，我们就简单判断一下每个数字出现在十位与个位的次数都是**n-1**，之后累加求和就好

* 1057 水题 遍历每一个字符，如果是英文字母，就累加一下求序号和，最后十进制转二进制数一下有多少个0和1，唯一需要注意的是输入用**getline**，因为它给的字符串是有空格的

* 1058 简单题 这道题感觉更多的是在考察输入与输出，对每道题选项的存储最好用字符串，这样的话比较起来简单。遍历每个学生的每道题，对了就加分，错了记录的次数就加1

* 1059 简单题 对于所有得奖的队伍，可以分成三种：冠军获得神秘大奖，排名素数的队伍得到小黄人（**可以先把10000以内的素数找出来，而不是输入名次的时候再判断**），其它队伍得到巧克力。同时我们需要两个标志位，一个表示所查的ID是否在排名里，一个是该队伍是否已经领过奖了，最后需要注意一下输出队号要是4位的，printf可以直接用** %04d **

* 1060 中等题 这道题题意理解起来有点费劲，特别注意两个地方，首先爱丁顿数可能不是骑行公里数，其次要求的有E天骑行公里数大于E公里是至少E天，即大于等于E天的都可以。算法如下：首先找到骑行公里数的最大值与天数两者的最小值max，因为爱丁顿数必然小于等于max。然后把骑行公里数组tem从大到小排个序，max从其本身到0遍历，找到max在tem中的位置i**（tem[i]>max&&tem[i+1]<=max）**，如果**i(骑行公里大于max的天数)大于等于max**的话，它就是爱丁顿数了。

* 1061 水题 对于每个学生的答案，都和标准答案比较一下，如果正确就加上该题的分值

* 1062 简单题 这道题注意两点：1.判断分数的大小最好用乘法，比如**m1/n1>m2/n2等价于m1*n2>m2*n1**，如果用小数比较的话精度可能不够   
2.两个数互质等价于两个数的最大公约数等于1，求最大公约数的函数gcd要记住：
```C++
int gcd(int a, int b)//计算最大公约数
{
	return b == 0 ? a : gcd(b, a % b);
}
```

* 1063 水题 对于每一组数据，求一下两个数平方和再开方的值，找最大的即可

* 1064 水题 对于每一个输入计算一下它的各位数字之和i，然后计数数组count[i]++，最后输出count非0的数，如果要记录有多少个不同的朋友证号的话，仅在count**从0变到1**的时候计数

* 1065 简单题 这道题思路还是比较清晰的，但就是注意一下落单的人不只是没有伴侣的人，**还有有伴侣但是伴侣没有来参加聚会的人**。我们开两个map，tem用来存每一对情侣（注意如果a,b是情侣，要分别以a,b为关键字存一次），peo用来存储来参加聚会的人，遍历peo，如果他在tem的值为0或者他的伴侣在peo中的值为0的话，就说明他落单了

* 1066 水题 对于每一组数据，判断一下输入是否在给定区间内，是的话就用特定值替换一下，最后输出注意要是三位

* 1067 水题 题意很简单不多说，但有几个坑点需要注意一下。首先，正确密码是不含空白符的，但这并不意味着输入的密码也不含空白符，所以输入必须用getline而不能用cin；其次，**遇到#必须要立刻退出**，而不能输出Wrong answer:#；最后，当n次尝试都失败时，先输出Wrong answer：错误密码，再输出Account locked，接下来的输入不用再理会

* 1068 简单题 这道题很坑，因为题目要求的“一点红”明明是该点的颜色与其周围8个相邻像素的颜色差充分大，但实际上测试样例里是**有边缘像素点**的。对于边缘像素点来说，默认它和它的那些不存在的方向上的像素点色差充分大。在开数组的时候，我们可以开大两个长度，并初始化所有像素值充分小，这样就不用判断边界情况了。还有一点就是记录每个颜色出现的次数可以用map，如果用桶排序的思想的话会浪费很多空间

* 1069 简单题 这道题有一个坑点就是新抽中的人可能之前就中过奖了，总体思路就是第一个中奖人的序号是s，接下来中奖人的序号应该是**s+=n**，但如果抽中的人是已经中过奖的了，就需要**s++** （我原来用的是另一种算法，不过看了柳姐姐的发现这种算法要简单很多）

* 1070 简单题 这道题严格来说是道数学题，因为要让总绳长最大，那么**越长的绳子折叠的次数应该越少，越短的绳子折叠的次数应该越多**。我们先把绳长从低到高排序，先选出的两根最短的绳子的折叠次数应该n-1，接下来每根绳子的折叠次数逐次减1

* 1071 水题 对每一组数据先判断下下注是否超过筹码总数了，再判断是输是赢，唯一需要注意的是**如果全输光了整个游戏就结束了**，也就是不用再考虑接下来的投注了

* 1072 水题 对于每一个学生，遍历他所有的物品看是否在缴纳清单内，在的话就记录一下，最后输出物品编号要注意必须是**四位**的

* 1073 中档题 这道题其实和1058是很相似的，但是1058里并不需要判断那种少选的情况，而且也不需要统计每道题的每个选项的错误次数。其实我觉得这道题蛮难的，可是PAT上这道题的AC率却挺高，可能是有更一般的解法吧。这里我推荐一种更好的解法：我们分别用00001,00010,00100,01000,10000（十进制为1,2,4,8,16）表示正确选项a,b,c,d,e。如果正确选项是ae，那么其对应的二进制为10001（十进制是17），如果考生的选择也是ae(10001),那么两者**异或结果为0**；如果考生没有全选对，那么结果就是1。接下来我们再判断少选与错选，如果之前的**异或结果为1且考生的选择与正确选项或的结果为1**，那么说明考生少选了（比如考生选择了a，也就是00001）。而对于每个题目每个选项错误次数的判断，我们可以**用之前异或的结果与每一个选项对应的数做与运算**，如果结果非0，则说明考生该选项少选或错选，注意这里的错误既包括少选又包括错选。

>>在这道题的同时，我想强调一下几个输入输出的问题：  
1.scanf和printf是要比cin和cout快很多的   
2.scanf在读入字符的时候，是会读入空格的，所以如果你用scanf循环读入字符，一定要小心   
3.如果你用getline读入字符串而且前面还有别的输入时，记得用getchar()读掉上一行末尾的换行符，不然getline的第一个读入就会是换行符

* 1074 简单题 这道题和1048比较相似，都是先把数进行反转，然后**补0**让两个数长度相等再每一位做加法运算，最后再反转输出。这里需要注意的是**最高位可能出现的进位**以及反转后结果的前几位可能是0且不要输出。唯一的坑点在于结果可能就是0，所以对这种情况要单独输出一下

* 1075 中档题 这道链表题还是有一定难度的，想要AC不是那么容易（和1025有一些相似）。说几点注意的地方：  
1.把存储节点的数组开大，存储的时候**节点的下标就是其地址**，而不是顺序存储，然后再遍历一遍找下一个节点，这样肯定会超时，然而由于数组开的太大，代码在vs都没法运行，只能直接交到PAT测评机让它跑（PAT对时间复杂度的要求远高于空间）   
2.在将所有节点根据其数据域大小分别存放到三个vector里时，循环终止的条件**不应该只是i小于节点个数，还有某个节点的next域是否为-1**，因为所给数据可能有不在链表上的节点，不判断有一个测试点是过不了的   
3.将三个vector合并可以用内置的**insert**函数   
4.输出每一个节点的next值时可以直接输出下一个节点的地址，而不需要提前把每个next值修正一遍，这样可以大大节省时间

* 1076 水题 很简单的题目，思路就是找到每道题的正确选项再转成对应的数字字符即可

* 1077 水题 这道题就注意两个地方：首先对符合要求的分数进行**排序**，这样可以很容易去掉最高分与最低分；再就是在之前的运算中都用double精度，最后再四舍五入成整数，如果一开始就用int精度会有误差

* 1078 水题 首先输入用getline，因为字符串里有空格。如果是压缩，就要对相同的字符进行计数，如果出现了多次再把该数字从整型转成字符型存到字符串里；如果是解压，就要把数字从字符型转成整数型再循环打印字符

* 1079 简单题 这道题考察两个点：一个是用string做大数加法运算，算的时候需要注意一下最高位的进位；另一个就是**reverse函数**，它可以对字符串进行反转直接判断回文

* 1080 简单题 这道题改了很久还是只能拿19分，也看了很多人的代码，发现思路都是一样的，但我就一直AC不了，（摊手。思路如下：首先我们可以利用map完成学号到平时编程成绩、学号到期中成绩以及学号到期末成绩的映射（map的一些常用操作我会在1085总结）。在平时成绩这块，我们可以只处理分数大于等于200的，然后遍历平时成绩的map，再计算每一位学生的总评成绩，大于等于60的就合格，唯一需要注意的是学生可能没有期中成绩（用期中的map是否为0判断），最后自己写个比较函数再sort排序输出即可

* 1081 水题 这道题有一个比较坑的地方就是在用cin读个数n和getline读字符串之间必须**用getchar()把第一个换行符读了**。其它的就是简单的分支比较了，但要注意一下比较的优先级，首先是长度是否过短，再是是否有非法字符，最后才是是否缺数字、字母或者完美

* 1082 水题 每组数据计算下到靶心的距离，找最大值与最小值即可

* 1083 水题 做一次循环，用它自己减去它的次序，然后用桶排序的方式存，最后输出出现次数大于等于2的

* 1084 水题 这道题其实和1078挺相似的，就是遍历出每个字符重复出现的次数，再按照字符、出现次数的方式输出，和1078不同的地方就是这里出现了一次也要输出一个1，而且这里出现次数没有超过10次的

* 1085 中档题 这道题AC的唯一方法就是用map容器。首先面说一下这道题的大体思路：对于每一组输入，先将学校名的字符串全转成小写（利用**tolower函数**），再对学校与成绩、学校与人数的map处理。然后遍历学校成绩的map，将相关信息存入vector里。最后自己写个cmp比较函数进行输出。但这里需要注意一下排名的输出：因为排名存在并列的情况，所以**如果这个学校和前一个学校成绩相同（并列）则排名不变，否则排名为其数组下标加1**。

>>map实际上可以认为是一种哈希，就像数组一样，只不过数组是从整型数到其他类型参数的映射，而map可以是任何类型参数到任何类型参数的映射。实例化map需要两个参数，第一个是关键字，另一个是关键字对应的值。关于map的一些常见操作有：实例化：map<string,int> m;插入数据：m[string]=int;遍历map：for (auto i = m.begin(); i != m.end(); i++)或者for (map<string,int>::iterator i = m.begin(); i != m.end(); i++);查找：m.find(string),若其等于m.end()，则未找到，否则找到了。此外，map中两个关键字分别是i->first，i->second，其中第二个关键字用数组方式取出也可以。需要特别注意的是，`在容器m里，string对应的int的初值为0！`

## 致谢

最后要特别感谢[柳诺姐姐的博客](https://www.liuchuo.net/ "悬停显示")提供的部分代码思路
