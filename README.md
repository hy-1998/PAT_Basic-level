# PAT_Basic-level
1001 水题 简单模拟 偶数每次除2，奇数每次乘3加1再除2 注意每次处理完后重新判断是奇数还是偶数

1002 水题 简单大数运算 先用字符串数组存储好每一位对应的拼音，对每一位求和后再拆开数字，对着拼音数组输出

1004 水题 首先定义结构体存储学生信息，再对学生成绩进行排序，自己写了个冒泡，但其实用vector存结构体再用容器本身的sort排序更省时间

1005 简单题 首先定义结构体存储每个数字的信息（主要包括数字本身以及它能覆盖的数），然后写一个函数，寻找数字a所能覆盖的数，存到数组n里，对于每一个数字的覆盖数组n，都将它与给出的这列数字比较，判断是否为关键数（这里用了三重循环，不过处理的数据量比较小，暴力还是能过）

1006 水题 分解每一位数字，根据题意循环输出即可

1007 水题 从2到给的数字区间找素数，然后判断相邻两个的差是否为2，计数即可

1008 水题 因为不让再用数组，所以把原来的数组开大一点，存两次数据。循环右移m其实就是小标加m再取模的过程

1009 水题 这道题的关键是要找到句子中空格的位置（包括句首以及句尾的空格），然后从倒数第二个空格开始，连续输出它与下一个空格间的内容

1010 水题 这里我用的do-while语句输入（一个小技巧，当输入不给数据量的时候，可以用如下输入方式）

do{

cin>>a;

count++;//计数

while(cin.get()!='\n');

然后分两种情况，即存在常数项和不存在，存在常数项又得区分是否为零多项式，因为零多项式是需要输出的，而非零多项式的常数项不输出

1011 水题 这个数据范围用longlong定义再加一下就好

1012 水题 第一类数是10的倍数，第二类判断一下-1的次方再进行混合运算，第三类计个数，第四类求个和，第五类可以先用一个数组单独存起来再sort一下

1013 简单题 这道题它最多就是第10000个素数，所以先把前10000个素数找到存在数组，然后输出的时候就从这个数组遍历，注意一下输出的格式

1014 简单题 这道题有点坑，首先第一对相同的大写英文字符必须要在A到G之间，然后第二对相同的字符可以是0到9之间的数字，也可以是A到N之间的大写字符，最后一对相同的字符排除掉&，输出注意补0

1015 中档题 这道题的数据量很大，所以很容易出现超时或者数组越界的情况。我的做法是，首先用vector进行数存储，然后用容器自带的sort函数来节省时间，这里需要自己定义一个比较函数cmp，最后说明一下scanf与printf是要比cin和cout快的。至于题目本身的逻辑很简单，分四类比较就好

1016 水题，找出A中Da以及B中Db的位数即可，A、B数据量大用string存

1017 中档题 简单的除法模拟 除数很大，用string存。然后从高位开始算，如果第j位大于被除数，直接除即可，然后余数再赋值给第j位；如果小于，则需要从第j+1位借位运算，余数赋值给第j+1位，特别注意只有此时才执行j++。这个循环因为有j+1，所以实际上做到了倒数第二位。对于除数是1位的，一定要单独考虑。

1018 水题 定义结构体存每一回合数据，vector存结构体。每一回合根据规则判断胜负，甲胜的次数就是乙输的次数。记录甲乙每种手势胜的次数，然后找到最大的对应的下标，输出手势字符。

1021 水题 字符串输入，每位数计数即可

1022 水题 进制转换，注意倒序以及和为0的情况

1023 水题 将第一个不为0的数作为首位，其余位从小到大输出即可

1024 简单题 这道题其实逻辑很简单，但是坑有点多。首先分类，看它的指数是大于0还是小于0。小于0的话就前面补0，大于0的话就后面加0。但有一种情况特殊，就是E的次方数小于小数部分的位数，此时小数点仍然右移，但后面不会添0（测试点4过不了就是因为这个）。还有一种情况是指数为0的情况，也必须单独考虑（但测试点里好像没有这个坑，不写也能过）

1025 难题 这道题可以说是乙级里最难的了，我写的第五个测试点超时了过不了，实在是脑壳疼所以就不想再改了，哪天想起来再说吧。先说一下思路：就是你得先把整个链表捋顺了，从头结点到尾节点，然后开始每k个进行反转，最后k个不反转。数据用vector型的结构体来存，因为这道题数据量比较大。注意输入的数据存在不在链表上的节点，所以要将链表上的节点存在新的vector里，之后再对这个vector进行操作。在捋链表的时候记录下每个节点在链表中的实际位置（下标），然后利用重构sort函数的排序实现反转，同时注意修改每个节点的指针域。同时如果不存在不足k个的节点，最后一个节点指针域要手动修改成-1；存在就不需要。最后就是注意下地址和指针用string存，不然输出麻烦。

1026 水题 秒数转换成小时、分钟与秒，注意一下数据用double还是int定义，再就是四舍五入的小技巧 int (a+0.5)

1027 水题 首先分析下给出的n个字符能用到多少个以及能输出多少行，可以推表达式，我图简单就用循环来判断了。然后先从上向下打印到输出3个字符的那一行，再向下打印，每行的字符数和空格数推一下就好

1028 水题 这道题逻辑很简单，对于每一个输入的数据判断一下是否在给定的时间范围内，用vector存了以后排个序即可。但是这题有两个坑点，一个是数据量比较大，用cin和cout会超时，所以要用scanf与printf；再就是要考虑所有数据都无效的情况，单独输出

1031 水题 用字符串存每一个身份证号，然后对前17位加权求和再取模，判断校验位是否正确

1032 水题 先用一个数组存下每个学校的总分，再在这个总分数组中顺序遍历找到最大值即可

1036 水题 注意为奇数时行数需要四舍五入，即int(a+0.5),然后就是分别处理第一行、中间行以及最后一行

1037 水题 先将钱都转换成以纳特为单位再相减，注意一下谁大谁小，最后再转化一次

1038 水题 这道题就是桶排序的思想，对于每个分数都统计下有多少个人再存在数组里，最后从数组里输出即可

1039 水题 对于摊主的珠串和小红的珠串，都顺序遍历一遍，统计下他们都有哪些珠子以及有多少个，然后对于小红想要的珠子，查询摊主的那个珠子有多少个，如果小于等于小红的，就做差（不能直接做差，因为摊主可能有多余的珠子），最后如果差的和为0，就说明可以买；否则就不可以，而且差的和就是差的总珠子数

1041 水题 这道题很简单，首先用一个结构体数组存储所有的数据，再根据给出的试机座位进行遍历求出考试座位与准考证号即可

1042 水题 首先对于有空格的字符串的输入，要用getline，然后遍历每一个字符，对其中的英文字符计数，最后输出出现次数最多的字符与次数即可

1043 水题 这道题考察的就是一个简单循环分支的判断，首先得到P,A,T,e,s,t各有多少个，然后再顺序输出，每输出一次其个数减一，如果个数等于0了就不用再输出了

1045 简单题 这道题考察了一些简单的算法，显然如果你想对每个数据都遍历它左边的所有数是否都比它小，右边的所有数是否都比它大是会超时的。其实我们可以这样想：既然要比左边的所有数都要大那就等价于大于左边数的最大值，比右边所有数都小那就是要小于右边所有数的最小值。那么我们可以从左往右遍历一遍，找到每一位数它前面数的最大值；再从右往左遍历一遍，找到每一位数它后面数的最小值。需要注意的是第一个数的左边数的最大值可以认为是0，最后一个数的右边数的最小值可以认为是无穷大。最后这道题有一个坑点就是主元数为0时，需要再输出一个换行

1046 水题 对于每一行的数据，都判断一下甲和乙喊的数字之和是否等于甲或者乙划的数字，注意一下不可以有同赢的情况

1047 水题 这道题就是对于每个输入，累加一下该队伍的总成绩，然后找到成绩最高的。但是我想强调一下输入的问题，我一开始用的cin输入，因为前两个队号队员编号连在一起了，只能用一个string变量来存再转成int型这样就很麻烦，后来看到别人用的scanf输入发现超级简单，所以很多时候对于特定格式的输入可以优先考虑scanf

1048 简单题 这道题逻辑不难，就是对奇数位和偶数位分别做不同的操作，但是做的时候却发现了自己对串的基本操作极其不熟练，后来参考了柳姐姐的代码，发现她的代码真的写的既简洁又漂亮，自己也写了一份。首先一定要考虑到当两个字符串长度不等时需要补足0，这里可以用类函数append，然后因为个位是第一位，为了简单我们可以将整个字符串反转一下，用swap函数。在操作的时候，因为数组下标是从0开始的，所以实际上对奇数和偶数的操作的相反的。最后如果想往字符串c里加字符，是可以直接用c+=的，这我还是第一次知道。。

1049 水题 这道题其实没什么好说的，关键就是找规律，我们发现第i个数（i从0开始）出现的次数是(i+1)*(n-i)，最后乘起来求和就好

1051 水题 这道题稍微推导下就能求得A和B的表达式，但在输出的时候会比较坑。比如当数字在-0.005与0之间时，用%.2f输出的是-0.00而不是0.00，对这部分数据要特别处理一下

1053 水题 这道题很简单，就是每一组数据遍历一遍，看看有多少天的用电量少于阈值，唯一需要注意的就是没有既是可能闲置又是闲置的情况

1055 简单题 这道题逻辑不难，首先理解一下什么叫字典序，比如Amy和Tim同样高，则认为Amy更高。实际上我们可以直接比较它们名字的字符串，更小的就更高。首先把所有人的身高从高到低排序，先处理最后一排，计算最后一排有多少人，再把最高的人放到中间，之后的人按照先左后右的顺序排，这里可以用奇偶来判断处理。对于非最后一排的，因为它们每一排的人数都确定了，就直接先找到中间的位置，再按照先左后右的规则排就好

1056 水题 因为是求所有组合出来的两位数的和，我们就简单判断一下每个数字出现在十位与个位的次数都是n-1，之后累加求和就好

1057 水题 遍历每一个字符，如果是英文字母，就累加一下求序号和，最后十进制转二进制数一下有多少个0和1，唯一需要注意的是输入用getline，因为它给的字符串是有空格的

1058 简单题 这道题感觉更多的是在考察输入与输出，对每道题选项的存储最好用字符串，这样的话比较起来简单。遍历每个学生的每道题，对了就加分，错了记录的次数就加1

1059 简单题 对于所有得奖的队伍，可以分成三种：冠军获得神秘大奖，排名素数的队伍得到小黄人（可以先把10000以内的素数找出来，而不是输入名次的时候再判断），其它队伍得到巧克力。同时我们需要两个标志位，一个表示所查的ID是否在排名里，一个是该队伍是否已经领过奖了，最后需要注意一下输出队号要是4位的，printf可以直接用%04d

1061 水题 对于每个学生的答案，都和标准答案比较一下，如果正确就加上该题的分值

1063 水题 对于每一组数据，求一下两个数平方和再开方的值，找最大的即可

1064 水题 对于每一个输入计算一下它的各位数字之和i，然后计数数组count[i]++，最后输出count非0的数，如果要记录有多少个不同的朋友证号的话，仅在count从0变到1的时候计数

1066 水题 对于每一组数据，判断一下输入是否在给定区间内，是的话就用特定值替换一下，最后输出注意要是三位


