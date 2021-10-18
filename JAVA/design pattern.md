# 依赖倒置原则（DIP）
- High level modules should not depend upon low level modules. Both should depend upon abstractions. Abstractions should not depend upon details. Details should depend upon abstractions
- 高层模块不应该依赖低层模块，两者都应该依赖其抽象；抽象不应该依赖细节，细节应该依赖抽象
# 单一职责原则（SRP）
- There should never be more than one reason for a class to change。
- 应该有且仅有一个原因引起类的变更。简单点说，一个类，最好只负责一件事，只有一个引起它变化的原因。
# 接口隔离原则（ISP）
- Clients should not be forced to depend upon interfaces that they don't use，还有一种定义是The dependency of one class to another one should depend on the smallest possible interface。
- 其一是不应该强行要求客户端依赖于它们不用的接口；其二是类之间的依赖应该建立在最小的接口上面。简单点说，客户端需要什么功能，就提供什么接口，对于客户端不需要的接口不应该强行要求其依赖；类之间的依赖应该建立在最小的接口上面，这里最小的粒度取决于单一职责原则的划分。
# 开闭原则（OCP）
- Software entities (classes, modules, functions) should be open for extension but closed for modification。
- 软件实体（包括类、模块、功能等）应该对扩展开放，但是对修改关闭

# 里氏替换原则（LSP）
- 子类对象能够替换父类对象，而程序逻辑不变。
- 就是尽量不要从可实例化的父类中继承，而是要使用基于抽象类和接口的继承。

## 简单工厂设计模式 
工厂模式（Factory Pattern）是 Java 中最常用的设计模式之一。这种类型的设计模式属于创建型模式，它提供了一种创建对象的最佳方式。

在工厂模式中，我们在创建对象时不会对客户端暴露创建逻辑，并且是通过使用一个共同的接口来指向新创建的对象。
## 工厂方法设计模式 
抽象工厂模式（Abstract Factory Pattern）是围绕一个超级工厂创建其他工厂。该超级工厂又称为其他工厂的工厂。这种类型的设计模式属于创建型模式，它提供了一种创建对象的最佳方式。

在抽象工厂模式中，接口是负责创建一个相关对象的工厂，不需要显式指定它们的类。每个生成的工厂都能按照工厂模式提供对象。
## 单例设计模式 
单例模式（Singleton Pattern）是 Java 中最简单的设计模式之一。这种类型的设计模式属于创建型模式，它提供了一种创建对象的最佳方式。

这种模式涉及到一个单一的类，该类负责创建自己的对象，同时确保只有单个对象被创建。这个类提供了一种访问其唯一的对象的方式，可以直接访问，不需要实例化该类的对象。

注意：

1、单例类只能有一个实例。
2、单例类必须自己创建自己的唯一实例。
3、单例类必须给所有其他对象提供这一实例
## 建造者设计模式
建造者模式（Builder Pattern）使用多个简单的对象一步一步构建成一个复杂的对象。这种类型的设计模式属于创建型模式，它提供了一种创建对象的最佳方式。

一个 Builder 类会一步一步构造最终的对象。该 Builder 类是独立于其他对象的。
## 适配器设计模式 
https://www.runoob.com/design-pattern/adapter-pattern.html

适配器模式（Adapter Pattern）是作为两个不兼容的接口之间的桥梁。这种类型的设计模式属于结构型模式，它结合了两个独立接口的功能。

这种模式涉及到一个单一的类，该类负责加入独立的或不兼容的接口功能。举个真实的例子，读卡器是作为内存卡和笔记本之间的适配器。您将内存卡插入读卡器，再将读卡器插入笔记本，这样就可以通过笔记本来读取内存卡。

我们通过下面的实例来演示适配器模式的使用。其中，音频播放器设备只能播放 mp3 文件，通过使用一个更高级的音频播放器来播放 vlc 和 mp4 文件。
## 门面设计模式
外观模式（Facade Pattern）隐藏系统的复杂性，并向客户端提供了一个客户端可以访问系统的接口。这种类型的设计模式属于结构型模式，它向现有的系统添加一个接口，来隐藏系统的复杂性。

这种模式涉及到一个单一的类，该类提供了客户端请求的简化方法和对现有系统类方法的委托调用。