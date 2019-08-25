# C++ 菜鸟教程读书笔记
## 参考内容
* [C++教程|菜鸟教程](http://www.runoob.com/cplusplus/cpp-tutorial.html)
* [google c++ 编码规范](https://zh-google-styleguide.readthedocs.io/en/latest/google-cpp-styleguide/)
## 1. C++简介
### 1.1 基本特征
* C++是静态，编译性程序
* 支持过程化、面向对象、*泛型编程*
* 1979年在贝尔实验室开有Bjarne Stroustrup 开发的，1983年更名为C++
* 是C的超集，完全涵盖了C
* 组成：核心语言， C++标准库， 标准模板库
* 当年主要的标准 2011 年C++ 11， 2014年C++14， 2017年C++17， 当前尽量按照C++11来编程。
* 面向对象四大特征：封装，继承，多态，抽象
### 1.2 C++环境设置
主要使用GNU的GCC，G++编译环境
## 2. C++基本知识
**基本概念：**
* 对象：生活中的物体的数据抽象，对应生活中的名词
* 类：对象的模板，对象是类的实例
* 方法：指对象具备的行为、能力或者功能。
* 属性：对象具备的静态特性
* 数据：是面向过程编程方法中对生活中物体的抽象，等同于“对象”
* 函数：面向过程中对生活中事情的抽象，等同于“方法”

**C++程序的结构：**
* 头文件，以引入标准库或者第三方库
* 命名空间引入语句，例如：using namespace std;
* 全局变量
* 入口函数：int main 函数
* main函数体，包含：局部变量和各种语句等。例如：赋值语句、函数调用语句、选择语句、循环语句等。
* C++语句之间呈现三种结构：顺序结构、选择结构、循环结构
* 每天语句必须以分号结尾。
* C++中用 //, /* */进行注释书写。
* 赋值语句的构成，举例：x = 5+ 6 * y + max(4,7);, 其中x为变量，等式右边为表达式，
表达式由常量、变量、运算符、函数调用组成。

**C++中的标识符：**
* 给变量，函数，类，模块，常量等起名字所用。
* 规则：
    + 以英文字母或者 _ 开始，后面跟0个或者多个字母， _ 和数字。
    + 不允许出现特殊符号，例如：￥%&*等
    + 区分大小写，例如：Hello， hello是两个不同的标识符。
    + 不能和C++的关键词相同，例如：不能使用 int 作为标识符。

**C++中的数据类型：**
* 基本内置类型：bool, char, int, float, double, void, wchar_t。
* 基本修饰符：signed, unsigned, short, long
* 枚举类型，使用 enum 关键词定义。

**C++变量类型**
* C++中的变量就是对生活中物体的抽象，可以是基本数据类型变量，例如int, float, bool, double 等。也可以是对象型变量，例如： Person, Student, string, vector等。
* 定义：变量类型 变量名；例如：int i, j, k;
* 变量定义：创建了一个变量，并且为此变量分配了内存。，例如： int i,j,k; char ch; float salary; Person lxy; Person *llx = new Person(); 任何一个变量，在一个程序中同一个生命周期区间内只能定义1次。
* 变量声明：告诉编译器，会存在一个变量，但是这个变量在别处定义。使用extern 关键词， 例如：extern string name；
* 函数的声明： 只包含函数定义的第1行，即：返回值类型 函数名 参数列表； 例如： int func(int x, int y);
* 函数定义：函数声明+函数体，例如：
    ```c++
    int add(int x, y){
        return x +  y;
    }
    ```
* 左值和右值：编程语言中最重要的语句是赋值语句，等价于生活中的陈述句，例如： a = 5 + 6 * x + add(7,8); “=” 符号的左边就是左值，右边就是右值。 通常，左值是1个变量，右值是一个表达式。表达式由：常量、运算符、变量、函数构成。

**变量的作用域**
* C++程序在执行时存储数据的区域主要有三种： 全局变量区，线程或者进程栈区，堆。
* C++中的变量主要分为：全局变量和局部变量， 全局变量存储在全局变量去，局部变量存储在栈中；如果这些全局变量或者局部变量是指针变量的化，它所指向的数据可以是另外的全局变量、局部变量或者是堆中的一个数据对象。
* 全局变量：定义在所有函数之外的变量
* 局部变量：定义在函数内部，包含函数的参数型变量。
* 如果全局变量和局部变量都可见，使用时采用就近原则。如果要访问全局变量，使在变量前加符号“::”，例如：
```c++
    #include<iostream>
    #include<string>
    #include <limits>
    using namespace std;
    int i; // global variable
    int main()
    {
        i = 100; //global variable
        int i;
        i = 0; //local variable
        cout<<"local i="<<i<<endl; // using local i
        cout<<"global i="<<::i<<endl; // using global i
        return 0;
    }
```
* 常量定义的两种方法： （1） 使用 #define （2）使用const关键词

**C++存储类型**
* C++11中主要包含：staic, extern, mutable, thread_local
* static: 静态存储类型用于函数中的局部变量，本质上，它的声明周期和全局变量相同，但是变量可见性只局限于函数内部。
* extern: 对变量或者函数进行声明而已，不是定义。
* mutable：易变的对象。
* threa_local: 用于多线程编程。

**C++中的运算符**
* 算术运算：+， -， *， /， %， ++， --。
* 关系运算：==， !=, >, <, >=, <=。
* 逻辑运算：&&, ||, !
* 位运算: &, | ~, ^, >>, <<
* 赋值运算: =, 以及其派生出的复合赋值运算符，如： +=, -=, <<==。
* 其他运算：sizeof, ?:, ",", ".", "->", Cast, &, *

**结构化编程的三种结构**
* 本质：生活中的事情完全可以用三种结构：顺序结构、选择结构和循环结构模拟和仿真。
* 顺序结构：编程语句从上到下排列就是顺序结构，计算机执行程序的方式就是“存储程序，顺序执行”，所以，顺序结构是一种最自然支持的一种结构。
* 循环：为了模拟和仿真生活中事情或者步骤的反复执行过程。while，for， do...while。区别 -- for循环常用于已知或固定循环次数的计算过程。while循环常用于不固定循环次数的计算过程，依赖于一定的循环条件判定。 do...while, 和while的唯一区别就是循环体至少执行一次。
* 分支结构：但分支if语句， 双分支if...else..., 多分支的 if... else if...else if...else if ...... else...., 这个基于事物本身的复杂度而定。多分支if语句可以搞定一切分支结构，但是，有时候显得很啰嗦，C++提供了更加简明的switch语句。

**函数**
* 本质： 对事情或者过程的抽象。
* 组成：函数的返回结果、函数名、参数（形式参数，即输入数据）、函数体（即过程实现）。
* 函数声明：不包含函数体。
* 函数定义：有函数体。
* 函数调用：函数名(实际参数)。
* 函数的传值和传地址： 传值就是把实际参数的值拷贝一份给形式参数， 传地址是把实际参数的内存地址拷贝一份给形式参数。 
* 传地址又可以分为两类：通过指针和引用。
* 指针和引用的区别： 指针就是一个变量或者对象的内存起始地址，引用类似于生活中物体的名称（例如：别名），对引用的使用会作用到具体的对象上。 指针变量可以指向不同的对象，而引用变量只能够在定义时指向一个确定的对象，并且在使用过程中不允许更改。
* 在c/c++ 中， 加入函数A要调用函数B，过程如下： 
    * 在栈中保留函数A在调用前的各种现场数据，例如各种重要寄存器、调用函数B后的下一条指令地址等。
    * 把调用B的实际参数入栈
    * 把B中的局部变量入栈
    * 执行函数B
    * 函数B执行结束后，把函数B的局部变量、实际参数等退栈，并把函数调用的返回值通过eax寄存器返回到上一层。
* 如果函数B的返回值是64位以下长度的数据，上述过程就OK了。如果返回值是结构体数据，大于64位的数据，则其返回值需要用到A的一个临时数据区，这个临时数据区是在A的栈帧内分配，通过eax寄存器传入到B函数，B函数中调用 return 结构体对象; 语句时，会把相应的值赋值到A中的临时数据区。A中使用B的返回值时，再通过eax从此临时数据区复制其到A中的具体的结构体类型变量中。
    ```c++
    #include <iostream>

    using namespace std;

    typedef struct numbers {
        int number1;
        int number2;
        int number3;
        int number4;
    } Numbers;

    int add(int i, int j) {
        int result;
        result = i + j;
        return result;
    }

    Numbers numbers_add(Numbers i, Numbers j) {
        Numbers result;
        result.number1 = i.number1 + j.number1;
        result.number2 = i.number2 + j.number2;
        result.number3 = i.number3 + j.number3;
        result.number4 = i.number4 + j.number4;
        return result;
    }

    int main() {

        int n1, n2, n3;
        n1 = 10;
        n2 = 20;
        n3 = add(n1, n2);
        /* 说明如下：
         *     1. 实参n1, n2 入栈，局部变量 result 入栈。
         *     2. 计算n1+n2的值，赋值给result变量
         *     3. 遇到return result语句时，把result值赋值给eax寄存器
         *     4. 出栈释放掉n1,n2,result变量。
         *     5. 复制eax变量的值给n3, 使得n3的值等于n1+n2。 
         */
        cout << "n3=" << n3 << endl;
        
        Numbers numbers1, numbers2, numbers3;
        numbers1 = {10, 20, 30, 40};
        numbers2 = {110, 120, 130, 140};
        numbers3 = numbers_add(numbers1, numbers2);
        /* 说明如下：
         *     1. 在main方法栈区临时分配可以容纳一个Numbers结构对象的临时变量，并且把其起始地址存入eax寄存器。
         *     2. 把实参numbers1, numbers2入栈，局部变量 result 入栈。
         *     2. 计算numbers1 + numbers2的值，赋值给result变量
         *     3. 遇到return result语句时，把result值赋值给eax寄存器指向的Numbers的临时变量。
         *     4. 出栈释放掉n1,n2,result变量。
         *     5. 通过eax变量把eax指向的临时变量的值赋值给numbers3, 使得numbers3的值等于numbers1 + numbers2。 
         */

        cout << "numbers=" << "(" << numbers3.number1 << "," << numbers3.number2 << ","
            << numbers3.number3 << "," << numbers3.number4 << ")" << endl;

        return 0;
    }



    ```


**C++数组**
* 数据和数据之间经常呈现某些共性的关系，我们把这种关系叫做数据结构，常见的有三大类： 线性结构、树状结构、图状结构。
* C++数组是一种最常见的线性结构。
* 数组中的每个元素可以是任意值，如果每个元素是一个数组，那么这可以定义成二维数组，如果每个元素是个二维数组，则可以定义三维数组，如果每个元素为1个n-1维的数组，那么可以定义出n维数组。我们一般熟练掌握好3维以下即可。 数组中的元素可以是int, double, char等基本数据类型元素，也可以是任意的自定义数据类型，例如：Person， Student等通过class来自定义出来的数据类型。

**C++中的字符串**
* 本质：是数组，每个元素是char类型。
* 其最后一个元素符号为'\0'。
* 建议使用C++中的string类型。

**C++中的struct关键词**
* struct可以定义任意新的数据结构。
* struct也可以包含方法实现
* 换而言之，通过struct完全可以体现面向对象的编程思想。但是，C++中面向对象思想的关键词可以提供更精细、更自然的控制方式，例如：private, public, protected 等访问权限控制。

## 3. C++中的面向对象编程
**类的基本知识**
* 面向对象理念中几个概念：
    * 万物都是对象，对象有其生命的周期，包含: 产生、变化、消亡。
    * 对象由静态的属性、动态的行为或者功能构成，对象都从属于一定的类。所以，产生对象之前必须要先定义类。类是对象的模板，对象是类的实例。
    * 使用一个类可以产生多个对象，每个对象都拥有自己的实例数据和方法，这些数据和方法又称为实例成员。实例数据叫做“属性成员、数据成员”，实例方法又称为“成员函数”。在C++的实现中，每个对象有各自的数据成员副本、但是共用函数成员副本。
    * 成员修饰符：public，private，protected。public：所有其他对象或者方法可以使用该成员；private：所属对象函数才可以访问；protected：所属对象函数、其派生类对象函数可以访问。
    * 构造函数：在产生一个新的对象时被自动调用的函数，例如：一个小孩出生，就构造了一个新的生命，他拥有一定的属性，例如：50cm长，8斤重等等。
    * 析构函数：一个对象在消亡前调用的函数, 主要用于清理一些占用的资源。
    * C++的静态成员：类中定义的静态数据成员，会被保存到全局数据区，这个区域又称为静态/全局数据区； 类中定义的静态方法（method），它不需要产生对象就可以直接使用，使用方法为，类名::静态成员函数，例如： Box::getCount;

**继承**
* 反映面向对象的is a 关系，是面向对象编程思想三大基石：封装、继承和多态中的重要一环。是面向对象软件重用的基石。
* 继承类通过public，protected，private关键词从基类中继承其方法和属性，但是一般只会用public继承。
* 多重继承：从多个基类中继承属性和方法。

**运算符重载和函数重载**
* 运算符重载：赋予常用的运算符，例如 +， -， *， / 针对不同的数据类型具有新的含义。
* 函数重载（重载，overload）：在一个类中可以定义多个同名的函数，但是，这些函数的签名（signature)必须不同。签名的形式是： 函数名(参数1的类型，参数2的类型，..., 参数n的类型)。本质上，函数重载是多态的一种体现，而且是“编译时多态”。
    ```c++
    #include <iostream>
    using namespace std;
    class printData
    {
    public:
        void print(int i) { // print(int), 实际编译器函数名为：print_int
            cout << "Integer " << i << endl;
        }

        void print(double  f) { // print(double), 实际编译器函数名为：print_double
            cout << "float: " << f << endl;
        }

        void print(char c[]) { // print(char), 实际编译器函数名为：print_char
            cout << "string: " << c << endl;
        }
        void print(int a, int b){ // print(int, int), 实际编译器函数名为：print_int_int

        }
        void print(int a, double b){ // print(int, double), 实际编译器函数名为：print_int_double

        }
        void print(double a, int b){ // print(double, int), 实际编译器函数名为：print_double_int

        }
    };

    int main(void)
    {
        printData pd;

        // 输出整数
        pd.print(5);
        // 输出浮点数
        pd.print(500.263);
        // 输出字符串
        char c[] = "Hello C++";
        pd.print(c);

        return 0;
    }
    ```

**运行时多态（覆盖，override）**
* 覆盖是一种运行时多态：存在于父子类中的同名函数（具有完全相同的signature）。必须在父类函数前使用关键词virtual 修饰。
* 编译器在编译期间不能确定具体的调用函数，需要在执行时由执行环境的上下文来确定。所以称为运行时多态。
* 如果一个类中包含纯虚函数（只有函数声明，没有函数实现）的话，这个类是不完整的，不能用于产生具体的实例（对象），只可以用来被继承或者扩展。含有纯虚函数的类叫做抽象类。

    ```c++
    #include <iostream>
    using namespace std;

    class Shape {
    protected:
        int width, height;
    public:
        Shape( int a=0, int b=0)
        {
            width = a;
            height = b;
        }
        virtual int area() // area()
        {
            cout << "Parent class area :" <<endl;
            return 0;
        }
    };
    class Rectangle: public Shape{
    public:
        Rectangle( int a=0, int b=0):Shape(a, b) { }
        virtual  int area () // area()
        {
            cout << "Rectangle class area :" <<(width * height)<<endl;
            Shape::area();
            return (width * height);
        }
    };
    class Triangle: public Shape{
    public:
        Triangle( int a=0, int b=0):Shape(a, b) { }
        virtual  int area ()
        {
            cout << "Triangle class area :" << (width * height / 2)<<endl;
            return (width * height / 2);
        }
    };
    // 程序的主函数
    int main( )
    {
        Shape *shape;
        Rectangle rec(10,7);
        Triangle  tri(10,5);

        // 存储矩形的地址
        shape = &rec;
        // 调用矩形的求面积函数 area
        shape->area();

        // 存储三角形的地址
        shape = &tri;
        // 调用三角形的求面积函数 area
        shape->area();

        return 0;
    }
    ```

    ```c++
    #include <iostream>
    using namespace std;

    class Shape {
    protected:
        int width, height;
    public:
        Shape( int a=0, int b=0)
        {
            width = a;
            height = b;
        }
        virtual int area() = 0;
    };
    class Rectangle: public Shape{
    public:
        Rectangle( int a=0, int b=0):Shape(a, b) { }
        virtual  int area () // area()
        {
            cout << "Rectangle class area :" <<(width * height)<<endl;
            //Shape::area();
            return (width * height);
        }
    };
    class Triangle: public Shape{
    public:
        Triangle( int a=0, int b=0):Shape(a, b) { }
        virtual  int area ()
        {
            cout << "Triangle class area :" << (width * height / 2)<<endl;
            return (width * height / 2);
        }
    };
    // 程序的主函数
    int main( )
    {
        Shape *shape;
        Rectangle rec(10,7);
        Triangle  tri(10,5);
    //    Shape sp;


        // 存储矩形的地址
        shape = &rec;
        // 调用矩形的求面积函数 area
        shape->area();

        // 存储三角形的地址
        shape = &tri;
        // 调用三角形的求面积函数 area
        shape->area();

        return 0;
    }
    ```
**封装**
* 主要体现为以下几种：
    * 把数据和方法用class包在一起定义类。
    * 对数据和方法通过public，protected，privat等进行访问权限控制（读和写）。
* 设计策略： 套用童安格的一首歌《无泪有伤》中的一句歌词：“所谓成熟就是学会隐藏”。也就是：尽量使用private来修饰没有必要往外暴露的数据和方法。

**接口实现**
* 接口（interface）：就是规则。例如：插座接口包含：电压，插脚数目，供电功能。
* C++中使用抽象类来实现接口定义。即使用Abastract Class来实现接口，Java中使用关键词 interface 来到定义接口。

**异常**
* 异常就是不正常，指程序执行过程中出现不正常或者错误。
* 异常处理可以针对这些异常提供合适的处理方式，增强程序的健壮性。
* 使用try...catch关键词进行异常处理， 通过throw关键词可以抛出异常对象。
* C++提供的异常基础类为Exception，程序员可以通过扩展Exception类来产生符合自己程序的异常处理体系。






