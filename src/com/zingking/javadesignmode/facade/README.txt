门面(外观)模式
Facade Pattern
1.定义
Provide a unified interface to a set of interfaces in a subsystem.Facade defines a higher-level interface that makes the
subsystem easier to use.
要求一个子系统的外部与其内部的通信必须通过一个统一的对象进行。门面模式提供一个高层次的接口，使得子系统更易于使用

2.组成
Facade门面角色
客户端可以调用这个角色的方法，此角色知晓子系统的所有功能和责任。本角色将所有从客户端的请求都委派到相应的子系统，该角色没
有实际的业务逻辑，只是一个委托类。客户端通过此类与子系统交互

一般是一个单例类

Subsystem 子系统角色
可以同时有一个或者多个子系统。每个子系统都不是一个单独的类，而是一个类的集合。

子系统不知道门面的存在，对于子系统而言，门面仅仅是另外一个客户端而已

3.优缺点
优点：
①减少系统的互相依赖
如果不使用门面模式，外界直接深入系统内部，相互间构成强耦合关系。改用门面模式后所有外部对系统的依赖都是对门面对象的依赖，
与子系统无关。
②提高灵活性
子系统内部不管如何变化或者重构，只有不影响到门面对象，可以随意改动
③提高安全性
外部只能通过门面范围子系统，门面想让你访问哪些你就只能访问哪些，没有开通的方法，休想访问

缺点：
不符合开闭原则，对扩展开放，对修改关闭。如果门面类发生了错误，需要修改门面角色代码就有可能影响到外部客户端的使用。

4.适用场景
①为复杂模块或者相对独立的模块或子系统提供一个供外界访问的接口
②预防低水平人员带来的风险扩散

5.demo
简单的医院系统
挂号、门诊、化验、收费、取药










