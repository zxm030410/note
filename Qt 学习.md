#  Qt 学习

##  初识

```c++
#include "mywidget.h"

#include <QApplication> // 包含一个应用程序类的头文件
#include <QLocale>
#include <QTranslator>


// argc 命令行变量的数量 argv 命令行变量的数组
int main(int argc, char *argv[])
{
    // a应用程序对象 ， 在Qt中，应用程序对象，有且仅有一个
    QApplication a(argc, argv);

    QTranslator translator;
    const QStringList uiLanguages = QLocale::system().uiLanguages();
    for (const QString &locale : uiLanguages) {
        const QString baseName = "Project_01_" + QLocale(locale).name();
        if (translator.load(":/i18n/" + baseName)) {
            a.installTranslator(&translator);
            break;
        }
    }
    // 窗口对象 myWidget父类 -> QWidget



    myWidget w;

    //窗口对象 默认不会显示，必须要调用show方法显示窗口
    w.show();


    //让应用程序对象进入消息循环
    //让代码阻塞到这行
    return a.exec();
}

```





##  命名规范

类名 首字母大写 ， 单词和单词之间首字母大写

函数名 变量名称 首字母小写 ， 单词和单词之间首字母的大写



快捷键



注释 CTRL + /

运行 CTRL + R

编译 CTRL + B

编译 CTRL + 鼠标滚轮

查找 CTRL + F 

整行移动 CTRL + SHIFT +  ↑  或者  ↓ 

帮助文档 F1   

自动对齐  CTRL + i 

同名之间的 .h 和 .cpp 切换 F4

##  QPushButton 按钮控件常用Api

```c++
 //头文件
 #include <QPushButton>
 
 //创建一个按钮
    QPushButton *btn = new QPushButton;
    btn ->show(); //show 以顶层方式弹出窗口控件
    //让btn对象，依赖在 myWidget窗口中
    btn ->setParent(this);

    //显示文本
    btn->setText("第一个按钮");

    // 创建第二个按钮 按照控件的大小创建窗口
    QPushButton *btn2 = new QPushButton("第二个按钮",this);

    //移动btn2按钮
    btn2 ->move(100,100);

    // 重置窗口大小 按钮也可以重置
    resize(600,400);

    //设置固定窗口大小
    setFixedSize(600,400);

    //设置窗口标题
    setWindowTitle("第一个标题");
```

##  对象树

