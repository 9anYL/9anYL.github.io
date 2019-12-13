# 嵌套类

Java允许你在一个类中定义另一个类。这样的类称为**嵌套类（nested class）**，如下：

``` java
class OuterClass {
  ...
  class NestedClass {
    ...
  }
}
```

> 嵌套类有两种：静态（static）与非静态（non-static）。声明为`static`的嵌套类称为**静态嵌套类（static nested classes）**。非静态嵌套类称为**内部类（inner classes）**。

``` java
class OuterClass {
  ...
  static class StaticNestedClass {
    ...
  }
  class InnerClass {
    ...
  }
}
```

嵌套类是其封闭类的成员。非静态嵌套类（内部类）可以访问其封闭类的其他成员，即使它们被声明为`private`也是如此。静态嵌套类无权访问其封闭类的其他成员。作为`OuterClass`的成员，可以将嵌套类声明为`private`，`public`，`protect`或*package-private*。（回想一下，外部类只能声明为`public`或*package-private*。）

## 为什么要用嵌套类？

- 将只在一个地方使用的类进行逻辑分组：如果一个类仅对另一个类有用，那么将其嵌入该类并将两者放在一起是合乎逻辑的。嵌套这种“帮手类”可使包的结构更加精简。
- 增加封装性：
- 提高代码的可读性和维护性：将小型类嵌套在顶级类中使代码更紧凑。

## 静态嵌套类

与类方法和类变量一样，静态嵌套类与其外部类相关联。与静态类方法一样，静态嵌套类不能直接引用其封闭类中定义的实例变量或实例方法：它只能通过对象引用来使用它们。

> 静态嵌套类与它的外部类（和其他类）的实例成员进行交互，就像其他任何顶级类一样。实际上，静态嵌套类在行为上是顶级类，为了包装方便，该顶级类已嵌套在另一个顶级类中。

静态嵌套类使用封闭的类名称访问：

``` java
OuterClass.StaticNestedClass
```

例如，要为静态嵌套类创建一个对象，请使用以下语法：

``` java
OuterClass.StaticNestedClass nestedObject = new OuterClass.StaticNestedClass();
```

## 内部类

与实例方法和变量一样，内部类与其所在类的实例相关联，并且可以直接访问该对象的方法和字段。另外，由于内部类与实例相关联，因此它本身不能定义任何静态成员。

作为内部类实例的对象存在于外部类实例中。考虑以下类别：

``` java
class OuterClass {
  ...
  class InnerClass {
    ...
  }
}
```

InnerClass的实例只能存在于OuterClass的实例中，并且可以直接访问其封闭实例的方法和字段。

要实例化内部类，必须首先实例化外部类。然后，使用以下语法在外部对象内创建内部对象：

``` java
OuterClass.InnerClass innerObject = outerObject.new InnerClass();
```

有两种特殊的内部类：本地类和匿名类。
