 C++ 入门教程：变量、数据类型与基本输入/输出

![C++ Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/1/18/ISO_C%2B%2B_Logo.svg/1200px-ISO_C%2B%2B_Logo.svg.png)
*图片来源：Wikimedia Commons*

## 🚀 欢迎来到 C++ 的世界！

C++ 是一种功能强大、高效且用途广泛的编程语言，广泛应用于系统编程、游戏开发、高性能计算等领域。对于初学者来说，理解其核心概念是迈向C++大师的第一步。

本教程将带你了解C++中最基础但至关重要的概念：**变量**、**数据类型**以及如何进行**基本的输入/输出操作**。

### 🎯 学习目标

完成本教程后，你将能够：
*   理解变量在C++中的作用。
*   识别并使用常见的C++数据类型。
*   声明和初始化变量。
*   使用 `cout` 进行屏幕输出。
*   使用 `cin` 获取用户输入。

### 📚 前置知识

*   对编程有基本概念（例如，什么是程序、指令）。
*   一个C++编译器（如GCC、Clang或MSVC）和代码编辑器（如VS Code、CLion）。

---

## 1. 什么是变量？

在编程中，**变量**可以看作是内存中一个命名的存储区域，用于存放数据。你可以把它们想象成贴有标签的盒子，每个盒子可以装不同类型的东西。当你需要使用或修改这些数据时，只需通过变量名来访问它。

### 声明变量

在C++中，使用变量之前必须先**声明**它。声明变量时，你需要指定变量的**数据类型**和**变量名**。

```cpp
数据类型 变量名;
示例：

CPP
int age;         // 声明一个名为 age 的整数变量
double price;    // 声明一个名为 price 的双精度浮点数变量
char initial;    // 声明一个名为 initial 的字符变量
初始化变量
声明变量后，通常会给它一个初始值，这称为初始化。你可以选择在声明时初始化，也可以在之后赋值。

CPP
// 声明时初始化
int score = 100;
std::string name = "Alice"; // 注意：string 类型需要 #include <string>

// 先声明，后赋值
double temperature;
temperature = 25.5;
2. C++ 中的数据类型
数据类型定义了变量可以存储的数据种类以及这些数据可以执行的操作。C++ 提供了多种内置数据类型：

数据类型	描述	示例值	内存大小 (通常)
int	整数（正数、负数、零）	10, -5, 0	4 字节
double	双精度浮点数（带小数的数字）	3.14, -0.5	8 字节
float	单精度浮点数（带小数的数字，精度低于double）	3.14f, -0.5f	4 字节
char	单个字符	'A', 'b', '7'	1 字节
bool	布尔值（真或假）	true, false	1 字节
std::string	字符序列（文本字符串）	"Hello", "C++"	动态
注意： std::string 并不是内置类型，它是一个标准库类，但使用频率极高，因此在这里列出。使用它需要 #include <string>。

示例：使用不同数据类型
CPP
#include <iostream> // 用于输入输出
#include <string>   // 用于 std::string

int main() {
    // 整数类型
    int age = 30;
    std::cout << "我的年龄是: " << age << std::endl;

    // 浮点数类型
    double pi = 3.14159;
    std::cout << "圆周率是: " << pi << std::endl;

    // 字符类型
    char grade = 'A';
    std::cout << "我的成绩是: " << grade << std::endl;

    // 布尔类型
    bool isStudent = true;
    std::cout << "我是学生吗? " << isStudent << std::endl; // true 输出 1, false 输出 0

    // 字符串类型
    std::string greeting = "你好，C++！";
    std::cout << greeting << std::endl;

    return 0;
}
运行结果：

TEXT
我的年龄是: 30
圆周率是: 3.14159
我的成绩是: A
我是学生吗? 1
你好，C++！
3. 基本输入/输出 (I/O)
C++ 使用流 (streams) 的概念进行输入和输出。最常用的两个流对象是：

std::cout：用于向标准输出设备（通常是屏幕）输出数据。
std::cin：用于从标准输入设备（通常是键盘）读取数据。
要使用 std::cout 和 std::cin，你需要包含 <iostream> 头文件。

std::cout：输出到屏幕
std::cout 结合插入运算符 << 来将数据发送到输出流。

CPP
#include <iostream> // 包含输入输出库

int main() {
    std::cout << "Hello, World!" << std::endl; // 输出字符串并换行
    std::cout << "我的幸运数字是: " << 7 << std::endl; // 输出字符串和整数
    std::cout << "C++ 很有趣！" << " 我正在学习它。" << std::endl; // 链式输出

    return 0;
}
std::endl：是一个操纵符，用于在输出末尾插入一个换行符并刷新输出缓冲区。
你也可以使用 \n 来表示换行，它通常比 std::endl 效率更高，因为它不强制刷新缓冲区。
CPP
std::cout << "第一行\n第二行\n";
std::cin：从键盘获取输入
std::cin 结合提取运算符 >> 来从输入流中读取数据并存储到变量中。

CPP
#include <iostream> // 包含输入输出库
#include <string>   // 包含字符串库

int main() {
    std::string name;
    int age;

    std::cout << "请输入你的名字: ";
    std::cin >> name; // 从键盘读取字符串并存入 name 变量

    std::cout << "请输入你的年龄: ";
    std::cin >> age;  // 从键盘读取整数并存入 age 变量

    std::cout << "你好，" << name << "！你今年 " << age << " 岁了。" << std::endl;

    return 0;
}
运行示例：

TEXT
请输入你的名字: Alice
请输入你的年龄: 25
你好，Alice！你今年 25 岁了。
注意： std::cin >> name; 默认只读取到第一个空格。如果想读取包含空格的整行文本，可以使用 std::getline(std::cin, name);。

4. 完整示例：一个简单的用户交互程序
让我们把所学知识结合起来，编写一个简单的程序，询问用户的姓名和出生年份，然后计算并显示他们的年龄。

CPP
#include <iostream> // 用于 std::cout, std::cin, std::endl
#include <string>   // 用于 std::string
#include <limits>   // 用于 std::numeric_limits (用于清除输入缓冲区，虽然在这个简单例子中可以省略，但良好实践会考虑)

int main() {
    std::string userName;
    int birthYear;
    int currentYear = 2024; // 假设当前年份是 2024

    // 1. 获取用户姓名
    std::cout << "欢迎来到年龄计算器！" << std::endl;
    std::cout << "请输入你的名字: ";
    // 使用 getline 读取整行，包括空格
    std::getline(std::cin, userName); 

    // 2. 获取用户出生年份
    std::cout << "请输入你的出生年份 (例如: 1990): ";
    std::cin >> birthYear;

    // 错误处理：如果用户输入了非数字，cin 会进入错误状态
    if (std::cin.fail()) {
        std::cout << "无效的输入！请输入一个数字年份。" << std::endl;
        // 清除错误标志并忽略剩余的错误输入
        std::cin.clear();
        std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
        return 1; // 返回非零表示程序异常退出
    }

    // 3. 计算年龄
    int age = currentYear - birthYear;

    // 4. 显示结果
    std::cout << "\n------------------------------------" << std::endl;
    std::cout << "你好，" << userName << "！" << std::endl;
    std::cout << "根据你的出生年份 " << birthYear << " 和当前年份 " << currentYear << "，" << std::endl;
    std::cout << "你大约 " << age << " 岁了。" << std::endl;
    std::cout << "------------------------------------" << std::endl;

    return 0; // 返回 0 表示程序成功执行
}
编译和运行：
如果你使用GCC编译器，可以将上述代码保存为 age_calculator.cpp，然后在终端中执行：

BASH
g++ age_calculator.cpp -o age_calculator
./age_calculator
总结
恭喜你！你已经掌握了C++编程的基石：

变量是存储数据的命名内存区域。
数据类型定义了变量可以存储的数据种类（如 int, double, char, bool, std::string）。
std::cout 用于向屏幕输出信息。
std::cin 用于从键盘获取用户输入。
这些概念是所有C++程序的基础。熟练掌握它们将为你未来的学习打下坚实的基础。

🚀 下一步
尝试编写更多使用变量和I/O的小程序。
探索更多C++数据类型，例如 long, short, unsigned 等。
学习C++中的运算符（算术运算符、比较运算符等）。
了解条件语句（if, else if, else）和循环（for, while）。
祝你在C++的学习旅程中一切顺利！如果你有任何问题，欢迎在评论区留言。

本文由 [piaoai-stack/GitHub piaoai-stack] 撰写，发布于 [piaoai-stack/GitHub Pages]。
