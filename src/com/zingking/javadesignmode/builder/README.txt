建造者模式
1.定义
也叫生成器模式，Separate the contruction of a complex object from its representation so that the same construction process
can create different representations.
将一个复制对象的构建与它的表示分离，使得同样的构建过程可以创建不同的表示。

产品的的内部表象(定义中的表示)解释：一个产品常有不同的组成成分作为产品的零件，这些零件有可能是对象，也有可能不是对象，他
们通常又叫做产品的内部表象（internal representation）。不同的产品可以有不同的内部表象，也就是不通的零件。

表象(表示)：
有可能是对象：可以理解为是一个具体事例类中的成员变量，建造者模式就是把对象的构建和成员变量的赋值分离开来，当这个产品的构建比较复杂
时可以使用该模式。
不是对象：内部表象也可以理解为方法执行顺序，在build对象的时候传不同的参数导致某些方法执行属性不同，或者方法不执行(见demo
模板方法和建造者模式结合)

该模式与工厂模式的主要区别：
1.该模式注重零件的装配顺序，不同的零件顺序可以产生不同的产品；工厂模式注重的是产品结果，工厂模式可以用于零件的创建

完整的建造者模式有几个角色：
1.导演类：提供给外部使用，由导演指挥建造
2.抽象建造者：定义建造者的通用接口
3.具体建造者：负责建造具体的产品，一般由几个产品就需要几个建造者。建造是写好给外部用的
4.产品类：建造者建造的产品即返回给上层使用的实例对象

退化的建造者：
1.省略抽象建造者，当只有一个建造者角色的话就可以省略抽象建造者
2.省略导演类：建造者角色只有一个，导演类的功能也可以交给建造者，这种建造者和模板方法有些类似
3.合并建造者与产品类：在产品类中定义内部类实现建造者的功能(AlertDialog.Builder、链式调用)