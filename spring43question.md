1.Ϊʲôʹ��Spring ?
1). �������򻯿���
         ͨ��Spring�ṩ��IoC���������Խ�����֮���������ϵ����Spring���п��ƣ�����Ӳ��������ɵĹ��ȳ�����ϡ�
    2). AOP��̵�֧��
         ͨ��Spring�ṩ��AOP���ܣ����������������ı�̣������ܼ�⡢���������־��¼�ȡ�
    3). ����ʽ�����֧��
    4). ���㼯�ɸ���������
    5). ����Java EE API��ʹ���Ѷ�
         ���JDBC��JavaMail��Զ�̵��õ��ṩ�˼���װ��
2. ʲô��IoC��Ϊʲʹ��IoC ?
 IoCȫ��Iversion of Controller�����Ʒ�ת��
    �������˵�㲻�ô������󣬶�ֻ��Ҫ��������α��������㲻�ڴ�����ֱ����װ�������ͷ��񣬵���Ҫ�������ļ���������Щ�����Ҫ��Щ����֮��һ��������IOC�����������������װ������
    ����ָ�����������Ƴ�����ϡ��������ĳ���
3.ʲô��AOP��Ϊʲôʹ��AOP ?
AOPȫ�ƣ�Aspect-Oriented Programming�����������̡�
     AOP�����������̣����ǰѿ����õĹ�����ȡ������Ȼ����Щͨ�ù����ں��ʵ�ʱ��֯�뵽Ӧ�ó����У������������Ȩ�޿��ơ���־��¼������ͳ�Ƶȡ�
    AOP��û�а������ǽ���κ��µ����⣬��ֻ���ṩ��һ�ָ��õİ취���ܹ��ø��ٵĹ�������������е�һЩ���⣬ʹ��ϵͳ���ӽ�׳����ά���Ը��á�
4.ʲô��Spring���������
������Ƕ�һϵ�е����ݿ�������������������ݣ�����ͳһ���ύ��ع��������������ɹ�����ôһ��ɹ�������м���һ�������쳣����ô�ع�֮ǰ�����в������������Է�ֹ���������ݣ���ֹ���ݿ����ݳ������⡣
    ������Ϊ�˱����������һ�㶼������������
    Spring������ʽ����ͨ����ָ�������ļ��ж���������������������а����˺ܶ��������ԣ�����ͨ��Spring Proxy�����������Լ����ö����д���룬ֻҪ��Spring�����ļ����������ɣ�ͨ���������ݿ�Ĳ������棻
    ���ʽ�������ָͨ��Ӳ����ķ�ʽ�����������ִ���ʽ��Ҫд���룬�����е��߼������Լ����ƣ����������ݿ�Ķ�����Ҳ�����������Ĳ�����
    Spring��Ҳ���Լ������������ƣ�һ����ʹ��TransactionMananger���й�������ͨ��Spring��ע������ɴ˹��ܡ�
5.Spring���֧����������bean��������?
singleton : Ĭ��ֵ��bean��ÿ��Spring ioc ������ֻ��һ��ʵ����
    prototype��һ��bean�Ķ�������ж��ʵ����
    request��ÿ��http���󶼻ᴴ��һ��bean������������ڻ���web��Spring ApplicationContext��������Ч�� 
    session����һ��HTTP Session�У�һ��bean�����Ӧһ��ʵ��������������ڻ���web��Spring ApplicationContext��������Ч��
    global-session����һ��ȫ�ֵ�HTTP Session�У�һ��bean�����Ӧһ��ʵ��������������ڻ���web��Spring ApplicationContext��������Ч��
6.ʲô��Spring��MVC��ܣ�
 Spring �䱸����Web Ӧ�õ�ȫ����MVC��ܡ�Spring���Ժܱ�ݵغ�����MVC��ܼ��ɣ���Struts��Spring ��MVC����ÿ��Ʒ�ת��ҵ�����Ϳ����߼������ظ��롣��Ҳ�����������ķ�ʽ�����������ҵ�����󶨡�
    spring mvc��һ������mvc��web��ܡ�spring mvc��spring��ܵ�һ��ģ�飬springmvc��spring����ͨ���м����ϲ�������ϡ�
7.�������ע��?
<context:annotation-config/>
    ���ʹ��<context:component-scan base-package="com.tgb.web.controller.annotation"> </context:component-scan>  ���������ݿ���ʡ�� 
 8.Spring MVC����������?
    ��һ������������ǰ�˿�����(DispatcherServlet)
    �ڶ�����ǰ�˿���������HandlerMapping����Handler���Ը���xml���á�ע����в���
    ��������������ӳ����HandlerMapping��ǰ�˿���������Handler
    ���Ĳ���ǰ�˿��������ô�����������ȥִ��Handler
    ���岽��������������ȥִ��Handler
    ��������Handlerִ����ɸ�����������ModelAndView
    ���߲�����������������ǰ�˿���������ModelAndView��ModelAndView��springmvc��ܵ�һ���ײ���󣬰��� Model��view
    �ڰ˲���ǰ�˿�����������ͼ������ȥ������ͼ�����������߼���ͼ����������������ͼ(jsp)
    �ھŲ�����ͼ��������ǰ�˿���������View
    ��ʮ����ǰ�˿�����������ͼ��Ⱦ����ͼ��Ⱦ��ģ������(��ModelAndView������)��䵽request��
    ��ʮһ����ǰ�˿��������û���Ӧ���
9.web.xml������

10.ע��Ĵ�����ӳ������������?
spring3.1֮��ʹ��org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerMappingע��ӳ������
��spring3.1֮��ʹ��org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapterע����������
ʹ�� mvc:annotation-driven�����ϱ�ע��ӳ������ע������������
11.spring �� mybatis���Ϲ���?
��һ��������dao��
   mybatis��spring���ϣ�ͨ��spring����mapper�ӿڡ�
   ʹ��mapper��ɨ�����Զ�ɨ��mapper�ӿ���spring�н���ע�ᡣ
�ڶ���������service��
   ͨ��spring���� service�ӿڡ�
   ʹ�����÷�ʽ��service�ӿ�������spring�����ļ��С�
   ʵ��������ơ�
������������springmvc
   ����springmvc��spring��ģ�飬����Ҫ����

��Ҫ�����У�
      1). mybatis�����ļ�sqlMapConfig.xml���ñ����Զ�ɨ��(ʵ����)
      2). mapperɨ����(�ӿڣ����ݿ���ʽӿ�)
      3). ���ݿ����ӳ�����
      4). ����ʽ��������
      5). ����ע��ɨ�裺<context:component-scan base-package="cn.itcast.ssm.controller"></context:component-scan>
      6). ����ע��ӳ�������������� <mvc:annotation-driven></mvc:annotation-driven>
      7). ��ͼ��������<bean  class="org.springframework.web.servlet.view.InternalResourceViewResolver">
      8). ���ÿ����ࣺ DispatcherServletǰ�˿�����
      9). ����spring�����ļ������ࣺClassLoadListener
12.��ͼ����������ǰ׺�ͺ�׺?

13.sqlMapConfig.xml��mybatis�Լ��������ļ�?

14.��������Դ?

15.�������(applicationContext-transaction.xml)?
��applicationContext-transaction.xml��ʹ��spring����ʽ������Ʒ�����

16.����spring����?

17.��̬��Դ���ʲ�������?
 <resources mapping="/resources/**" location="/resources/" />
      <resources mapping="/images/**" location="/images/" />
      <resources mapping="/js/**" location="/js/" />
18.@RequestMapping������?
1). urlӳ��
2). խ������ӳ��
3). ����http���󷽷�
19.controller�����ķ���ֵ?
1 ����ModelAndView 
    ��Ҫ��������ʱ������ModelAndView����model��view�ֱ�������á� 
2 ����string
     ���controller��������string��
     1). ��ʾ�����߼���ͼ����������ͼ(jsp·��)=ǰ׺+�߼���ͼ��+��׺
     2). redirect�ض��򣺷����ַ�����ʽΪ��"redirect:queryItem.action"
     3). forwardҳ��ת���������ַ�����ʽΪ����forward:queryItem.action��
3 ����void
      ��controller�����β��Ͽ��Զ���request��response��ʹ��request�� responseָ����Ӧ�����
     1). ʹ��requestת��ҳ�棬���£�request.getRequestDispatcher("ҳ��·��").forward(request, response);
     2). Ҳ����ͨ��responseҳ���ض���response.sendRedirect("url")
     3). Ҳ����ͨ��responseָ����Ӧ�����������Ӧjson�������£�
           response.setCharacterEncoding("utf-8");
           response.setContentType("application/json;charset=utf-8");
           response.getWriter().write("json��");
20.������
1 Ĭ��֧�ֵ�����
ֱ����controller�����β��϶����±����͵Ķ��󣬾Ϳ���ʹ����Щ�����ڲ����󶨹����У���������±�����ֱ�ӽ��а󶨡�
1). HttpServletRequest��ͨ��request�����ȡ������Ϣ
2). HttpServletResponse��ͨ��response������Ӧ��Ϣ
3). HttpSession��ͨ��session����õ�session�д�ŵĶ���
4). Model/ModelMap��model��һ���ӿڣ�modelMap��һ���ӿ�ʵ�� �����ã���model������䵽request��
2 ������
ͨ��@RequestParam�Լ����͵Ĳ������а󶨡�
�����ʹ��@RequestParam��Ҫ��request����������ƺ�controller�������β�����һ�£����ɰ󶨳ɹ���
���ʹ��@RequestParam����������request����������ƺ�controller�������β�����һ�¡�
ͨ��required����ָ�������Ƿ����Ҫ���룬�������Ϊtrue��û�д���������ᱨ��
3 pojo��
ҳ����input��name��controller��pojo�β��е���������һ�£���ҳ�������ݰ󶨵�pojo��(usename,age������Ҫuser.username,user.age)
4 �Զ��������ʵ���������Ͱ�
����controller�β���pojo����������������������ͣ���Ҫ�Զ�������󶨡��������������ݴ�ת�� �������ͣ�Ҫת�����������ͺ�pojo���������Ե����ͱ���һ�¡�
21.Spring MVC �� Struts2 �Ա�?
1). Struts2���༶������أ� һ�����Ӧһ��request�����ģ�SpringMVC�Ƿ�����������أ�һ��������Ӧһ��request�����ģ�������ͬʱ�ָ�һ��url��Ӧ������˵�Ӽܹ�������SpringMVC ������ʵ��restful url
2). ���ϱ�ԭ��SpringMVC�ķ���֮������϶����ģ�����request response���ݣ���������ͨ��������ȡ��������ͨ��ModelMap���ظ���ܣ�����֮�䲻�����������Struts2��ľͱȽ��ң���Ȼ����֮��Ҳ�Ƕ����ģ���������Action�����ǹ���ģ��ⲻ��Ӱ��������У�ȴ�����Ǳ��� ������ʱ�����鷳��ÿ����������ʹ���һ��Action��һ��Action�����Ӧһ��request�����ġ�
3). ����Struts2��Ҫ���ÿ��request���з�װ����request��session��servlet�������ڵı�����װ��һ��һ��Map������ÿ��Actionʹ�ã�����֤�̰߳�ȫ��������ԭ���ϣ��ǱȽϺķ��ڴ�ġ�
4). SpringMVC������Ajax��ʹ�÷ǳ����㣬ֻ��һ��ע��@ResponseBody�Ϳ���ʵ�֣�Ȼ��ֱ�ӷ�����Ӧ�ı����ɣ���Struts2������������Ajax����Action�д���ʱһ����밲װ��������Լ�д���뼯�ɽ�ȥ��ʹ������Ҳ��Բ����㡣
5). springmvc���򷽷������ģ����ӽ�service�ӿڵĿ�����ʽ����struts2�����࿪����
6). springmvc���Ե���������struts2ֻ���Ƕ���������
22. ���봦��?
1). post����
     ��web.xml���post����filter��CharacterEncodingFilter
2). ����get�������Ĳ�������������������������
     a. �޸�tomcat�����ļ���ӱ����빤�̱���һ�£����£�
<Connector URIEncoding="utf-8" connectionTimeout="20000" port="8080" protocol="HTTP/1.1" redirectPort="8443"/>
     b. �Բ����������±��룺
String userName = new String(request.getParamter("userName").getBytes("ISO8859-1"),"utf-8")
ISO8859-1��tomcatĬ�ϱ��룬��Ҫ��tomcat���������ݰ�utf-8����
23. �������Ͱ�
1). ����󶨣�
     controller��������ʹ�ã�(Integer[] itemId)
     ҳ��ͳһʹ��:itemId ��Ϊname
2). list�󶨣�
     pojo������Ϊ��itemsList
     ҳ�棺itemsList[index].������
3). map �󶨣�
     pojo������Ϊ��Map<String, Object> itemInfo = new HashMap<String, Object>(); 
     ҳ�棺 <td>������<inputtype="text"name="itemInfo['name']"/>
24.spring У�� ?
1). ��Ŀ�У�ͨ��ʹ�ý϶���ǰ�˵�У�飬����ҳ����jsУ�顣���ڰ�ȫҪ��ϸߵ㽨���ڷ���˽���У�顣
2). springmvcʹ��hibernate��У����validation(��hibernateû���κι�ϵ)��
У��˼·��ҳ���ύ����Ĳ���������controller�����У�ʹ��validation����У�顣���У�������������Ϣչʾ��ҳ�档
25.���ݻ���?
1). @ModelAttribute�����Խ������ķ���ֵ����ҳ�棺�ڷ����ϼ�ע��@ModelAttribute
2). ʹ����򵥷���ʹ��model�����Բ���@ModelAttribute��model.addAttribute("id", id);
3). springmvcĬ�϶�pojo���ݽ��л��ԡ�pojo���ݴ���controller������springmvc�Զ���pojo���ݷŵ�request��key����pojo���ͣ�����ĸСд��
4). public String testParam(PrintWriter out, @RequestParam("username") String username) { //outֱ�����
26.�쳣����?
springmvc�ṩȫ���쳣��������һ��ϵͳֻ��һ���쳣������������ͳһ�쳣����
      ϵͳ�����쳣���ڳ������ֶ��׳���dao�׸�service��service��controller��controller�׸�ǰ�˿�������ǰ�˿���������ȫ���쳣��������
27.�ϴ�ͼƬ?
1). ��ҳ��form���ύenctype="multipart/form-data"������ʱ����Ҫspringmvc��multipart���͵����ݽ��н�����
2). ��springmvc.xml������multipart���ͽ�������

3). ������ʹ�ã�MultipartFile attach (�����ļ��ϴ�) ����  MultipartFile[] attachs (����ļ��ϴ�)
28.Json����
1). ����jsonת����jar����springmvc��ʹ��jackson�İ�����jsonת����@requestBody��@responseBodyʹ���±ߵİ�����jsonת��
2). ����jsonת��������ע��������RequestMappingHandlerAdapter�м���messageConverters�����ʹ��<mvc:annotation-driven /> ����Զ����롣
3). ajax
       
4). Controller (ResponseBody��RequestBody)

5). ע��ajax��contentType���������Ϊjson���ͣ��򴫵Ĳ���Ϊkey/value���͡��������ú󣬴�����json���͡�
29.������?
1). ������������ʵ��HandlerInterceptor�ӿڡ��ӿ����ṩ����������
a. preHandle ������ Handler����֮ǰִ�У����������֤�������Ȩ�����������֤�������֤ͨ����ʾ��ǰ�û�û�е�½����Ҫ�˷������ز�������ִ��
b. postHandle������Handler����֮�󣬷���modelAndView֮ǰִ�У�Ӧ�ó�����modelAndView�����������õ�ģ������(����˵�����)�����ﴫ����ͼ��Ҳ����������ͳһָ����ͼ
c. afterCompletion��ִ��Handler���ִ�д˷�����Ӧ�ó�����ͳһ�쳣����ͳһ��־����
2). ���������ã�
a. ���HandlerMapping����(���Ƽ�)��springmvc���������HandlerMapping�����������ã������ĳ��HandlerMapping���������أ������� HandlerMappingӳ��ɹ���handler����ʹ�ø� ��������  (һ�㲻�Ƽ�ʹ��)
b. ����ȫ�ֵ���������springmvc��������ȫ�ֵ���������springmvc��ܽ����õ�����ȫ�ֵ�������ע�뵽ÿ��HandlerMapping��

30.spring���Զ�װ��ķ�ʽ����Щ��
1��No�����������Զ�װ�䡣
2��byName��ͨ�����Ե����ֵķ�ʽ����JavaBean�����Ķ���Ϊ��ע�롣����˵��Computer�и�����printer��ָ����autowire����ΪbyName��Spring IoC�������������ļ��в���id/name����Ϊprinter��bean��Ȼ��ʹ��Seter����Ϊ��ע�롣
3��byType��ͨ�����Ե����Ͳ���JavaBean�����Ķ���Ϊ��ע�롣������Computer�и�����printer������ΪPrinter����ô��ָ����autowire����ΪbyType��Spring IoC���������Class����ΪPrinter��bean��ʹ��Seter����Ϊ��ע�롣
4��constructor��ͨbyTypeһ����Ҳ��ͨ�����Ͳ�������������byType����������������ʹ��Seter����ע�룬����ʹ�ù�����ע�롣
5��autodetect����byType��constructor֮���Զ���ѡ��ע�뷽ʽ��
6��default�����ϼ���ǩ<beans>��default-autowire����ȷ����
31.Spring��AOP��Ӧ�ó�����Aopԭ���ô���
AOP--Aspect Oriented Programming���������̣�������װ���й�ע�㣬�������������ĳ�����ʹ��:
Authentication Ȩ�ޡ�Caching ���桢Context passing ���ݴ��ݡ�Error handling ������Lazy loading�����ء�Debugging���ԡ�logging, tracing, profiling and monitoring ��¼�����Ż���У׼��Performance optimization�������Ż���Persistence �־û���Resource pooling����Դ�ء�Synchronization��ͬ����Transactions ����
ԭ��AOP�����������̣���ͨ����̬����ķ�ʽΪ�������ͳһ���ܣ����н��һЩ�������⡣
�ŵ㣺1.��������֮������ø���������Դ�󽵵� 
           2.Դ�����޹��ԣ�����չ���ܵ�ͬʱ����Դ������޸Ĳ��� 
32.Spring��IOC��������ԭ�����󴴽��Ĺ��̣�
IOC--Inversion of Control���Ʒ�ת����ĳ����ɫ��Ҫ����һ����ɫЭ����ʱ���ڴ�ͳ�ĳ�����ƹ����У�ͨ���ɵ������������������ߵ�ʵ�����󡣵���spring�д����������ߵĹ��������ɵ���������ɣ���˳�Ϊ���Ʒ�ת�������������ߵĹ�����spring����ɣ�Ȼ��ע������� ֱ��ʹ�á�
33.Spring�������������ע�⣿
@Component@Controller@ Service@ Repository
34.Spring���õ������ģʽ��
�򵥹�������������������ģʽ������������װ���������۲��ߡ����ԡ�ģ�巽��
35.Spring���ŵ㣿
1.���������֮�������� ��ʵ�����������֮��Ľ��� 
2.����ʹ�������ṩ���ڶ���������������Ϣ����� 
3.�����ṩ����ģʽ֧�� 
4.�����ṩ��AOP������������������ʵ����Ȩ�����أ������ڼ�صȹ��� 
5.�����ṩ���ڶ�ĸ����࣬�ܼӿ�Ӧ�õĿ��� 
6.spring����������Ӧ�ÿ���ṩ�˼���֧�֣���hibernate��JPA��Struts�� 
7.spring���ڵ�����ʽ��ƣ��������Ⱦ���� 
8.�����ڸ���Ӧ�÷����� 
9.spring��DI���ƽ�����ҵ������滻�ĸ����� 
10.Spring�ĸ߶ȿ����ԣ�����ǿ��Ӧ����ȫ������Spring�������߿�������ѡ��spring�Ĳ��ֻ�ȫ�� 
36.Spring Bean��������֮����ʲô����
Spring�����е�bean���Է�Ϊ5����Χ�����з�Χ�����ƶ�����˵���ģ�����Ϊ�˱������������������������һ�£�
singleton������bean��Χ��Ĭ�ϵģ����ַ�Χȷ�����ܽ��ܵ����ٸ�����ÿ��������ֻ��һ��bean��ʵ����������ģʽ��bean factory������ά����
prototype��ԭ�η�Χ�뵥����Χ�෴��Ϊÿһ��bean�����ṩһ��ʵ����
request��������bean��Χ�ڻ�ÿһ�����Կͻ��˵��������󴴽�һ��ʵ��������������Ժ�bean��ʧЧ�����������������ա�
Session��������Χ���ƣ�ȷ��ÿ��session����һ��bean��ʵ������session���ں�bean����֮ʧЧ��
global-session��global-session��PortletӦ����ء������Ӧ�ò�����Portlet�����й���ʱ���������ܶ�portlet���������Ҫ���������е�portlet����ȫ�ֵĴ洢�����Ļ�����ô��ȫ�ֱ�����Ҫ�洢��global-session�С�
ȫ����������Servlet�е�session������Ч����ͬ��
37.Spring���������м��ַ�ʽ��
�����ַ�ʽ��
1�����ʽ�����ڴ�����Ӳ���롣(���Ƽ�ʹ��)
2������ʽ�����������ļ������ã��Ƽ�ʹ�ã�
����ʽ�����ַ�Ϊ���֣�
a������XML������ʽ����
b������ע�������ʽ����
38.spring�еĺ���������Щ������ʲô���ã�
BeanFactory������һ���µ�ʵ��������ʵ�ֵ���ģʽ
BeanWrapper���ṩͳһ��get��set����
ApplicationContext:�ṩ��ܵ�ʵ�֣�����BeanFactory�����й���
39.Bean�ĵ��÷�ʽ����Щ��
�����ַ�ʽ���Եõ�Bean�����е��ã�
1��ʹ��BeanWrapper
HelloWorld hw=new HelloWorld(); 
BeanWrapper bw=new BeanWrapperImpl(hw); 
bw.setPropertyvalue(��msg��,��HelloWorld��);
system.out.println(bw.getPropertyCalue(��msg��));
2��ʹ��BeanFactory
InputStream is=new FileInputStream(��config.xml��);
XmlBeanFactory factory=new XmlBeanFactory(is);
HelloWorld hw=(HelloWorld) factory.getBean(��HelloWorld��);
system.out.println(hw.getMsg()); 
3��ʹ��ApplicationConttext
ApplicationContext actx=new FleSystemXmlApplicationContext(��config.xml��);
HelloWorld hw=(HelloWorld) actx.getBean(��HelloWorld��);
System.out.println(hw.getMsg());
40.ʲô��IOC��ʲô����DI��������ʲô����
����ע��DI��һ���������ģʽ�ͼܹ�ģ�ͣ� һЩʱ��Ҳ�������Ʒ�ת�������ڼ���������������ע����һ��IOC������ʵ�֣�����ע����ָһ������Ӧ������һ���������ṩһ����������������磺��һ�� ���ݿ������Ѳ�������ʽ����һ������Ľṹ����������������Ǹ������ڲ����д���һ�����ӡ����Ʒ�ת������ע��Ļ���˼����ǰ�������������ڲ�ת������ ���Լ�������
Ӧ�ÿ��Ʒ�ת�������ڱ�������ʱ����һ������ϵͳ�����ж�������ʵ�壬�����������Ķ�������ã����ݸ�����Ҳ����˵��������ע�뵽�����С����ԣ����Ʒ�ת�ǣ�����һ��������λ�ȡ���������Ķ�������ã�������εķ�ת��
41.spring�����ִ���ʽ��
��Ŀ�����ʵ�������ɽӿڣ�springʹ��JDK��java.lang.reflect.Proxy�����
      �ŵ㣺��Ϊ�нӿڣ�����ʹϵͳ���������
      ȱ�㣺Ϊÿһ��Ŀ���ഴ���ӿ�
��Ŀ�����û��ʵ���κνӿڣ�springʹ��CGLIB������Ŀ���������ࡣ
      �ŵ㣺��Ϊ��������Ŀ�����Ǽ̳й�ϵ�����Բ���Ҫ�нӿڵĴ��ڡ�
      ȱ�㣺��Ϊû��ʹ�ýӿڣ�����ϵͳ�������û��ʹ��JDK�Ķ�̬����á�
42.springMVC�����̣�
1.�û�����������ǰ�˿�����DispatcherServlet
2.DispatcherServlet�յ��������HandlerMapping������ӳ������
3.������ӳ������������url�ҵ�����Ĵ����������ɴ��������󼰴�����������(�����������)һ�����ظ�DispatcherServlet��
4.DispatcherServletͨ��HandlerAdapter���������������ô�����
5.ִ�д�����(Controller��Ҳ�к�˿�����)��
6.Controllerִ����ɷ���ModelAndView
7.HandlerAdapter��controllerִ�н��ModelAndView���ظ�DispatcherServlet
8.DispatcherServlet��ModelAndView����ViewReslover��ͼ������
9.ViewReslover�����󷵻ؾ���View
10.DispatcherServlet��View������Ⱦ��ͼ������ģ�������������ͼ�У���
11.DispatcherServlet��Ӧ�û�
43.Springmvc���ŵ㣿
1.���ǻ������������.ȫ����Ӧ�ö���,���ۿ���������ͼ,����ҵ�����֮��Ķ��� java���.���Һ�Spring�ṩ�����������ṹ���ܼ���.
2.��������Servlet API(Ŀ���������,������ʵ�ֵ�ʱ��ȷʵ��������Servlet��)
3. ��������ʹ�ø�����ͼ����,��������������JSP
4 . ֧�ָ���������Դ��ӳ�����
5 .��Ӧ��������չ��