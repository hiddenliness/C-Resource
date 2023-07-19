# C++课程安排



* 明确C++课程学习阶段以及课程内容



| 阶段     | 内容            | 目标                                   | 案例           |
| -------- | --------------- | -------------------------------------- | -------------- |
| 第一阶段 | C++基础语法入门 | 对C++有初步了解，能够有基础编程能力    | 通讯录管理系统 |
| 第二阶段 | C++核心编程     | 介绍C++面向对象编程，为大型项目做铺垫  | 职工管理系统   |
| 第三阶段 | C++提高编程     | 介绍C++泛型编程思想，以及STL的基本使用 | 演讲比赛系统   |

* 综合大案例：机房预约系统



================================================================================
C++基礎入門
1 C++初識
1.1 第一個C++程序
編寫一個C++程序總共分為4個步驟
創建項目
創建文件
編寫代碼
運行程序
1.1.1 創建項目
​ Visual Studio是我們用來編寫C++程序的主要工具，我們先將它打開


1.1.2 創建文件
右鍵源文件，選擇添加->新建項

給C++文件起個名稱，然後點擊添加即可。

1.1.3 編寫代碼
# include < iostream >
 using namespace std ;


int main () {


	cout << " Hello world " << endl;


	system ( " pause " );


	return 0 ;
}
1.1.4 運行程序

1.2 註釋
作用：在代碼中加一些說明和解釋，方便自己或其他程序員程序員閱讀代碼
兩種格式
單行註釋：// 描述信息
通常放在一行代碼的上方，或者一條語句的末尾，==對該行代碼說明==
多行註釋：/* 描述信息 */
通常放在一段代碼的上方，==對該段代碼做整體說明==
提示：編譯器在編譯代碼時，會忽略註釋的內容
1.3 變量
作用：給一段指定的內存空間起名，方便操作這段內存
語法：数据类型 变量名 = 初始值;
示例：
# include < iostream >
 using namespace std ;


int main () {


	//變量的定義
	//語法：數據類型變量名=初始值


	int a = 10 ;


	cout << " a = " << a << endl;
	
	system ( " pause " );


	return 0 ;
}
注意：C++在創建變量時，必須給變量一個初始值，否則會報錯
1.4 常量
作用：用於記錄程序中不可更改的數據
C++定義常量兩種方式
#define宏常量：#define 常量名 常量值
==通常在文件上方定義==，表示一個常量
const修飾的變量const 数据类型 常量名 = 常量值
==通常在變量定義前加關鍵字const==，修飾該變量為常量，不可修改
示例：
// 1、宏常量
# define day 7


int main () {


	cout << "一周裡總共有" << day << "天" << endl;
	 // day = 8; //報錯，宏常量不可以修改


	// 2、const修飾變量
	const int month = 12 ;
	cout << "一年裡總共有" << month << "個月份" << endl;
	 // month = 24; //報錯，常量是不可以修改的
	
	
	system ( " pause " );


	return 0 ;
}
1.5 關鍵字
**作用：**關鍵字是C++中預先保留的單詞（標識符）
在定義變量或者常量時候，不要用關鍵字
C++關鍵字如下：
asm
do
if
return
typedef
auto
double
inline
short
typeid
bool
dynamic_cast
int
signed
typename
break
else
long
sizeof
union
case
enum
mutable
static
unsigned
catch
explicit
namespace
static_cast
using
char
export
new
struct
virtual
class
extern
operator
switch
void
const
false
private
template
volatile
const_cast
float
protected
this
wchar_t
continue
for
public
throw
while
default
friend
register
true


delete
goto
reinterpret_cast
try



提示：在给变量或者常量起名称时候，不要用C++得关键字，否则会产生歧义。
1.6 標識符命名規則
作用：C++規定給標識符（變量、常量）命名時，有一套自己的規則
標識符不能是關鍵字
標識符只能由字母、數字、下劃線組成
第一個字符必須為字母或下劃線
標識符中字母區分大小寫
建議：給標識符命名時，爭取做到見名知意的效果，方便自己和他人的閱讀
2 數據類型
C++規定在創建一個變量或者常量時，必須要指定出相應的數據類型，否則無法給變量分配內存
2.1 整型
作用：整型變量表示的是==整數類型==的數據
C++中能夠表示整型的類型有以下幾種方式，區別在於所佔內存空間不同：
數據類型
佔用空間
取值範圍
short(短整型)
2字節
(-2^15 ~ 2^15-1)
int(整型)
4字節
(-2^31 ~ 2^31-1)
long(長整形)
Windows為4字節，Linux為4字節(32位)，8字節(64位)
(-2^31 ~ 2^31-1)
long long(長長整形)
8字節
(-2^63 ~ 2^63-1)

2.2 sizeof關鍵字
**作用：**利用sizeof關鍵字可以==統計數據類型所佔內存大小==
語法： sizeof( 数据类型 / 变量)
示例：
int main () {


	cout << " short類型所佔內存空間為：" << sizeof ( short ) << endl;


	cout << " int類型所佔內存空間為：" << sizeof ( int ) << endl;


	cout << " long類型所佔內存空間為：" << sizeof ( long ) << endl;


	cout << " long long類型所佔內存空間為：" << sizeof ( long long ) << endl;


	system ( " pause " );


	return 0 ;
}
整型結論：==short < int <= long <= long long==
short類型所佔內存空間為：2
 int類型所佔內存空間為：4
 long類型所佔內存空間為：8
 long long類型所佔內存空間為：8
2.3 實型（浮點型）
作用：用於==表示小數==
浮點型變量分為兩種：
單精度float
雙精度double
兩者的區別在於表示的有效數字範圍不同。
數據類型
佔用空間
有效數字範圍
float
4字節
7位有效數字
double
8字節
15～16位有效數字

示例：
int main () {


	float f1 = 3 . 14f ;
	 double d1 = 3.14 ;


	cout << f1 << endl;
	cout << d1<< endl;


	cout << " float sizeof = " << sizeof (f1) << endl;
	cout << " double sizeof = " << sizeof (d1) << endl;


	//科學計數法
	float f2 = 3e2 ; // 3 * 10 ^ 2 
	cout << " f2 = " << f2 << endl;


	float f3 = 3e-2 ;   // 3 * 0.1 ^ 2 
	cout << " f3 = " << f3 << endl;


	system ( " pause " );


	return 0 ;
}

3.14
3.14
 float sizeof = 4
 double sizeof = 8
 f2 = 300
 f3 = 0.03
Press any key to continue . . .

2.4 字符型
**作用：**字符型變量用於顯示單個字符
語法：char ch = 'a';
注意1：在顯示字符型變量時，用單引號將字符括起來，不要用雙引號
注意2：單引號內只能有一個字符，不可以是字符串
C和C++中字符型變量只佔用==1個字節==。
字符型變量並不是把字符本身放到內存中存儲，而是將對應的ASCII編碼放入到存儲單元
示例：
int main () {
	
	char ch = ' a ' ;
	cout << ch << endl;
	cout << sizeof ( char ) << endl;


	// ch = "abcde"; //錯誤，不可以用雙引號
	// ch = 'abcde'; //錯誤，單引號內只能引用一個字符


	cout << ( int )ch << endl;   //查看字符a對應的ASCII碼
	ch = 97 ; //可以直接用ASCII給字符型變量賦值
	cout << ch << endl;


	system ( " pause " );


	return 0 ;
}

1
32
a
Press any key to continue . . .

ASCII碼表格：
ASCII值
控製字符
ASCII值
字符
ASCII值
字符
ASCII值
字符
0
NUT
32
(space)
64
@
96
、
1
SOH
33
!
65
A
97
a
2
STX
34
"
66
B
98
b
3
ETX
35
#
67
C
99
c
4
EOT
36
$
68
D
100
d
5
ENQ
37
%
69
E
101
e
6
ACK
38
&
70
F
102
f
7
BEL
39
,
71
G
103
g
8
BS
40
(
72
H
104
h
9
HT
41
)
73
I
105
i
10
LF
42
*
74
J
106
j
11
VT
43
+
75
K
107
k
12
FF
44
,
76
L
108
l
13
CR
45
-
77
M
109
m
14
SO
46
.
78
N
110
n
15
SI
47
/
79
O
111
o
16
DLE
48
0
80
P
112
p
17
DCI
49
1
81
Q
113
q
18
DC2
50
2
82
R
114
r
19
DC3
51
3
83
S
115
s
20
DC4
52
4
84
T
116
t
21
NAK
53
5
85
U
117
u
22
SYN
54
6
86
V
118
v
23
TB
55
7
87
W
119
w
24
CAN
56
8
88
X
120
x
25
EM
57
9
89
Y
121
y
26
SUB
58
:
90
Z
122
z
27
ESC
59
;
91
[
123
{
28
FS
60
<
92
/
124
|
29
GS
61
=
93
]
125
}
30
RS
62
>
94
^
126
`
31
US
63
?
95
_
127
DEL

ASCII碼大致由以下兩部分組成：
ASCII非打印控製字符： ASCII表上的數字0-31分配給了控製字符，用於控制像打印機等一些外圍設備。
ASCII打印字符：數字32-126分配給了能在鍵盤上找到的字符，當查看或打印文檔時就會出現。
2.5 轉義字符
**作用：**用於表示一些==不能顯示出來的ASCII字符==
現階段我們常用的轉義字符有： \n \\ \t
轉義字符
含義
ASCII碼值（十進制）
\a
警報
007
\b
退格(BS) ，將當前位置移到前一列
008
\f
換頁(FF)，將當前位置移到下頁開頭
012
\n
換行(LF) ，將當前位置移到下一行開頭
010
\r
回車(CR) ，將當前位置移到本行開頭
013
\t
水平製表(HT) （跳到下一個TAB位置）
009
\v
垂直製表(VT)
011
\\
代表一個反斜線字符""
092
'
代表一個單引號（撇號）字符
039
"
代表一個雙引號字符
034
?
代表一個問號
063
\0
數字0
000
\ddd
8進制轉義字符，d範圍0~7
3位8進制
\xhh
16進制轉義字符，h範圍09，af，A~F
3位16進制

示例：
int main () {
	
	
	cout << " \\ " << endl;
	cout << " \t Hello " << endl;
	cout << " \n " << endl;


	system ( " pause " );


	return 0 ;
}
2.6 字符串型
作用：用於表示一串字符
兩種風格
C風格字符串：char 变量名[] = "字符串值"
示例：
int main () {


	char str1[] = " hello world " ;
	cout << str1 << endl;
    
	system ( " pause " );


	return 0 ;
}
注意：C風格的字符串要用雙引號括起來
C++風格字符串： string 变量名 = "字符串值"
示例：
int main () {


	string str = " hello world " ;
	cout << str << endl;
	
	system ( " pause " );


	return 0 ;
}
​
注意：C++風格字符串，需要加入頭文件==#include<string>==
2.7 布爾類型bool
**作用：**布爾數據類型代表真或假的值
bool類型只有兩個值：
true --- 真（本質是1）
false --- 假（本質是0）
bool類型占==1個字節==大小
示例：
int main () {


	bool flag = true ;
	cout << flag << endl; // 1


	flag = false ;
	cout << flag << endl; // 0


	cout << " size of bool = " << sizeof ( bool ) << endl; // 1 bytes
	
	system ( " pause " );


	return 0 ;
}
2.8 數據的輸入
作用：用於從鍵盤獲取數據
**關鍵字：**cin
語法： cin >> 变量
示例：
int main (){


	//整型輸入
	int a = 0 ;
	cout << "請輸入整型變量：" << endl;
	cin >> a;
	cout << a << endl;


	//浮點型輸入
	double d = 0 ;
	cout << "請輸入浮點型變量：" << endl;
	cin >> d;
	cout << d << endl;


	//字符型輸入
	char ch = 0 ;
	cout << "請輸入字符型變量：" << endl;
	cin >> ch;
	cout << ch << endl;


	//字符串型輸入
	string str;
	cout << "請輸入字符串型變量：" << endl;
	cin >> str;
	cout << str << endl;


	//布爾類型輸入
	bool flag = true ;
	cout << "請輸入布爾型變量：" << endl;
	cin >> flag;
	cout << flag << endl;
	system ( " pause " );
	 return EXIT_SUCCESS;
}
3 運算符
**作用：**用於執行代碼的運算
本章我們主要講解以下幾類運算符：
運算符類型
作用
算術運算符
用於處理四則運算
賦值運算符
用於將表達式的值賦給變量
比較運算符
用於表達式的比較，並返回一個真值或假值
邏輯運算符
用於根據表達式的值返回真值或假值

3.1 算術運算符
作用：用於處理四則運算
算術運算符包括以下符號：
運算符
術語
示例
結果
+
正號
+3
3
-
負號
-3
-3
+
加
10 + 5
15
-
減
10 - 5
5
*
乘
10 * 5
50
/
除
10 / 5
2
%
取模(取餘)
10 % 3
1
++
前置遞增
a=2; b=++a;
a=3; b=3;
++
後置遞增
a=2; b=a++;
a=3; b=2;
--
前置遞減
a=2; b=--a;
a=1; b=1;
--
後置遞減
a=2; b=a--;
a=1; b=2;

示例1：
//加減乘除
int main () {


	int a1 = 10 ;
	 int b1 = 3 ;


	cout << a1 + b1 << endl;
	cout << a1 - b1 << endl;
	cout << a1 * b1 << endl;
	cout << a1 / b1 << endl;   //兩個整數相除結果依然是整數


	int a2 = 10 ;
	 int b2 = 20 ;
	cout << a2 / b2 << endl; 


	int a3 = 10 ;
	 int b3 = 0 ;
	 // cout << a3 / b3 << endl; //報錯，除數不可以為0




	//兩個小數可以相除
	double d1 = 0.5 ;
	 double d2 = 0.25 ;
	cout << d1 / d2 << endl;


	system ( " pause " );


	return 0 ;
}
總結：在除法運算中，除數不能為0
示例2：
//取模
int main () {


	int a1 = 10 ;
	 int b1 = 3 ;


	cout << 10 % 3 << endl;


	int a2 = 10 ;
	 int b2 = 20 ;


	cout << a2 % b2 << endl;


	int a3 = 10 ;
	 int b3 = 0 ;


	// cout << a3 % b3 << endl; //取模運算時，除數也不能為0


	//兩個小數不可以取模
	double d1 = 3.14 ;
	 double d2 = 1.1 ;


	// cout << d1 % d2 << endl;


	system ( " pause " );


	return 0 ;
}


總結：只有整型變量可以進行取模運算
示例3：
//遞增
int main () {


	//後置遞增
	int a = 10 ;
	a++; //等價於a = a + 1 
	cout << a << endl; // 11


	//前置遞增
	int b = 10 ;
	++b;
	cout << b << endl; // 11


	//區別
	//前置遞增先對變量進行++，再計算表達式
	int a2 = 10 ;
	 int b2 = ++a2 * 10 ;
	cout << b2 << endl;


	//後置遞增先計算表達式，後對變量進行++ 
	int a3 = 10 ;
	 int b3 = a3++ * 10 ;
	cout << b3 << endl;


	system ( " pause " );


	return 0 ;
}


總結：前置遞增先對變量進行++，再計算表達式，後置遞增相反
3.2 賦值運算符
**作用：**用於將表達式的值賦給變量
賦值運算符包括以下幾個符號：
運算符
術語
示例
結果
=
賦值
a=2; b=3;
a=2; b=3;
+=
加等於
a=0; a+=2;
a=2;
-=
減等於
a=5; a-=3;
a=2;
*=
乘等於
a=2; a*=2;
a=4;
/=
除等於
a=4; a/=2;
a=2;
%=
模等於
a=3; a%2;
a=1;

示例：
int main () {


	//賦值運算符


	// = 
	int a = 10 ;
	a = 100 ;
	cout << " a = " << a << endl;


	// += 
	a = 10 ;
	a += 2 ; // a = a + 2; 
	cout << " a = " << a << endl;


	// -= 
	a = 10 ;
	a -= 2 ; // a = a - 2 
	cout << " a = " << a << endl;


	// *= 
	a = 10 ;
	a *= 2 ; // a = a * 2 
	cout << " a = " << a << endl;


	// /= 
	a = 10 ;
	a /= 2 ;   // a = a / 2; 
	cout << " a = " << a << endl;


	// %= 
	a = 10 ;
	a %= 2 ;   // a = a % 2; 
	cout << " a = " << a << endl;


	system ( " pause " );


	return 0 ;
}
3.3 比較運算符
**作用：**用於表達式的比較，並返回一個真值或假值
比較運算符有以下符號：
運算符
術語
示例
結果
==
相等於
4 == 3
0
!=
不等於
4 != 3
1
<
小於
4 < 3
0
>
大於
4 > 3
1
<=
小於等於
4 <= 3
0
>=
大於等於
4 >= 1
1

示例：
int main () {


	int a = 10 ;
	 int b = 20 ;


	cout << (a == b) << endl; // 0


	cout << (a != b) << endl; // 1


	cout << (a > b) << endl; // 0


	cout << (a < b) << endl; // 1


	cout << (a >= b) << endl; // 0


	cout << (a <= b) << endl; // 1
	
	system ( " pause " );


	return 0 ;
}
注意：C和C++ 語言的比較運算中， ==“真”用數字“1”來表示， “假”用數字“0”來表示。==
3.4 邏輯運算符
**作用：**用於根據表達式的值返回真值或假值
邏輯運算符有以下符號：
運算符
術語
示例
結果
!
非
!a
如果a為假，則!a為真； 如果a為真，則!a為假。
&&
與
a && b
如果a和b都為真，則結果為真，否則為假。
||
或
a || b
如果a和b有一個為真，則結果為真，二者都為假時，結果為假。

**示例1：**邏輯非
//邏輯運算符---非
int main () {


	int a = 10 ;


	cout << !a << endl; // 0


	cout << !!a << endl; // 1


	system ( " pause " );


	return 0 ;
}
總結： 真變假，假變真
**示例2：**邏輯與
//邏輯運算符---與
int main () {


	int a = 10 ;
	 int b = 10 ;


	cout << (a && b) << endl; // 1


	a = 10 ;
	b = 0 ;


	cout << (a && b) << endl; // 0


	a = 0 ;
	b = 0 ;


	cout << (a && b) << endl; // 0


	system ( " pause " );


	return 0 ;
}


總結：邏輯==與==運算符總結： ==同真為真，其餘為假==
**示例3：**邏輯或
//邏輯運算符---或
int main () {


	int a = 10 ;
	 int b = 10 ;


	cout << (a || b) << endl; // 1


	a = 10 ;
	b = 0 ;


	cout << (a || b) << endl; // 1


	a = 0 ;
	b = 0 ;


	cout << (a || b) << endl; // 0


	system ( " pause " );


	return 0 ;
}
邏輯==或==運算符總結： ==同假為假，其餘為真==
4 程序流程結構
C/C++支持最基本的三種程序運行結構：==順序結構、選擇結構、循環結構==
順序結構：程序按順序執行，不發生跳轉
選擇結構：依據條件是否滿足，有選擇的執行相應功能
循環結構：依據條件是否滿足，循環多次執行某段代碼
4.1 選擇結構
4.1.1 if語句
**作用：**執行滿足條件的語句
if語句的三種形式
單行格式if語句
多行格式if語句
多條件的if語句
​
單行格式if語句：if(条件){ 条件满足执行的语句 }

示例：
int main () {


	//選擇結構-單行if語句
	//輸入一個分數，如果分數大於600分，視為考上一本大學，並在屏幕上打印


	int score = 0 ;
	cout << "請輸入一個分數：" << endl;
	cin >> score;


	cout << "您輸入的分數為：" << score << endl;


	// if語句
	//注意事項，在if判斷語句後面，不要加分號
	if (score > 600 )
	{
		cout << "我考上了一本大學！！！" << endl;
	}


	system ( " pause " );


	return 0 ;
}
​
注意：if條件表達式後不要加分號
多行格式if語句：if(条件){ 条件满足执行的语句 }else{ 条件不满足执行的语句 };

​
示例：
int main () {


	int score = 0 ;


	cout << "請輸入考試分數：" << endl;


	cin >> score;


	if (score > 600 )
	{
		cout << "我考上了一本大學" << endl;
	}
	else
	{
		cout << "我未考上一本大學" << endl;
	}


	system ( " pause " );


	return 0 ;
}
多條件的if語句：if(条件1){ 条件1满足执行的语句 }else if(条件2){条件2满足执行的语句}... else{ 都不满足执行的语句}

​
​
​
示例：
	int main () {


	int score = 0 ;


	cout << "請輸入考試分數：" << endl;


	cin >> score;


	if (score > 600 )
	{
		cout << "我考上了一本大學" << endl;
	}
	else if (score > 500 )
	{
		cout << "我考上了二本大學" << endl;
	}
	else if (score > 400 )
	{
		cout << "我考上了三本大學" << endl;
	}
	else
	{
		cout << "我未考上本科" << endl;
	}


	system ( " pause " );


	return 0 ;
}
​
嵌套if語句：在if語句中，可以嵌套使用if語句，達到更精確的條件判斷
案例需求：
提示用戶輸入一個高考考試分數，根據分數做如下判斷
分數如果大於600分視為考上一本，大於500分考上二本，大於400考上三本，其餘視為未考上本科；
在一本分數中，如果大於700分，考入北大，大於650分，考入清華，大於600考入人大。
示例：
int main () {


	int score = 0 ;


	cout << "請輸入考試分數：" << endl;


	cin >> score;


	if (score > 600 )
	{
		cout << "我考上了一本大學" << endl;
		 if (score > 700 )
		{
			cout << "我考上了北大" << endl;
		}
		else if (score > 650 )
		{
			cout << "我考上了清華" << endl;
		}
		else
		{
			cout << "我考上了人大" << endl;
		}
		
	}
	else if (score > 500 )
	{
		cout << "我考上了二本大學" << endl;
	}
	else if (score > 400 )
	{
		cout << "我考上了三本大學" << endl;
	}
	else
	{
		cout << "我未考上本科" << endl;
	}


	system ( " pause " );


	return 0 ;
}
練習案例：三隻小豬稱體重
有三隻小豬ABC，請分別輸入三隻小豬的體重，並且判斷哪隻小豬最重？
#include<iostream>
using namespace std;
int main()
{
	float a = 0;//三隻小豬分別是 a、b、c
	float b = 0;
	float c = 0;
 
	cout << "請分別輸入三隻小豬的體重" << endl;
	cout << "請輸入第一隻小豬a的體重 ：" << endl;
	cin >> a;
	cout << "請輸入第二隻小豬b的體重 ：" << endl;
	cin >> b;
	cout << "請輸入第三隻小豬c的體重 ：" << endl;
	cin >> c;
	if ((a > b) && (a > c))//判斷a是否為最大
	{
		if (b > c)//判斷b和c的體重大小
		{
		cout << "a豬的體重最大，c豬的體重最小" << endl;
	}
		else
		{
			cout << "a豬的體重最大，b豬的體重最小" << endl;
		}
	}
	else if (b > c)//判斷b是否為最大
	{
		if (a > c)//判斷a和c的體重大小
		{
			cout << "b豬的體重最大，c豬的體重最小" << endl;
		}
		else
		{
			cout << "b豬的體重最大，a豬的體重最小" << endl;
		}
 
	}
	else//此時c最大
	{
		if (a > b)//判斷a和b的體重大小
		{
			cout << "c豬的體重最大，b豬的體重最小" << endl;
		}
		else
		{
			cout << "c豬的體重最大，a豬的體重最小" << endl;
		}
	}
	system("pause");
 	return 0;
}


4.1.2 三目運算符
作用：通過三目運算符實現簡單的判斷
語法：表达式1 ? 表达式2 ：表达式3
解釋：
如果表達式1的值為真，執行表達式2，並返回表達式2的結果；
如果表達式1的值為假，執行表達式3，並返回表達式3的結果。
示例：
int main () {


	int a = 10 ;
	 int b = 20 ;
	 int c = 0 ;


	c = a > b ? a : b;
	cout << " c = " << c << endl;


	// C++中三目運算符返回的是變量,可以繼續賦值


	(a > b ? a : b) = 100 ;


	cout << " a = " << a << endl;
	cout << " b = " << b << endl;
	cout << " c = " << c << endl;


	system ( " pause " );


	return 0 ;
}
總結：和if語句比較，三目運算符優點是短小整潔，缺點是如果用嵌套，結構不清晰
4.1.3 switch語句
**作用：**執行多條件分支語句
語法：
switch (表達式)


{


	case結果1：執行語句; break ;


	case結果2：執行語句; break ;


	...


	default :執行語句; break ;


}


示例：
int main () {


	//請給電影評分
	// 10 ~ 9經典   
	// 8 ~ 7非常好
	// 6 ~ 5一般
	// 5分以下爛片


	int score = 0 ;
	cout << "請給電影打分" << endl;
	cin >> score;


	switch (score)
	{
	case 10 :
	 case 9 :
		cout << "經典" << endl;
		 break ;
	 case 8 :
		cout << "非常好" << endl;
		 break ;
	 case 7 :
	 case 6 :
		cout << "一般" << endl;
		 break ;
	 default :
		cout << "爛片" << endl;
		 break ;
	}


	system ( " pause " );


	return 0 ;
}
注意1：switch語句中表達式類型只能是整型或者字符型
注意2：case裡如果沒有break，那麼程序會一直向下執行
總結：與if語句比，對於多條件判斷時，switch的結構清晰，執行效率高，缺點是switch不可以判斷區間
4.2 循環結構
4.2.1 while循環語句
**作用：**滿足循環條件，執行循環語句
語法： while(循环条件){ 循环语句 }
解釋： ==只要循環條件的結果為真，就執行循環語句==

示例：
int main () {


	int num = 0 ;
	 while (num < 10 )
	{
		cout << " num = " << num << endl;
		num++;
	}
	
	system ( " pause " );


	return 0 ;
}
注意：在執行循環語句時候，程序必須提供跳出循環的出口，否則出現死循環
while循環練習案例： ==猜數字==
**案例描述：**系統隨機生成一個1到100之間的數字，玩家進行猜測，如果猜錯，提示玩家數字過大或過小，如果猜對恭喜玩家勝利，並且退出遊戲。

#include <iostream>
using namespace std;
//time系統時間頭文件包含
#include <ctime>
int main() {
	//添加隨機數種子  利用當前系統時間生成隨機數，防止每次隨機數都一樣
	srand((unsigned int)time(NULL));
	//1.系統生成隨機數
	int num=rand()%100+1;  // rand()%100 生成0+1~99+1的隨機數
	cout<<num<<endl;
	
	//2.玩家進行猜測
	int val=0;
	while(1){
		cin>>val;
		//3.判斷玩家的猜測
		if(val>num){
			//猜錯  提示猜的結果 過大或者過小 重新返回第2步
			cout<<"猜測過大"<<endl;
		}else if(val<num){
			//猜錯  提示猜的結果 過大或者過小 重新返回第2步
			cout<<"猜測過小"<<endl;
		}else{
			//猜對  退出遊戲
			cout<<"恭喜您猜對啦"<<endl;
			break;
		}
	}	
	system("pause");
 
	return 0;
}


4.2.2 do...while循環語句
作用：滿足循環條件，執行循環語句
語法： do{ 循环语句 } while(循环条件);
**注意：**與while的區別在於==do...while會先執行一次循環語句==，再判斷循環條件

示例：
int main () {


	int num = 0 ;


	do
	{
		cout << num << endl;
		num++;


	} while (num < 10 );
	
	
	system ( " pause " );


	return 0 ;
}
總結：與while循環區別在於，do...while先執行一次循環語句，再判斷循環條件
練習案例：水仙花數
**案例描述：**水仙花數是指一個3 位數，它的每個位上的數字的3次冪之和等於它本身
例如：1^3 + 5^3+ 3^3 = 153
請利用do...while語句，求出所有3位數中的水仙花數
#include <iostream>
using namespace std;
int main() {
	int num = 100;
	int a = 0;
	int b = 0;
	int c = 0;
	do {
		a = num / 100;
		b = (num / 10) % 10;
		c = num % 10;
		if (num == a * a * a + b * b * b + c * c * c) {
			cout << num << endl;
		}
		num++;
	} while (num < 1000);
 }
4.2.3 for循環語句
作用：滿足循環條件，執行循環語句
語法： for(起始表达式;条件表达式;末尾循环体) { 循环语句; }
示例：
int main () {


	for ( int i = 0 ; i < 10 ; i++)
	{
		cout << i << endl;
	}
	
	system ( " pause " );


	return 0 ;
}
詳解：

注意：for循環中的表達式，要用分號進行分隔
總結：while , do...while, for都是開發中常用的循環語句，for循環結構比較清晰，比較常用
練習案例：敲桌子
案例描述：從1開始數到數字100， 如果數字個位含有7，或者數字十位含有7，或者該數字是7的倍數，我們打印敲桌子，其餘數字直接打印輸出。

#include <iostream>
using namespace std;
 
int main() {
	int num;
	for (num = 1; num<= 100; num++) {
		if (num < 10)
			if (num == 7 || num % 7 == 0)
				cout << "敲桌子" << endl;
			else
				cout << num << endl;
		else if (num < 100)
			if (num % 10 == 7 || num / 10 == 7 || num % 7 == 0)
				cout << "敲桌子" << endl;
			else
				cout << num << endl;
		else
			if (num % 10 == 7 || (num / 10) % 10 == 7 || num % 7 == 0)
				cout << "敲桌子" << endl;
			else
				cout << num << endl;
 
	}
	system("pause");
	return 0;
 
}


4.2.4 嵌套循環
作用：在循環體中再嵌套一層循環，解決一些實際問題
例如我們想在屏幕中打印如下圖片，就需要利用嵌套循環

示例：
int main () {


	//外層循環執行1次，內層循環執行1輪
	for ( int i = 0 ; i < 10 ; i++)
	{
		for ( int j = 0 ; j < 10 ; j++)
		{
			cout << " * " << " " ;
		}
		cout << endl;
	}
	system ( " pause " );


	return 0 ;
}
**練習案例：**乘法口訣表
案例描述：利用嵌套循環，實現九九乘法表



#include<iostream>
using namespace std;


int main() {
    
	//嵌套循環實現九九乘法表
	for (int i = 1; i < 10; i++) {


		for (int j = 1; j <= i; j++) {
       
			cout <<i<< " * "<<j<<" = "<<i * j<<" ";
		}
		cout << endl;//換行


	}


	system("pause");


	return 0;
}




4.3 跳轉語句
4.3.1 break語句
作用:用於跳出==選擇結構==或者==循環結構==
break使用的時機：
出現在switch條件語句中，作用是終止case並跳出switch
出現在循環語句中，作用是跳出當前的循環語句
出現在嵌套循環中，跳出最近的內層循環語句
示例1：
int main () {
	 // 1、在switch語句中使用break 
	cout << "請選擇您挑戰副本的難度：" << endl;
	cout << " 1、普通" << endl;
	cout << " 2、中等" << endl;
	cout << " 3、困難" << endl;


	int num = 0 ;


	cin >> num;


	switch (num)
	{
	case 1 :
		cout << "您選擇的是普通難度" << endl;
		 break ;
	 case 2 :
		cout << "您選擇的是中等難度" << endl;
		 break ;
	 case 3 :
		cout << "您選擇的是困難難度" << endl;
		 break ;
	}


	system ( " pause " );


	return 0 ;
}
示例2：
int main () {
	 // 2、在循環語句中用break 
	for ( int i = 0 ; i < 10 ; i++)
	{
		if (i == 5 )
		{
			break ; //跳出循環語句
		}
		cout << i << endl;
	}


	system ( " pause " );


	return 0 ;
}
示例3：
int main () {
	 //在嵌套循環語句中使用break，退出內層循環
	for ( int i = 0 ; i < 10 ; i++)
	{
		for ( int j = 0 ; j < 10 ; j++)
		{
			if (j == 5 )
			{
				break ;
			}
			cout << " * " << " " ;
		}
		cout << endl;
	}
	
	system ( " pause " );


	return 0 ;
}
4.3.2 continue語句
**作用：**在==循環語句==中，跳過本次循環中餘下尚未執行的語句，繼續執行下一次循環
示例：
int main () {


	for ( int i = 0 ; i < 100 ; i++)
	{
		if (i % 2 == 0 )
		{
			continue ;
		}
		cout << i << enl;
	}
	
	system ( " pause " );


	return 0 ;
}
注意：continue並沒有使整個循環終止，而break會跳出循環
4.3.3 goto語句
**作用：**可以無條件跳轉語句
語法： goto 标记;
**解釋：**如果標記的名稱存在，執行到goto語句時，會跳轉到標記的位置
示例：
int main () {


	cout << " 1 " << endl;


	goto FLAG;


	cout << " 2 " << endl;
	cout << " 3 " << endl;
	cout << " 4 " << endl;


	FLAG:


	cout << " 5 " << endl;
	
	system ( " pause " );


	return 0 ;
}
注意：在程序中不建議使用goto語句，以免造成程序流程混亂
5 數組
5.1 概述
所謂數組，就是一個集合，裡面存放了相同類型的數據元素
**特點1：**數組中的每個==數據元素都是相同的數據類型==
**特點2：**數組是由==連續的內存==位置組成的

5.2 一維數組
5.2.1 一維數組定義方式
一維數組定義的三種方式：
数据类型 数组名[ 数组长度 ];
数据类型 数组名[ 数组长度 ] = { 值1，值2 ...};
数据类型 数组名[ ] = { 值1，值2 ...};
示例
int main () {


	//定義方式1 
	//數據類型數組名[元素個數]; 
	int score[ 10 ];


	//利用下標賦值
	score[ 0 ] = 100 ;
	score[ 1 ] = 99 ;
	score[ 2 ] = 85 ;


	//利用下標輸出
	cout << score[ 0 ] << endl;
	cout << score[ 1 ] << endl;
	cout << score[ 2 ] << endl;




	//第二種定義方式
	//數據類型數組名[元素個數] = {值1，值2 ，值3 ...}; 
	//如果{}內不足10個數據，剩餘數據用0補全
	int score2[ 10 ] = { 100 , 90 , 80 , 70 , 60 , 50 , 40 , 30 , 20 , 10 };
	
	//逐個輸出
	// cout << score2[0] << endl; 
	// cout << score2[1] << endl;


	//一個一個輸出太麻煩，因此可以利用循環進行輸出
	for ( int i = 0 ; i < 10 ; i++)
	{
		cout << score2[i] << endl;
	}


	//定義方式3 
	//數據類型數組名[] = {值1，值2 ，值3 ...}; 
	int score3[] = { 100 , 90 , 80 , 70 , 60 , 50 , 40 , 30 , 20 , 10 };


	for ( int i = 0 ; i < 10 ; i++)
	{
		cout << score3[i] << endl;
	}


	system ( " pause " );


	return 0 ;
}
總結1：數組名的命名規範與變量名命名規範一致，不要和變量重名
總結2：數組中下標是從0開始索引
5.2.2 一維數組數組名
一維數組名稱的用途：
可以統計整個數組在內存中的長度
可以獲取數組在內存中的首地址
示例：
int main () {


	//數組名用途
	// 1、可以獲取整個數組佔用內存空間大小
	int arr[ 10 ] = { 1 , 2 , 3 , 4 , 5 , 6 , 7 , 8 , 9 , 10 };


	cout << "整個數組所佔內存空間為：" << sizeof (arr) << endl;
	cout << "每個元素所佔內存空間為：" << sizeof (arr[ 0 ]) << endl;
	cout << "數組的元素個數為：" << sizeof (arr) / sizeof (arr[ 0 ]) << endl;


	// 2、可以通過數組名獲取到數組首地址
	cout << "數組首地址為：" << ( int )arr << endl;
	cout << "數組中第一個元素地址為：" << ( int )&arr[ 0 ] << endl;
	cout << "數組中第二個元素地址為：" << ( int )&arr[ 1 ] << endl;


	// arr = 100;錯誤，數組名是常量，因此不可以賦值




	system ( " pause " );


	return 0 ;
}
注意：數組名是常量，不可以賦值
總結1：直接打印數組名，可以查看數組所佔內存的首地址
總結2：對數組名進行sizeof，可以獲取整個數組佔內存空間的大小


練習案例1：五隻小豬稱體重
案例描述：
在一個數組中記錄了五隻小豬的體重，如：int arr[5] = {300,350,200,400,250};
找出並打印最重的小豬體重。
#include <iostream>
using namespace std;
int main(){
	//1.創建5隻小豬體重的數組
	int arr[5]={300,350,200,400,250};
	//2.從數組中找到最大值
	int max=0;
	for(int i=0;i<5;i++){
		if(arr[i]>max){
			max=arr[i];
		}
	}
	//3.打印最大值
	cout<<"最重的小豬體重為："<<max<<endl;
 
	system("pause");
	return 0;
}




**練習案例2：**數組元素逆置
**案例描述：**請聲明一個5個元素的數組，並且將元素逆置.
(如原數組元素為：1,3,2,5,4;逆置後輸出結果為:4,5,2,3,1);
#include <iostream>
using namespace std;
int main(){
    //實現數組元素的逆置
    //1.創建數組
    int arr[5]={1,2,3,4,5};
    int len=sizeof(arr)/sizeof(arr[0]);
    cout<<"數組逆置前：";
    for(int i=0;i<len;i++){
        cout<<arr[i]<<"  ";
    }
    cout<<endl;
    //2.實現逆置
    //2.1記錄起始下標位置
    //2.2記錄結束下標位置
    //2.3起始下標與結束下標的元素互換
    //2.4 起始位置++  結束位置--
    //2.5循環執行2.1操作，直到起始位置》=結束位置
    int start=0;//起始下標
    int end=len-1;//結束下標
  //  while(start<end){
        //實現元素互換
    for(start=0;start<end;start++,end--)
    {
        int temp=arr[start];
        arr[start]=arr[end];
        arr[end]=temp;
        //下標更新
      //  start++;
     //   end--;
    }
    //打印逆置後的數組
    cout<<"數組逆置後：";
    for(int i=0;i<len;i++){
        cout<<arr[i]<<"  ";
    }
    cout<<endl;
    system("pause");
    return 0;
}




5.2.3 冒泡排序
作用：最常用的排序算法，對數組內元素進行排序
比較相鄰的元素。如果第一個比第二個大，就交換他們兩個。
對每一對相鄰元素做同樣的工作，執行完畢後，找到第一個最大值。
重複以上的步驟，每次比較次數-1，直到不需要比較

示例：將數組{ 4,2,8,0,5,7,1,3,9 }進行升序排序
int main () {


	int arr[ 9 ] = { 4 , 2 , 8 , 0 , 5 , 7 , 1 , 3 , 9 };


	for ( int i = 0 ; i < 9 - 1 ; i++)
	{
		for ( int j = 0 ; j < 9 - 1 - i; j++)
		{
			if (arr[j] > arr[j + 1 ])
			{
				int temp = arr[j];
				arr[j] = arr[j + 1 ];
				arr[j + 1 ] = temp;
			}
		}
	}


	for ( int i = 0 ; i < 9 ; i++)
	{
		cout << arr[i] << endl;
	}
    
	system ( " pause " );


	return 0 ;
}
5.3 二維數組
二維數組就是在一維數組上，多加一個維度。

5.3.1 二維數組定義方式
二維數組定義的四種方式：
数据类型 数组名[ 行数 ][ 列数 ];
数据类型 数组名[ 行数 ][ 列数 ] = { {数据1，数据2 } ，{数据3，数据4 } };
数据类型 数组名[ 行数 ][ 列数 ] = { 数据1，数据2，数据3，数据4};
数据类型 数组名[ ][ 列数 ] = { 数据1，数据2，数据3，数据4};
建議：以上4種定義方式，利用==第二種更加直觀，提高代碼的可讀性==
示例：
int main () {


	//方式1   
	//數組類型數組名[行數][列數] 
	int arr[ 2 ][ 3 ];
	arr[ 0 ][ 0 ] = 1 ;
	arr[ 0 ][ 1 ] = 2 ;
	arr[ 0 ][ 2 ] = 3 ;
	arr[ 1 ][ 0 ] = 4 ;
	arr[ 1 ][ 1 ] = 5 ;
	arr[ 1 ][ 2 ] = 6 ;


	for ( int i = 0 ; i < 2 ; i++)
	{
		for ( int j = 0 ; j < 3 ; j++)
		{
			cout << arr[i][j] << " " ;
		}
		cout << endl;
	}


	//方式2 
	//數據類型數組名[行數][列數] = { {數據1，數據2 } ，{數據3，數據4 } }; 
	int arr2[ 2 ][ 3 ] =
	{
		{ 1 , 2 , 3 },
		{ 4 , 5 , 6 }
	};


	//方式3 
	//數據類型數組名[行數][列數] = {數據1，數據2 ,數據3，數據4 }; 
	int arr3[ 2 ][ 3 ] = { 1 , 2 , 3 , 4 , 5 , 6 };


	//方式4 
	//數據類型數組名[][列數] = {數據1，數據2 ,數據3，數據4 }; 
	int arr4[][ 3 ] = { 1 , 2 , 3 , 4 , 5 , 6 };
	
	system ( " pause " );


	return 0 ;
}
總結：在定義二維數組時，如果初始化了數據，可以省略行數
5.3.2 二維數組數組名
查看二維數組所佔內存空間
獲取二維數組首地址
示例：
int main () {


	//二維數組數組名
	int arr[ 2 ][ 3 ] =
	{
		{ 1 , 2 , 3 },
		{ 4 , 5 , 6 }
	};


	cout << "二維數組大小：" << sizeof (arr) << endl;//24bytes
	cout << "二維數組一行大小：" << sizeof (arr[ 0 ]) << endl;//12bytes
	cout << "二維數組元素大小：" << sizeof (arr[ 0 ][ 0 ]) << endl;//4bytes


	cout << "二維數組行數：" << sizeof (arr) / sizeof (arr[ 0 ]) << endl;
	cout << "二維數組列數：" << sizeof (arr[ 0 ]) / sizeof (arr[ 0 ][ 0 ]) << endl;


	//地址
	cout << "二維數組首地址：" << arr << endl;
	cout << "二維數組第一行地址：" << arr[ 0 ] << endl;
	cout << "二維數組第二行地址：" << arr[ 1 ] << endl;


	cout << "二維數組第一個元素地址：" << &arr[ 0 ][ 0 ] << endl;
	cout << "二維數組第二個元素地址：" << &arr[ 0 ][ 1 ] << endl;


	system ( " pause " );


	return 0 ;
}
總結1：二維數組名就是這個數組的首地址
總結2：對二維數組名進行sizeof時，可以獲取整個二維數組佔用的內存空間大小
5.3.3 二維數組應用案例
考試成績統計：
案例描述：有三名同學（張三，李四，王五），在一次考試中的成績分別如下表，請分別輸出三名同學的總成績


語文
數學
英語
張三
100
100
100
李四
90
50
100
王五
60
70
80

參考答案：
int main () {


	int scores[ 3 ][ 3 ] =
	{
		{ 100 , 100 , 100 },
		{ 90 , 50 , 100 },
		{ 60 , 70 , 80 },
	};


	string names[ 3 ] = { "張三" , "李四" , "王五" };


	for ( int i = 0 ; i < 3 ; i++)
	{
		int sum = 0 ;
		 for ( int j = 0 ; j < 3 ; j++)
		{
			sum += scores[i][j];
		}
		cout << names[i] << "同學總成績為：" << sum << endl;
	}


	system ( " pause " );


	return 0 ;
}
6 函數
6.1 概述
**作用：**將一段經常使用的代碼封裝起來，減少重複代碼
一個較大的程序，一般分為若干個程序塊，每個模塊實現特定的功能。
6.2 函數的定義
函數的定義一般主要有5個步驟：
1、返回值類型
2、函數名
3、參數表列
4、函數體語句
5、return 表達式
語法：
返回值類型函數名（參數列表）
{


       函數體語句


       return表達式


}
返回值類型：一個函數可以返回一個值。在函數定義中
函數名：給函數起個名稱
參數列表：使用該函數時，傳入的數據
函數體語句：花括號內的代碼，函數內需要執行的語句
return表達式： 和返回值類型掛鉤，函數執行完後，返回相應的數據
**示例：**定義一個加法函數，實現兩個數相加
//函數定義
int add ( int num1, int num2)
{
	int sum = num1 + num2;
	 return sum;
}
6.3 函數的調用
**功能：**使用定義好的函數
語法： 函数名（参数）
示例：
//函數定義
int add ( int num1, int num2) //定義中的num1,num2稱為形式參數，簡稱形參
{
	int sum = num1 + num2;
	 return sum;
}


int main () {


	int a = 10 ;
	 int b = 10 ;
	 //調用add函數
	int sum = add (a, b); //調用時的a，b稱為實際參數，簡稱實參
	cout << " sum = " << sum << endl;


	a = 100 ;
	b = 100 ;


	sum = add (a, b);
	cout << " sum = " << sum << endl;


	system ( " pause " );


	return 0 ;
}
總結：函數定義裡小括號內稱為形參，函數調用時傳入的參數稱為實參
6.4 值傳遞
所謂值傳遞，就是函數調用時實參將數值傳入給形參
值傳遞時，==如果形參發生，並不會影響實參==
示例：
void swap ( int num1, int num2)
{
	cout << "交換前：" << endl;
	cout << " num1 = " << num1 << endl;
	cout << " num2 = " << num2 << endl;


	int temp = num1;
	num1 = num2;
	num2 = temp;


	cout << "交換後：" << endl;
	cout << " num1 = " << num1 << endl;
	cout << " num2 = " << num2 << endl;


	// return ;當函數聲明時候，不需要返回值，可以不寫return
}


int main () {


	int a = 10 ;
	 int b = 20 ;


	swap (a, b);


	cout << " mian中的a = " << a << endl;
	cout << " mian中的b = " << b << endl;


	system ( " pause " );


	return 0 ;
}
總結： 值傳遞時，形參是修飾不了實參的
6.5 函數的常見樣式
常見的函數樣式有4種
無參無返
有參無返
無參有返
有參有返
示例：
//函數常見樣式
// 1、無參無返
void test01 ()
{
	// void a = 10; //無類型不可以創建變量,原因無法分配內存
	cout << " this is test01 " << endl;
	 // test01();函數調用
}


// 2、有參無返
void test02 ( int a)
{
	cout << " this is test02 " << endl;
	cout << " a = " << a << endl;
}


// 3、無參有返
int test03 ()
{
	cout << " this is test03 " << endl;
	 return 10 ;
}


// 4、有參有返
int test04 ( int a, int b)
{
	cout << " this is test04 " << endl;
	 int sum = a + b;
	 return sum;
}
6.6 函數的聲明
作用：告訴編譯器函數名稱及如何調用函數。函數的實際主體可以單獨定義。
函數的聲明可以多次，但是函數的定義只能有一次
示例：
//聲明可以多次，定義只能一次
//聲明
int max ( int a, int b);
 int max ( int a, int b);
 //定義
int max ( int a, int b)
{
	return a > b ? a : b;
}


int main () {


	int a = 100 ;
	 int b = 200 ;


	cout << max (a, b) << endl;


	system ( " pause " );


	return 0 ;
}
6.7 函數的分文件編寫
**作用：**讓代碼結構更加清晰
函數分文件編寫一般有4個步驟
創建後綴名為.h的頭文件
創建後綴名為.cpp的源文件
在頭文件中寫函數的聲明
在源文件中寫函數的定義

示例：
// swap.h文件
# include <iostream>
 using namespace std ;


//實現兩個數字交換的函數聲明
void swap ( int a, int b);


// swap.cpp文件
# include "swap.h"


void swap ( int a, int b)
{
	int temp = a;
	a = b;
	b = temp;


	cout << " a = " << a << endl;
	cout << " b = " << b << endl;
}
// main函數文件
# include "swap.h"
 int main () {


	int a = 100 ;
	 int b = 200 ;
	 swap (a, b);


	system ( " pause " );


	return 0 ;
}


7 指針
7.1 指針的基本概念
指針的作用：可以通過指針間接訪問內存
內存編號是從0開始記錄的，一般用十六進制數字表示
可以利用指針變量保存地址
​
7.2 指針變量的定義和使用
指針變量定義語法： 数据类型 * 变量名；
示例：
int main () {


	// 1、指針的定義
	int a = 10 ; //定義整型變量a
	
	//指針定義語法：數據類型*變量名; 
	int * p;


	//指針變量賦值
	p = &a; //指針指向變量a的地址
	cout << &a << endl; //打印數據a的地址
	cout << p << endl;  //打印指針變量p


	// 2、指針的使用
	//通過*操作指針變量指向的內存
	cout << " *p = " << *p << endl;


	system ( " pause " );


	return 0 ;
}
指針變量和普通變量的區別
普通變量存放的是數據,指針變量存放的是地址
指針變量可以通過" * "操作符，操作指針變量指向的內存空間，這個過程稱為解引用
總結1： 我們可以通過& 符號獲取變量的地址
總結2：利用指針可以記錄地址
總結3：對指針變量解引用，可以操作指針指向的內存
7.3 指針所佔內存空間
提問：指針也是種數據類型，那麼這種數據類型占用多少內存空間？
示例：
int main () {


	int a = 10 ;


	int * p;
	p = &a; //指針指向數據a的地址


	cout << *p << endl; // *解引用
	cout << sizeof (p) << endl;
	cout << sizeof ( char *) << endl;
	cout << sizeof ( float *) << endl;
	cout << sizeof ( double *) << endl;


	system ( " pause " );


	return 0 ;
}
總結：所有指針類型在32位操作系統下是4個字節
7.4 空指針和野指針
空指針：指針變量指向內存中編號為0的空間
**用途：**初始化指針變量
**注意：**空指針指向的內存是不可以訪問的
示例1：空指針
int main () {


	//指針變量p指向內存地址編號為0的空間
	int * p = NULL ;


	//訪問空指針報錯
	//內存編號0 ~255為系統佔用內存，不允許用戶訪問
	cout << *p << endl;


	system ( " pause " );


	return 0 ;
}
野指針：指針變量指向非法的內存空間
示例2：野指針
int main () {


	//指針變量p指向內存地址編號為0x1100的空間
	int * p = ( int *) 0x1100 ;


	//訪問野指針報錯
	cout << *p << endl;


	system ( " pause " );


	return 0 ;
}
總結：空指針和野指針都不是我們申請的空間，因此不要訪問。
7.5 const修飾指針
const修飾指針有三種情況
const修飾指針--- 常量指針
const修飾常量--- 指針常量
const即修飾指針，又修飾常量
示例：
int main () {


	int a = 10 ;
	 int b = 10 ;


	// const修飾的是指針，指針指向可以改，指針指向的值不可以更改
	const int * p1 = &a;
	p1 = &b; //正確
	// *p1 = 100;報錯
	


	// const修飾的是常量，指針指向不可以改，指針指向的值可以更改
	int * const p2 = &a;
	 // p2 = &b; //錯誤
	*p2 = 100 ; //正確


    // const既修飾指針又修飾常量
	const int * const p3 = &a;
	 // p3 = &b; //錯誤
	// *p3 = 100; //錯誤


	system ( " pause " );


	return 0 ;
}
技巧：看const右側緊跟著的是指針還是常量, 是指針就是常量指針，是常量就是指針常量
7.6 指針和數組
**作用：**利用指針訪問數組中元素
示例：
int main () {


	int arr[] = { 1 , 2 , 3 , 4 , 5 , 6 , 7 , 8 , 9 , 10 };


	int * p = arr;   //指向數組的指針


	cout << "第一個元素：" << arr[ 0 ] << endl;
	cout << "指針訪問第一個元素：" << *p << endl;


	for ( int i = 0 ; i < 10 ; i++)
	{
		//利用指針遍歷數組
		cout << *p << endl;
		p++;
	}


	system ( " pause " );


	return 0 ;
}
7.7 指針和函數
**作用：**利用指針作函數參數，可以修改實參的值
示例：
//值傳遞
void swap1 ( int a , int b)
{
	int temp = a;
	a = b; 
	b = temp;
}
//地址傳遞
void swap2 ( int * p1, int *p2)
{
	int temp = *p1;
	*p1 = *p2;
	*p2 = temp;
}


int main () {


	int a = 10 ;
	 int b = 20 ;
	 swap1 (a, b); //值傳遞不會改變實參


	swap2 (&a, &b); //地址傳遞會改變實參


	cout << " a = " << a << endl;


	cout << " b = " << b << endl;


	system ( " pause " );


	return 0 ;
}
總結：如果不想修改實參，就用值傳遞，如果想修改實參，就用地址傳遞
7.8 指針、數組、函數
**案例描述：**封裝一個函數，利用冒泡排序，實現對整型數組的升序排序
例如數組：int arr[10] = { 4,3,6,9,1,2,10,8,7,5 };
示例：
//冒泡排序函數
void bubbleSort ( int * arr, int len)  // int * arr也可以寫為int arr[]
{
	for ( int i = 0 ; i < len - 1 ; i++)
	{
		for ( int j = 0 ; j < len - 1 - i; j++)
		{
			if (arr[j] > arr[j + 1 ])
			{
				int temp = arr[j];
				arr[j] = arr[j + 1 ];
				arr[j + 1 ] = temp;
			}
		}
	}
}


//打印數組函數
void printArray ( int arr[], int len)
{
	for ( int i = 0 ; i < len; i++)
	{
		cout << arr[i] << endl;
	}
}


int main () {


	int arr[ 10 ] = { 4 , 3 , 6 , 9 , 1 , 2 , 10 , 8 , 7 , 5 };
	 int len = sizeof (arr) / sizeof ( int );


	bubbleSort (arr, len);


	printArray (arr, len);


	system ( " pause " );


	return 0 ;
}
總結：當數組名傳入到函數作為參數時，被退化為指向首元素的指針
8 結構體
8.1 結構體基本概念
結構體屬於用戶==自定義的數據類型==，允許用戶存儲不同的數據類型
8.2 結構體定義和使用
語法：struct 结构体名 { 结构体成员列表 }；
通過結構體創建變量的方式有三種：
struct 結構體名變量名
struct 結構體名變量名= { 成員1值， 成員2值...}
定義結構體時順便創建變量
示例：
//結構體定義
struct student
{
	//成員列表
	string name;  //姓名
	int age;      //年齡
	int score;    //分數
}stu3; //結構體變量創建方式3




int main () {


	//結構體變量創建方式1 
	struct student stu1; // struct關鍵字可以省略


	stu1. name = "張三" ;
	stu1. age = 18 ;
	stu1. score = 100 ;
	
	cout << "姓名：" << stu1. name << "年齡：" << stu1. age   << "分數：" << stu1. score << endl;


	//結構體變量創建方式2 
	struct student stu2 = { "李四" , 19 , 60 };


	cout << "姓名：" << stu2. name << "年齡：" << stu2. age   << "分數：" << stu2. score << endl;




	stu3. name = "王五" ;
	stu3. age = 18 ;
	stu3. score = 80 ;
	


	cout << "姓名：" << stu3. name << "年齡：" << stu3. age   << "分數：" << stu3. score << endl;


	system ( " pause " );


	return 0 ;
}
總結1：定義結構體時的關鍵字是struct，不可省略
總結2：創建結構體變量時，關鍵字struct可以省略
總結3：結構體變量利用操作符''.'' 訪問成員
8.3 結構體數組
**作用：**將自定義的結構體放入到數組中方便維護
語法： struct 结构体名 数组名[元素个数] = { {} , {} , ... {} }
示例：
//結構體定義
struct student
{
	//成員列表
	string name;  //姓名
	int age;      //年齡
	int score;    //分數
}


int main () {
	
	//結構體數組
	struct student arr[ 3 ]=
	{
		{ "張三" , 18 , 80 },
		{ "李四" , 19 , 60 },
		{ "王五" , 20 , 70 }
	};


	for ( int i = 0 ; i < 3 ; i++)
	{
		cout << "姓名：" << arr[i]. name << "年齡：" << arr[i]. age << "分數：" << arr[i]. score << endl;
	}


	system ( " pause " );


	return 0 ;
}
8.4 結構體指針
**作用：**通過指針訪問結構體中的成員
利用操作符-> 可以通過結構體指針訪問結構體屬性
示例：
//結構體定義
struct student
{
	//成員列表
	string name;  //姓名
	int age;      //年齡
	int score;    //分數
};




int main () {
	
	struct student stu = { "張三" , 18 , 100 , };
	
	struct student * p = &stu;
	
	p-> score = 80 ; //指針通過->操作符可以訪問成員


	cout << "姓名：" << p-> name << "年齡：" << p-> age << "分數：" << p-> score << endl;
	
	system ( " pause " );


	return 0 ;
}
總結：結構體指針可以通過-> 操作符來訪問結構體中的成員
8.5 結構體嵌套結構體
作用：結構體中的成員可以是另一個結構體
**例如：**每個老師輔導一個學員，一個老師的結構體中，記錄一個學生的結構體
示例：
//學生結構體定義
typedef struct student
{
	//成員列表
	string name;  //姓名
	int age;      //年齡
	int score;    //分數
};


//教師結構體定義
struct teacher
{
    //成員列表
	int id; //職工編號
	string name;  //教師姓名
	int age;   //教師年齡
	struct student stu; //子結構體學生
};




int main () {


	struct teacher t1;
	t1. id = 10000 ;
	t1. name = "老王" ;
	t1. age = 40 ;


	t1. stu . name = "張三" ;
	t1. stu . age = 18 ;
	t1. stu . score = 100 ;


	cout << "教師職工編號：" << t1. id << "姓名：" << t1. name << "年齡：" << t1. age << endl;
	
	cout << "輔導學員姓名：" << t1. stu . name << "年齡：" << t1. stu . age << "考試分數：" << t1. stu . score << endl;


	system ( " pause " );


	return 0 ;
}
**總結：**在結構體中可以定義另一個結構體作為成員，用來解決實際問題
8.6 結構體做函數參數
**作用：**將結構體作為參數向函數中傳遞
傳遞方式有兩種：
值傳遞
地址傳遞
示例：
//學生結構體定義
struct student
{
	//成員列表
	string name;  //姓名
	int age;      //年齡
	int score;    //分數
};


//值傳遞
void printStudent (student stu )
{
	stu. age = 28 ;
	cout << "子函數中姓名：" << stu. name << "年齡：" << stu. age   << "分數：" << stu. score << endl;
}


//地址傳遞
void printStudent2 (student *stu)
{
	stu-> age = 28 ;
	cout << "子函數中姓名：" << stu-> name << "年齡：" << stu-> age   << "分數：" << stu-> score << endl;
}


int main () {


	student stu = { "張三" , 18 , 100 };
	 //值傳遞
	printStudent (stu);
	cout << "主函數中姓名：" << stu. name << "年齡：" << stu. age << "分數：" << stu. score << endl;


	cout << endl;


	//地址傳遞
	printStudent2 (&stu);
	cout << "主函數中姓名：" << stu. name << "年齡：" << stu. age   << "分數：" << stu. score << endl;


	system ( " pause " );


	return 0 ;
}

子函數中姓名：張三年齡：28分數：100
主函數中姓名：張三年齡：18分數：100


子函數中姓名：張三年齡：28分數：100
主函數中姓名：張三年齡：28分數：100
Press any key to continue . . .

總結：如果不想修改主函數中的數據，用值傳遞，反之用地址傳遞
8.7 結構體中const使用場景
**作用：**用const來防止誤操作
示例：
//學生結構體定義
struct student
{
	//成員列表
	string name;  //姓名
	int age;      //年齡
	int score;    //分數
};


// const使用場景
void printStudent ( const student *stu) //加const防止函數體中的誤操作
{
	// stu->age = 100; //操作失敗，因為加了const修飾
	cout << "姓名：" << stu-> name << "年齡：" << stu-> age << "分數：" << stu-> score << endl;


}


int main () {


	student stu = { "張三" , 18 , 100 };


	printStudent (&stu);


	system ( " pause " );


	return 0 ;
}
8.8 結構體案例
8.8.1 案例1
案例描述：
學校正在做畢設項目，每名老師帶領5個學生，總共有3名老師，需求如下
設計學生和老師的結構體，其中在老師的結構體中，有老師姓名和一個存放5名學生的數組作為成員
學生的成員有姓名、考試分數，創建數組存放3名老師，通過函數給每個老師及所帶的學生賦值
最終打印出老師數據以及老師所帶的學生數據。
示例：
struct Student
{
	string name;
	int score;
};
struct Teacher
{
	string name;
	Student sArray [ 5 ];
};


void allocateSpace (Teacher tArray[] , int len)
{
	string tName = "教師" ;
	string sName = "學生" ;
	string nameSeed = "ABCDE" ;
	 for ( int i = 0 ; i < len; i++)
	{
		tArray[i]. name = tName + nameSeed[i];
		
		for ( int j = 0 ; j < 5 ; j++)
		{
			(tArray+i)->sArray [j]. name = sName + nameSeed[j];
			tArray[i]. sArray [j]. score = rand () % 61 + 40 ;
		}
	}
}


void printTeachers (Teacher tArray[], int len)
{
	for ( int i = 0 ; i < len; i++)
	{
		cout << tArray[i]. name << endl;
		 for ( int j = 0 ; j < 5 ; j++)
		{
			cout << " \t姓名：" << tArray[i]. sArray [j]. name << "分數：" << tArray[i]. sArray [j]. score << endl;
		}
	}
}


int main () {


	srand (( unsigned int ) time ( NULL )); //隨機數種子頭文件#include <ctime>


	Teacher tArray[ 3 ]; //老師數組


	int len = sizeof (tArray) / sizeof (Teacher);


	allocateSpace (tArray, len); //創建數據


	printTeachers (tArray, len); //打印數據
	
	system ( " pause " );


	return 0 ;
}
8.8.2 案例2
案例描述：
設計一個英雄的結構體，包括成員姓名，年齡，性別;創建結構體數組，數組中存放5名英雄。
通過冒泡排序的算法，將數組中的英雄按照年齡進行升序排序，最終打印排序後的結果。
五名英雄信息如下：
		{ "劉備" , 23 , "男" },
		{ "關羽" , 22 , "男" },
		{ "張飛" , 20 , "男" },
		{ "趙雲" , 21 , "男" },
		{ "貂蟬" , 19 , "女" },
示例：
//英雄結構體
struct hero
{
	string name;
	int age;
	string sex;
};
//冒泡排序
void bubbleSort (hero arr[] , int len)
{
	for ( int i = 0 ; i < len - 1 ; i++)
	{
		for ( int j = 0 ; j < len - 1 - i; j++)
		{
			if (arr[j]. age > arr[j + 1 ]. age )
			{
				hero temp = arr[j];
				arr[j] = arr[j + 1 ];
				arr[j + 1 ] = temp;
			}
		}
	}
}
//打印數組
void printHeros (hero arr[], int len)
{
	for ( int i = 0 ; i < len; i++)
	{
		cout << "姓名：" << arr[i]. name << "性別：" << arr[i]. sex << "年齡：" << arr[i]. age << endl;
	}
}


int main () {


	struct hero arr[ 5 ] =
	{
		{ "劉備" , 23 , "男" },
		{ "關羽" , 22 , "男" },
		{ "張飛" , 20 , "男" },
		{ "趙雲" , 21 , "男" },
		{ "貂蟬" , 19 , "女" },
	};


	int len = sizeof (arr) / sizeof (hero); //獲取數組元素個數


	bubbleSort (arr, len); //排序


	printHeros (arr, len); //打印


	system ( " pause " );


	return 0 ;
}






#include <iostream>

using namespace std;

int main()
{
    printf("%d\n",printf("%s","Hello World!\n"));
    cout<<sizeof("Hello World!")<<endl;

    string a ="Hello World!\n";
    cout<<a.length()<<endl;
    cout<<a.size()<<endl;

    return 0;
}

//Random numbers generated between 1 and 10
#include <iostream>
#include <ctime>
#include <cstdlib>
using namespace std;
int main() 
{
 srand(time(0));  // Initialize random number generator.
  cout<<"Random numbers generated between 1 and 10:\n"<<endl;
 for(int i=0;i<10;i++)
     cout << (rand() % 10) + 1<<" "; 
 return 0; 
}



// Optimized bubble sort in C++
//Sorted Array in Ascending Order
#include <iostream>
#include <cstdlib> /* 亂數相關函數 */
#include <ctime>   /* 時間相關函數 */
 
using namespace std;


// print an array
void printArray(int array[], int size) {
  for (int i = 0; i < size; ++i) {
    cout << "  " << array[i];
  }
  cout << "\n";
}


// perform bubble sort
void bubbleSort(int array[], int size) {
    
  // loop to access each array element
  for (int i = 0; i < (size-1); ++i) {
      
    // check if swapping occurs
    int swapped = 0;
    
    // loop to compare two elements
    for (int j = 0; j < (size-i-1); ++j) {
        
      // compare two array elements
      if (array[j] > array[j + 1]) {

        // swapping occurs if elements
        // are not in intended order 
        int temp = array[j];
        array[j] = array[j + 1];
        array[j + 1] = temp;
        
        swapped = 1;
      }
      printArray(array, size);
    }

    // no swapping means the array is already sorted
    // so no need of further comparison
    if (swapped == 0)
      break;
  }
}



int main() {
  
  const int MAX = 10;
  int data[] = {9,8,7,6,5,4,3,2,1,0};
  
  /*int data[MAX]; //1D array to hold data
  for (int i=0; i<MAX; i++)
  {
   data[i]=rand() % 10+1;
   cout <<"  " << data[i];
  }
  cout << "\n"<<endl;*/
  
  // find the array's length
  int size = sizeof(data) / sizeof(data[0]);
  
  bubbleSort(data, size);
  
  cout << "Sorted Array in Ascending Order:\n";
  printArray(data, size);
}



// Optimized bubble sort in C++
// Optimized bubble sort in C++
//Sorted Array in Descending Order
#include <iostream>
#include <cstdlib> /* 亂數相關函數 */
#include <ctime>   /* 時間相關函數 */
 
using namespace std;


// print an array
void printArray(int array[], int size) {
  for (int i = 0; i < size; ++i) {
    cout << "  " << array[i];
  }
  cout << "\n";
}


// perform bubble sort
void bubbleSort(int array[], int size) {
    
  // loop to access each array element
  for (int i = (size-1); i >=0 ; --i) {
      
    // check if swapping occurs
    int swapped = 0;
    
    // loop to compare two elements
    for (int j = (size-2); j >=0 ; --j) {
        
      // compare two array elements
      if (array[j] > array[j + 1]) {

        // swapping occurs if elements
        // are not in intended order 
        int temp = array[j];
        array[j] = array[j + 1];
        array[j + 1] = temp;
        
        swapped = 1;
      }
      printArray(array, size);
    }

    // no swapping means the array is already sorted
    // so no need of further comparison
    if (swapped == 0)
      break;
  }
}



int main() {
  
  const int MAX = 10;
  int data[] = {9,8,7,6,5,4,3,2,1,0};
  
  /*int data[MAX]; //1D array to hold data
  for (int i=0; i<MAX; i++)
  {
   data[i]=rand() % 10+1;
   cout <<"  " << data[i];
  }
  cout << "\n"<<endl;*/
  
  // find the array's length
  int size = sizeof(data) / sizeof(data[0]);
  
  bubbleSort(data, size);
  
  cout << "Sorted Array in Descending Order:\n";
  printArray(data, size);
}




// Optimized bubble sort in C++
//Bubble sort using pointers
//Sorted Array in Ascending Order
#include <iostream>
#include <cstdlib> /* 亂數相關函數 */
#include <ctime>   /* 時間相關函數 */

using namespace std;

// print an array
void printArray(int* ptr , int n) {
  for (int i = 0; i < n; ++i) {
    cout << "  " << *(ptr + i);
  }
  cout << "\n";
}


// perform bubble sort
void bubbleSort(int* ptr, int size) {
    
  // loop to access each array element
  for (int i = 0; i < (size-1); ++i) {
      
    // check if swapping occurs
    int swapped = 0;
    
    // loop to compare two elements
    for (int j = 0; j < (size-i-1); ++j) {
        
      // compare two array elements
      if (*(ptr + j) > *(ptr + j + 1)) {

        // swapping occurs if elements
        // are not in intended order 
        int temp = *(ptr + j);
        *(ptr + j) = *(ptr + j + 1);
        *(ptr + j + 1) = temp;
        
        swapped = 1;
      }
      printArray(ptr, size);
    }

    // no swapping means the array is already sorted
    // so no need of further comparison
    if (swapped == 0)
      break;
  }
}



int main() {
  
  const int MAX = 10;
  int data[] = {9,8,7,6,5,4,3,2,1,0};
  
  /*int data[MAX]; //1D array to hold data
  for (int i=0; i<MAX; i++)
  {
   data[i]=rand() % 10+1;
   cout <<"  " << data[i];
  }
  cout << "\n"<<endl;*/
  
  // find the array's length
  int size = sizeof(data) / sizeof(data[0]);
  
  bubbleSort(data, size);
  
  cout << "Sorted Array in Ascending Order:\n";
  printArray(data, size);
}





//sort an Array using STL in C++
#include <iostream>
#include <algorithm>
using namespace std;
int main() {
    
   int arr[] = {9, 8, 7, 6, 5, 4, 3,2,1};
   int n = sizeof(arr) / sizeof(arr[0]);
   
   
   cout << "Array before sorting: ";
   for (int i = 0; i < n; i++)
      cout << arr[i] << " ";
      
      
   sort(arr, arr + n);
   cout << "\nArray after sorting: ";
   for (int i = 0; i < n; i++)
      cout << arr[i] << " ";
}




// C Dynamic Memory Allocation

#include <stdio.h>
#include <stdlib.h>

int main() {
  int n=1, *pointInt;
  float *pointFloat;

    // dynamically allocate memory
 pointInt = (int*) malloc(n * sizeof(int));
// pointInt = (int*) realloc(pointInt, n *  sizeof(int));
 pointFloat = (float*) calloc(n, sizeof(float));
 
     // assigning value to the memory
    *pointInt = 45;
    *pointFloat = 45.45f;
    
  // if memory cannot be allocated
  if(pointInt == NULL || pointFloat == NULL ) {
    printf("Error! memory not allocated.");
    exit(0);
  }

  printf("%d  \t  %p\n",*pointInt, pointInt);
  printf("%.2f  \t  %p\n",*pointFloat, pointFloat);
  
  
  // deallocating the memory
  free(pointInt);
  free(pointFloat);
  return 0;
}

、
+// C++ Memory Management: new and delete

#include <iostream>
using namespace std;

int main() {
    // declare an int pointer
    int* pointInt;

    // declare a float pointer
    float* pointFloat;

    // dynamically allocate memory
    pointInt = new int;
    pointFloat = new float;

    // assigning value to the memory
    *pointInt = 45;
    *pointFloat = 45.45f;

    cout << *pointInt<<"\t"<<pointInt<< endl;
    cout << *pointFloat<<"\t"<<pointFloat<< endl;

    // deallocate the memory
    delete pointInt;
    delete pointFloat;

    return 0;
}

// Linked list implementation in C

#include <stdio.h>
#include <stdlib.h>

// Creating a node
typedef struct node {
  int value;
struct  node *next;
};
typedef struct node node;
// print the linked list value
void printLinkedlist(struct node *p) {
  while (p != NULL) {
    printf("%d ", p->value);
    p = p->next;
  }
}

int main() {
  // Initialize nodes
  
  node *head;
   node *one = NULL;
   node *two = NULL;
   node *three = NULL;

  // Allocate memory
  one = malloc(sizeof(struct node));
  two = malloc(sizeof(struct node));
  three = malloc(sizeof(struct node));

  // Assign value values
  one->value = 1;
  two->value = 2;
  three->value = 3;

  // Connect nodes
  one->next = two;
  two->next = three;
  three->next = NULL;

  // printing node-value
  head = one;
  printLinkedlist(head);
}

// Linked list implementation in C++

// malloc() Prototype The prototype of malloc() as defined in the cstdlib header file is:  void* malloc(size_t size);

#include <stdio.h>
#include <stdlib.h>

//#include <iostream>
//using namespace std;
//#include <cstdlib>

// Creating a node
typedef struct node {
  int value;
struct  node *next;
};
typedef struct node node;
// print the linked list value
void printLinkedlist(struct node *p) {
  while (p != NULL) {
    printf("%d ", p->value);
    p = p->next;
  }
}

int main() {
  // Initialize nodes
  
  node *head;
   node *one = NULL;
   node *two = NULL;
   node *three = NULL;

  // Allocate memory
  //  Notice that we have type casted the void pointer returned by malloc() to  (node *)
  one = (node *)malloc(sizeof(struct node));
  two =(node *) malloc(sizeof(struct node));
  three =(node *) malloc(sizeof(struct node));

  // Assign value values
  one->value = 1;
  two->value = 2;
  three->value = 3;

  // Connect nodes
  one->next = two;
  two->next = three;
  three->next = NULL;

  // printing node-value
  head = one;
  printLinkedlist(head);
}



// Linked list implementation in C++ with Class

#include <bits/stdc++.h>
//#include <iostream>
using namespace std;
//#include <cstdlib>
// Creating a node
class Node {
   public:
  int value;
  Node* next;
};

int main() {
  Node* head;
  Node* one = NULL;
  Node* two = NULL;
  Node* three = NULL;

  // allocate 3 nodes in the heap
  one = new Node();
  two = new Node();
  three = new Node();

  // Assign value values
  one->value = 1;
  two->value = 2;
  three->value = 3;

  // Connect nodes
  one->next = two;
  two->next = three;
  three->next = NULL;

  // print the linked list value
  head = one;
  while (head != NULL) {
    cout << head->value;
    head = head->next;
  }
}



#include <stdio.h>
#include <stdlib.h>

int main()
{
   FILE * fp;

   fp = fopen ("file.txt", "w+");
   fprintf(fp, "%s", "Hello world!\n");
   
   fclose(fp);
   
   return(0);
}




//The following example creates a file called 'file.txt' and puts the text 'Hello, world!' followed by a newline into it.

#include <fstream>
int main()
{
    std::ofstream file;// can be merged to std::ofstream file("file.txt");
    file.open("file.txt");
    file << "Hello world!\n";
    file.close();// is not necessary because the destructor closes the open file by default
    return 0;
}



import math #python
x = math.sqrt(64)
print("Square root is ",x)
///////////////////////////////////////////////////////////////
#include <stdio.h>
#include <math.h>
int main()
{
 float x = sqrt(64);
printf("Square root is %.3f", x);
    return 0;
}
///////////////////////////////////////////////////////////////
#include <iostream>
#include <cmath>
#include <iomanip>

using namespace std;

int main()
{
 float x = sqrt(65);
 
 cout << fixed << setprecision(3);
 cout << "Square root is "<<x << endl;

    return 0;
}






// 1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9 + 10 + … + n  
// 1 - 2 + 3 - 4 + 5 - 6 + 7 - 8 + 9 - 10 + … + n      
#include <math.h> 
#include <stdio.h> 

double sum(double n) ;

int main() 
{ 
 double n =0; 
 printf("Please enter n = ");
 scanf("%lf",&n);
 printf("%.2lf", sum(n)); 
 return 0; 
}

double sum(double n) 
{ 
 double  total = 0;
 for (int i = 1; i <= n; i++) 
 {

    //total = total +  i * pow(1,i-1);      // 1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9 + 10 + … + n  
    total = total +  i * -(((i&0)<<1)-1);
    
    //total = total +  i * pow(-1,i-1);      // 1 - 2 + 3 - 4 + 5 - 6 + 7 - 8 + 9 - 10 + … + n  
    //total = total +  i * (((i&1)<<1)-1);    
 }
 return total; 
} 







