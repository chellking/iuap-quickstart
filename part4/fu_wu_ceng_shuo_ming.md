# 业务层说明

业务逻辑层，采用spring注解的方式声明成bean，主要负责业务逻辑的处理工作，如果有复杂的数据库操作，可以在此层引入多个业务的Dao类，并在此类中控制事务。  
示例采用的是平台建议的Spring的方式利用注解控制事务。示例如下：  


![](/img/image024.jpg)
 