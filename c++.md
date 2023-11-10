#  c++

##  std::stringstream

```c++
std::stringstream 使用方法

首先创建一个 std::stringstream 对象

std::stringstream ss;

将输入存入 ss 的内部缓冲区

ss<<data;

从ss内部缓冲区逐个读取数据

方法一 :

char ch;

while(ss>>ch)  // 这种方法会过滤掉空格
{
	std::cout<<ch;
}

方法二 ：

char ch ;
while(ss.get(ch)  // 这种方法不会会过滤掉空格
{
	std::cout<<ch;
}

//std::stringstream 默认以空格为分隔符来提取数据，并将数据分配给不同的变量。如果字符串中包含多个空格，它将在每个空格处分隔数据，并尝试将这些分隔的部分分配给不同的变量。

例子 ：

std::string str1,str2;
ss<<"hello world";
ss>>str1>>str2; // 此时 str1 中 存入的是hello str2中存入的是world; 此时的空格会被默认为分隔符

//更改默认的分隔符，可以使用 std::stringstream 的 delimiter 函数来设置自定义的分隔符。例如，你可以将分隔符设置为逗号 ,，这样它将使用逗号来分隔数据。

std::stringstream ss("apple,banana,cherry");
std::string fruit1, fruit2, fruit3;
ss.delimiter(',');
ss >> fruit1 >> fruit2 >> fruit3;

```