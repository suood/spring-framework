###### AnnotationConfigApplicationContext
1. 继承自 extends GenericApplicationContext 类  
2. 实现 implements AnnotationConfigRegistry  接口
3. 构造方法 AnnotationConfigApplicationContext(Class<?>... componentClasses) 
   传入得参数类是使用 @Configuration注解的相关类 ，同事使用相关 @ComponentScan，@Bean类想关注解
    3.1 构造方法首先调用父类构造方法->GenericApplicationContext.
    3.2 调用本类无参数构造方法->创建相关的bean定义读取器。AnnotatedBeanDefinitionReader的registry属性就是对应的ApplicationContext。 
        AnnotationConfigUtils#registerAnnotationConfigProcessors  -> 注册定义了spring内部的6个 bean。
        