## 包

如何将类和接口捆绑成包，如何使用包中的类，如何编排文件系统，以便编译器可以找到源文件。

### 包的创建和使用

为了使类型更易于查找和使用，为了避免命名冲突以及控制访问，程序员将多组相关的类型捆绑成包。

> 定义：**包**是相关的类型的分组，它提供访问保护和命名空间管理。**类型**指的是类，接口，枚举和注解。枚举和注解是特殊的类和接口，因此**类型**通常指的是**类和接口**。

Java平台的部分类型是由按功能捆绑的类所组成的各种包的成员：`java.lang`中的基础类，`java.io`中的读写类（输入输出类）。

#### 包的创建
