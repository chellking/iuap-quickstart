# 实体层介绍

实体层是与数据库表进行映射的vo类，采用iuap-jdbc方式进行持久化的vo类的示例如下，如果是JPA方式采用简单POJO类配合相应的注解即可。  
注意：iuap-jdbc方式的vo类，注解为iuap-jdbc组件指定的注解。  


![](/img/image021.jpg)
  

其中iuap-jdbc要求用户实现的预留元数据方式访问的方法如下，请注意：  

![](img/image022.jpg)
 

具体的注解的使用请参考技术组件中的JDBC持久化组件对应的手册。  