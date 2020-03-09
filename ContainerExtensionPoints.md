# 容器的扩展
开发人员无需继承`ApplicationContext`的实现类,而是通过实现一些特殊的**集成接口**来实现对容器的扩展。

## 使用`BeanPostProcessor`自定义Bean
`org.springframework.beans.factory.config.BeanPostProcessor`
> The `BeanPostProcessor` interface defines callback methods that you can implement to provide your own (or override the container’s default) instantiation logic, dependency resolution logic, and so forth. 
> If you want to implement some custom logic after the Spring container finishes instantiating, configuring, and initializing a bean, you can plug in one or more custom `BeanPostProcessor` implementations.

## 使用`BeanFactoryPostProcessor`自定义容器的配置
`org.springframework.beans.factory.config.BeanFactoryPostProcessor`
> `BeanFactoryPostProcessor` operates on the bean configuration metadata. 
> That is, the Spring IoC container lets a `BeanFactoryPostProcessor` read the configuration metadata and potentially change it before the container instantiates any beans other than `BeanFactoryPostProcessor` instances.

## 使用`FactoryBean`自定义容器的实例化逻辑
`org.springframework.beans.factory.FactoryBean`
> You can implement the `org.springframework.beans.factory.FactoryBean` interface for objects that are themselves factories.
> The `FactoryBean` interface is a point of pluggability into the Spring IoC container’s instantiation logic.
