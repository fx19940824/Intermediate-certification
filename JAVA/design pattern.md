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