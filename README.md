# JAVA-
一些关于Java面试的学习
### 理解static
[参考链接](http://www.cnblogs.com/dolphin0520/p/3799052.html)
#### static方法
静态方法**不依赖于任何对象**就可以进行访问，因此没有this，*在静态方法中不能访问类的非静态成员变量和非静态成员方法，因为非静态成员方法/变量都是必须依赖具体的对象才能够被调用*。例如：main方法就是static，因为程序在执行main方法的时候没有创建任何对象，因此只有通过类名来访问。
#### static变量
静态变量和非静态变量的区别是：静态变量被**所有的对象所共享**，它当且仅当在类初次**加载时会被初始化**。而非静态变量是**对象**所拥有的，在**创建对象**的时候被初始化，存在多个副本，各个对象拥有的副本互不影响。static成员变量的初始化顺序**按照定义的顺序**进行初始化。
#### static代码块
static关键字还有一个比较关键的作用就是 用来形成静态代码块以优化程序性能。static块可以置于类中的任何地方，类中可以有多个static块。在类初次被加载的时候，会按照static块的顺序来执行每个static块，并且只会执行一次。
*因为静态的成员属于类，随着类的加载而加载到静态方法区内存，当类加载时，此时不一定有实例创建，没有实例，就不可以访问非静态的成员。*
### final关键字 ###
final修饰类不能被继承，修饰方法不能被重写。（可以重载）修饰变量，只能被赋值一次，必须要初始化。
### 方法重写和方法重载 ###
***方法重写***：若子类中的方法与父类中的某一方法具有相同的方法名、返回类型和参数表，则新方法将覆盖原有的方法。用super关键字访问父类方法。
***方法重载***：同一个类的相同名称的方法，参数类型，个数，顺序。**只有返回值不同是不构成 方法重载**。
### Java中的构造方法和构造方法重载
***构造方法***：为了初始化对象，构造函数的函数名和类名一致。构造方法的重载类似于方法重载，参数列表不同。
### Java支持多继承？ ###
Java只支持单继承，出于对安全性的考虑。
### 接口和抽象类的区别 ###

***抽象类***：是含有抽象方法（abstact修饰的方法，只声明，没有具体实现）的类。抽象类不能创建对象，抽象类是为了继承而存在的。

***接口***：一种特殊的抽象类，接口中的方法必须全是抽象方法（必须是public abstract修饰）接口中的变量必须是public abstract final修饰。

***区别***：1 抽象类可以提供成员方法的实现细节，而接口中只能存在public abstract 方法；

　        　2 抽象类中的成员变量可以是各种类型的，而接口中的成员变量只能是public static final类型的；

　        　3 接口中不能含有静态代码块以及静态方法，而抽象类可以有静态代码块和静态方法；

        　　4 一个类只能继承一个抽象类，而一个类却可以实现多个接口。
