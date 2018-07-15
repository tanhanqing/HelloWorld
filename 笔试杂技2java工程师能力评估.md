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


# 有关servlet和cgi的描述

    serlet 各方面都优于cgi 
    线程 > 进程k
    可移植性好 
    轻量级

# servlet service描述

service判断请求类型，决定是调用doGet还是doPost方法

![test](https://tanhanqing.github.io/img/httpservele.png)

# Servlet的生命周期

    Servlet的生命周期
    1.加载：容器通过类加载器使用Servlet类对应的文件来加载Servlet
    2.创建：通过调用Servlet的构造函数来创建一个Servlet实例
    3.初始化：通过调用Servlet的init()方法来完成初始化工作，这个方法是在Servlet已经被创建，但在向客户端提供服务之前调用。
    4.处理客户请求：Servlet创建后就可以处理请求，当有新的客户端请求时，Web容器都会创建一个新的线程来处理该请求。接着调用Servlet的
    Service()方法来响应客户端请求（Service方法会根据请求的method属性来调用doGet（）和doPost（））
    5.卸载：容器在卸载Servlet之前需要调用destroy()方法，让Servlet释放其占用的资源。
    
    servlet在多线程下其本身并不是线程安全的。
    如果在类中定义成员变量，而在service中根据不同的线程对该成员变量进行更改，那么在并发的时候就会引起错误。最好是在方法中，定义局部变量，而不是类变量或者对象的成员变量。由于方法中的局部变量是在栈中，彼此各自都拥有独立的运行空间而不会互相干扰，因此才做到线程安全。
    
    
# Struts1和Struts2的区别和对比:

    Action 类:  
    • Struts1要求Action类继承一个抽象基类。Struts1的一个普遍问题是使用抽象类编程而不是接口，而struts2的Action是接口。  
    • Struts 2 Action类可以实现一个Action接口，也可实现其他接口，使可选和定制的服务成为可能。Struts2提供一个ActionSupport基类去 实现 常用的接口。Action接口不是必须的，任何有execute标识的POJO对象都可以用作Struts2的Action对象。 

    线程模式:  
    • Struts1 Action是单例模式并且必须是线程安全的，因为仅有Action的一个实例来处理所有的请求。单例策略限制了Struts1 Action能作的事，并且要在开发时特别小心。Action资源必须是线程安全的或同步的。 
    • Struts2 Action对象为每一个请求产生一个实例，因此没有线程安全问题。（实际上，servlet容器给每个请求产生许多可丢弃的对象，并且不会导致性能和垃圾回收问题） 

    Servlet 依赖:  
    • Struts1 Action 依赖于Servlet API ,因为当一个Action被调用时HttpServletRequest 和 HttpServletResponse 被传递给execute方法。 
    • Struts 2 Action不依赖于容器，允许Action脱离容器单独被测试。如果需要，Struts2 Action仍然可以访问初始的request和response。但是，其他的元素减少或者消除了直接访问HttpServetRequest 和 HttpServletResponse的必要性。 

    可测性:  
    • 测试Struts1 Action的一个主要问题是execute方法暴露了servlet API（这使得测试要依赖于容器）。一个第三方扩展－－Struts TestCase－－提供了一套Struts1的模拟对象（来进行测试）。 
    • Struts 2 Action可以通过初始化、设置属性、调用方法来测试，“依赖注入”支持也使测试更容易。  

    捕获输入:  
    • Struts1 使用ActionForm对象捕获输入。所有的ActionForm必须继承一个基类。因为其他JavaBean不能用作ActionForm，开发者经常创建多余的类捕获输入。动态Bean（DynaBeans）可以作为创建传统ActionForm的选择，但是，开发者可能是在重新描述(创建)已经存 在的JavaBean（仍然会导致有冗余的javabean）。 
    • Struts 2直接使用Action属性作为输入属性，消除了对第二个输入对象的需求。输入属性可能是有自己(子)属性的rich对象类型。Action属性能够通过 web页面上的taglibs访问。Struts2也支持ActionForm模式。rich对象类型，包括业务对象，能够用作输入/输出对象。这种 ModelDriven 特性简化了taglib对POJO输入对象的引用。 

    表达式语言：  
    • Struts1 整合了JSTL，因此使用JSTL EL。这种EL有基本对象图遍历，但是对集合和索引属性的支持很弱。  
    • Struts2可以使用JSTL，但是也支持一个更强大和灵活的表达式语言－－"Object Graph Notation Language" (OGNL). 

# swt swing

           AWT和Swing之间的区别：
           1)AWT 是基于本地方法的C/C++程序，其运行速度比较快；Swing是基于AWT的Java程序，其运行速度比较慢。
           2)AWT的控件在不同的平台可能表现不同，而Swing在所有平台表现一致。

           在实际应用中，应该使用AWT还是Swing取决于应用程序所部署的平台类型。例如：
           1)对于一个嵌入式应用，目标平台的硬件资源往往非常有限，而应用程序的运行速度又是项目中至关重要的因素。在这种矛盾的情况下，简单而高效的AWT当然成了嵌入式Java的第一选择。
           2)在普通的基于PC或者是工作站的标准Java应用中，硬件资源对应用程序所造成的限制往往不是项目中的关键因素。所以在标准版的Java中则提倡使用Swing， 也就是通过牺牲速度来实现应用程序的功能。
           
# 转发重定向

    redirect：请求重定向：客户端行为，本质上为2次请求，地址栏改变，前一次请求对象消失。举例：你去银行办事（forward.jsp），结果告诉你少带了东西，你得先去公安局办(index.html)临时身份证,这时你就会走出银行，自己前往公安局，地址栏变为index.html.
    forward：请求转发:服务器行为，地址栏不变。举例：你把钱包落在出租车上，你去警察局（forward.jsp）报案，警察局说钱包落在某某公司的出租车上（index.html)，这时你不用亲自去找某某公司的出租车,警察局让出租车自己给你送来，你只要在警察局等就行。所以地址栏不变，依然为forward.jsp
    
    
    
# 加载驱动方法

    加载驱动方法
    1.Class.forName("com.microsoft.sqlserver.jdbc.SQLServerDriver");
    2. DriverManager.registerDriver(new com.mysql.jdbc.Driver());
    3.System.setProperty("jdbc.drivers", "com.mysql.jdbc.Driver");
    
    DriverManager.getConnection方法返回一个Connection对象，这是加载驱动之后才能进行的
    
# 多线程
    Java中的多线程是一种抢占式的机制，而不是分时机制。抢占式的机制是有多个线程处于可运行状态，但是只有一个线程在运行。 
    共同点 ： 
    1. 他们都是在多线程的环境下，都可以在程序的调用处阻塞指定的毫秒数，并返回。 
    
# 数据加载
    JVM中一个字节以下的整型数据会在JVM启动的时候加载进内存，除非用new Integer()显式的创建对象，否则都是同一个对象
    2. wait()和sleep()都可以通过interrupt()方法 打断线程的暂停状态 ，从而使线程立刻抛出InterruptedException。 

    不同点 ：  
    1.每个对象都有一个锁来控制同步访问。Synchronized关键字可以和对象的锁交互，来实现线程的同步。 
    sleep方法没有释放锁，而wait方法释放了锁，使得其他线程可以使用同步控制块或者方法。 
    2.wait，notify和notifyAll只能在同步控制方法或者同步控制块里面使用，而sleep可以在任何地方使用 
    3.sleep必须捕获异常，而wait，notify和notifyAll不需要捕获异常 
    4.sleep是线程类（Thread）的方法，导致此线程暂停执行指定时间，给执行机会给其他线程，但是监控状态依然保持，到时后会自动恢复。调用sleep不会释放对象锁。
    5.wait是Object类的方法，对此对象调用wait方法导致本线程放弃对象锁，进入等待此对象的等待锁定池，只有针对此对象发出notify方法（或notifyAll）后本线程才进入对象锁定池准备获得对象锁进入运行状态。
    
# exception、

![test](https://tanhanqing.github.io/img/Exception.png)

    
    运行时异常： 都是RuntimeException类及其子类异常，如NullPointerException(空指针异常)、IndexOutOfBoundsException(下标越界异常)等，这些异常是不检查异常，程序中可以选择捕获处理，也可以不处理。这些异常一般是由程序逻辑错误引起的，程序应该从逻辑角度尽可能避免这类异常的发生。
           运行时异常的特点是Java编译器不会检查它，也就是说，当程序中可能出现这类异常，即使没有用try-catch语句捕获它，也没有用throws子句声明抛出它，也会编译通过。 
    非运行时异常 （编译异常）： 是RuntimeException以外的异常，类型上都属于Exception类及其子类。从程序语法角度讲是必须进行处理的异常，如果不处理，程序就不能编译通过。如IOException、SQLException等以及用户自定义的Exception异常，一般情况下不自定义检查异常。

# stuts

![test](https://tanhanqing.github.io/img/stuts.png)

# 动态 静态 include

    动态 INCLUDE 用 jsp:include 动作实现 <jsp:include page="included.jsp" flush="true" /> 它总是会检查所含文件中的变化 , 适合用于包含动态页面 , 并且可以带参数。各个文件分别先编译，然后组合成一个文件。
    静态 INCLUDE 用 include 伪码实现 , 定不会检查所含文件的变化 , 适用于包含静态页面 <%@ include file="included.htm" %> 。先将文件的代码被原封不动地加入到了主页面从而合成一个文件，然后再进行翻译，此时不允许有相同的变量。 

    以下是对 include 两种用法的区别 ， 主要有两个方面的不同 ;
    一 : 执行时间上 :
        <%@ include file="relativeURI"%> 是在翻译阶段执行
        <jsp:include page="relativeURI" flush="true" /> 在请求处理阶段执行 .
    二 : 引入内容的不同 :
        <%@ include file="relativeURI"%>
        引入静态文本 (html,jsp), 在 JSP 页面被转化成 servlet 之前和它融和到一起 .
        <jsp:include page="relativeURI" flush="true" /> 引入执行页面或 servlet 所生成的应答文本 
        
# JVM内存配置

![test](https://tanhanqing.github.io/img/JVMsetting..png)

    -Xmx10240m：代表最大堆
    -Xms10240m：代表最小堆
    -Xmn5120m：代表新生代
    -XXSurvivorRatio=3：代表Eden:Survivor = 3    根据Generation-Collection算法(目前大部分JVM采用的算法)，一般根据对象的生存周期将堆内存分为若干不同的区域，一般情况将新生代分为Eden ，两块Survivor；    计算Survivor大小， Eden:Survivor = 3，总大小为5120,3x+x+x=5120  x=1024
    新生代大部分要回收，采用Copying算法，快！
    老年代 大部分不需要回收，采用Mark-Compact算法
