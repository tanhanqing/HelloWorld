# JVM 相关

    JVM初始运行的时候都会分配好 Method Area（方法区） 和Heap（堆） ，而JVM 每遇到一个线程，就为其分配一个 Program Counter Register（程序计数器） ,   VM Stack（虚拟机栈）和Native Method Stack  （本地方法栈）， 当线程终止时，三者（虚拟机栈，本地方法栈和程序计数器）所占用的内存空间也会被释放掉。这也是为什么我把内存区域分为线程共享和非线程共享的原因，非线程共享的那三个区域的生命周期与所属线程相同，而线程共享的区域与JAVA程序运行的生命周期相同，所以这也是系统垃圾回收的场所只发生在线程共享的区域（实际上对大部分虚拟机来说知发生在Heap上）的原因。
    
在方法区中，存储了每个类的信息（包括类的名称、方法信息、字段信息）、静态变量、常量以及编译器编译后的代码等。

程序计数器是一个比较小的内存区域，用于指示当前线程所执行的字节码执行到了第几行

虚拟机栈描述的是Java方法执行的内存模型，用于存储局部变量，操作数栈，动态链接，方法出口等信息，是线程隔离的

![test](https://tanhanqing.github.io/img/jvmThreadShare.png)

![test](https://tanhanqing.github.io/img/jvm.png)


# statement

    1.Statement、PreparedStatement和CallableStatement都是接口(interface)。  
    2.Statement继承自Wrapper、PreparedStatement继承自Statement、CallableStatement继承自PreparedStatement。  
    3.  
    Statement接口提供了执行语句和获取结果的基本方法；  
    PreparedStatement接口添加了处理 IN 参数的方法；  
    CallableStatement接口添加了处理 OUT 参数的方法。  
    4.  
    a.Statement:  
    普通的不带参的查询SQL；支持批量更新,批量删除;  
    b.PreparedStatement:  
    可变参数的SQL,编译一次,执行多次,效率高;  
    安全性好，有效防止Sql注入等问题;  
    支持批量更新,批量删除;  
    c.CallableStatement:  
    继承自PreparedStatement,支持带参数的SQL操作;  
    支持调用存储过程,提供了对输出和输入/输出参数(INOUT)的支持;  

    Statement每次执行sql语句，数据库都要执行sql语句的编译 ，  
    最好用于仅执行一次查询并返回结果的情形，效率高于PreparedStatement。  

    PreparedStatement是预编译的，使用PreparedStatement有几个好处  
    1. 在执行可变参数的一条SQL时，PreparedStatement比Statement的效率高，因为DBMS预编译一条SQL当然会比多次编译一条SQL的效率要高。  
    2. 安全性好，有效防止Sql注入等问题。  
    3.  对于多次重复执行的语句，使用PreparedStament效率会更高一点，并且在这种情况下也比较适合使用batch；  
    4.  代码的可读性和可维护性。

# SPRING的事务传播特性

事务属性的种类：   传播行为、隔离级别、只读和事务超时

    如果你在你的Service层的这个方法中，除了调用了Dao层的方法之外，还调用了本类的其他的Service方法，那么在调用其他的Service方法的时候，这个事务是怎么规定的呢，我必须保证我在我方法里掉用的这个方法与我本身的方法处在同一个事务中，否则如果保证事物的一致性。事务的传播特性就是解决这个问题的，“事务是会传播的”在Spring中有针对传播特性的多种配置我们大多数情况下只用其中的一种:PROPGATION_REQUIRED：这个配置项的意思是说当我调用service层的方法的时候开启一个事务(具体调用那一层的方法开始创建事务，要看你的aop的配置),那么在调用这个service层里面的其他的方法的时候,如果当前方法产生了事务就用当前方法产生的事务，否则就创建一个新的事务。这个工作使由Spring来帮助我们完成的。 
    以前没有Spring帮助我们完成事务的时候我们必须自己手动的控制事务，例如当我们项目中仅仅使用hibernate，而没有集成进spring的时候，我们在一个service层中调用其他的业务逻辑方法，为了保证事物必须也要把当前的hibernate session传递到下一个方法中，或者采用ThreadLocal的方法，将session传递给下一个方法，其实都是一个目的。现在这个工作由spring来帮助我们完成，就可以让我们更加的专注于我们的业务逻辑。
    
    PROPAGATION_REQUIRED--支持当前事务，如果当前没有事务，就新建一个事务。这是最常见的选择。 
    PROPAGATION_SUPPORTS--支持当前事务，如果当前没有事务，就以非事务方式执行。 
    PROPAGATION_MANDATORY--支持当前事务，如果当前没有事务，就抛出异常。 
    PROPAGATION_REQUIRES_NEW--新建事务，如果当前存在事务，把当前事务挂起。 
    PROPAGATION_NOT_SUPPORTED--以非事务方式执行操作，如果当前存在事务，就把当前事务挂起。 
    PROPAGATION_NEVER--以非事务方式执行，如果当前存在事务，则抛出异常。 
