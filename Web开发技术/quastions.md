# 2. Java Web 概述
- Tomcat服务器的默认端口为( )
    - A. 8888
    - B. 8080
    - C. 8009
    - D. 80

    正确答案: B

- Tomcat的端口号可以在( )文件中修改
    - A. server.xml
    - B. web.xml
    - C. tomcat.xml
    - D. Config.xml

    正确答案：A

# 4. Servlet基础
- 在编写Servlet时需要( )
    - A. 继承自Servlet
    - B. 实现HttpRequestServlet
    - C. 继承HttpServlet
    - D. 实现HttpRequest

    正确答案: C

- HttpServlet中，用来处理GET请求的方法是( )
    - A. get
    - B. doGet
    - C. doPost
    - D. post

    正确答案: B

- 在java Web应用开发中，Servlet程序需要在( )文件中配置
    - A. Jsp
    - B. web.xml
    - C. servlet.xml
    - D. application.xml

    正确答案: B

- 以下关于Servlet生命周期说法错误的是( )
    - A. Servlet容器根据Servlet类的位置加载Servlet类,成功加载后,由Servlet容器创建Servlet的实例
    - B。对于每一个Servlet实例,init()方法只被调用一次
    - C. 当Servlet容器接收到客户端请求时,调用Servlet的service()方法以及destory()方法处理客户端请求
    - D. servlet的实例是由servlet容器创建的,所以实例销毁也由容器完成

    正确答案: C

- 多选题，有关Servlet的生命周期说法正确的有()
    - A. Servlet的生命周期由Servlet实例控制
    - B. init()方法在创建完Servlet实例后对其进行初始化,传递的参数为实现ServletConfig接口的对象
    - C. service()方法响应客户端发出的请求
    - D. destroy()方法释放Servlet实例

    正确答案: BCD

- 在访问Servlet时,在浏览器地址栏中输入的路径是在( )地方配置的
    - A. `<servlet-name/>`
    - B. `<servlet-mapping/>`
    - C. `<servlet-class/>`
    - D. `<url-pattern/>`

    正确答案: D

- 多选题，对于以下代码片段,说法正确的是( )
    ```xml
    <servlet>
        <servlet-name>testServlet</servlet-name>
        <servlet-class>edu.qust.TestServlet</servlet-class>
    </servlet>
    ```

    - A. 配置了逻辑名为 testServlet 的Servlet组件
    - B. 其对于的类的路径是: edu.qust.TestServlet
    - C. 客户端可以通过testServlet访问
    - D. 以上说法都不对

    正确答案: AB

- 对于HttpServlet类的描述,错误的是()
    - A. 我们自己编写的Servlet继承了HttpServlet类,一定需覆盖doPost或者doGet
    - B. Httpservlet类扩展了GenericServlet类,实现了GenericServlet类的抽象方法
    - C. Httpservlet类中处理客户请求和响应时所使用的两个接口是: HttpServletRequest和HttpServletResponse
    - D. 我们自己编写的servlet继承了Httpservlet类,一般只需要覆盖doPost或doGet方法,不必覆盖servive()方法,因为一个service()方法会调用doPost或者doGet方法

    正确答案: A

- 如果是整个应用程序会共享的数据,则适合存放在()对象之中成为属性?
    - A. ServletConfig
    - B. ServletContext
    - C. Servlet
    - D. Session

    正确答案: B

- 哪一个方法可以从ServletContext对象内读取某个属性()
    - A. String getAttribute(int index)
    - B. String getAttribute(String name)
    - C. Object getAttribute(String name)
    - D. Enumeration getAttribute(String name)

    正确答案: C

- 如果要取得ServletContext初始参数,则可以执行()方法?
    - A. getContextParameter()
    - B. getParameter()
    - C. getInitParameter()
    - D. getAttribute()

    正确答案: C

- 在Servlet中,response.getWriter()返回的是()
    - A. JspWriter对象
    - B. PrintWriter对象
    - C. Out对象
    - D. ResponseWriter对象

    正确答案: B

- 在Servlet中,下列语句可以正确获取PrintWriter对象的是()
    - A. PrintWriter out=request.getWriter();
    - B. PrintWriter out = request.getPrintWriter();
    - C. PrintWriter out=response.getWriter();
    - D. PrintWriter out = response.getPrintWriter();

    正确答案: C

- HttpServletResponse的()方法用于一个HTTP请求重定向到另一个资源。
    - A. sendURL()
    - B. sendRedirect()
    - C. forward()
    - D. redirectURL()

    正确答案: B

- 通过HttpServletResponse的( )方法可以设置响应所采用的字符编码类型。
    - A. setCharacterEncoding()
    - B. setCharset()
    - C. setEncoding()
    - D. setContentType()

    正确答案: A

- 现有HpptServletRequest对象request,以下代码中可以正确设置客户端请求编码为UTF-8的是()
    - A. request.setCharacterEncoding("UTF-8")
    - B. request.setCharset("UTF-8")
    - C. request.setContentType("UTF-8")
    - D. request.setEncoding("UTF-8")

    正确答案: A

- 对于ServletRequest接口的etAttribute()方法,说法正确的是()
    - A. 获取指定名称的属性值
    - B. 设置指定属性的值
    - C. 删除指定属性的值
    - D. 以上都不对

    正确答案: A

- 给定一个Servlet的doGet方法中的代码片段,如下:
    ```java
    request.setAttribute("name" ,"zhang" );
    response.sendRedirect( "http://localhost:8080/demo/MyServlt")
    ```

    那么在MyServlet中可以使用()方法把属性name的值取出来?
    - A. String str=request.getAttribute("name" );
    - B. String str=(String)request.getAttribute("name" );
    - C. Object str=request.getAttribute( "name" );
    - D. 无法取出

    正确答案: D

- 以下哪个方法可以正确获取复选框的值()
    - A. request.getParameterValue()
    - B. response.setParameterValues()
    - C. request.getParameterValues()
    - D. request.getParameter()

    正确答案: C

- 一次重定向过程中,浏览器会发出多少次服务器请求?()
    - A. 0次
    - B. 1次
    - C. 2次
    - D. 无数次

    正确答案: C

- 以下可以实现请求转发的是()
    - A. request.getRequest Dispatcher("list.jsp");
    - B. response.getRequest Dispatcher("list.jsp");
    - C. response.getRequest Dispatcher("list.jsp").forward(request,response);
    - D. request.getRequest Dispatcher("list.jsp").forward(request,response):

    正确答案: D

- 以下关于转发和重定向的说法错误的是( )
    - A. 转发通过request的getRequestDispatcher().forward()方法即可实现,它的作用是在多个页面交互过程中实现请求数据的共享。
    - B. 重定向可以理解为是浏览器至少提交了两次请求,它是在客户端发挥作用,通过请求新的地址实现页面转向
    - C. 转发和重定向都可以共享request范围内的数据
    - D. 转发时客户端的URL地址不会发生改变,而重定向时客户端浏览器中显示的是新的URL地址。

    正确答案: C

# 5. 会话及会话技术

- 如何创建Cookie对象?()
    - A. 使用newCookie语句
    - B. 调用response.addCookie方法
    - C. 使用Cookie的setMaxAge方法
    - D. 调用setCookie方法

    正确答案: A

- 如何发送Cookie对象?()
    - A. 使用newCookie语句
    - B. 调用response.addCookie方法
    - C. 使用Cookie的setMaxAge方法
    - D. 调用setCookie方法

    正确答案: B

- 如何设定Cookie的有效期限?()
    - A. 使用setMaxAge()
    - B. 使用setMaxInactive()
    - C. 使用setMaxInactiveInterval()
    - D. 在web.xml中设定`<cookie-timeout>`

    正确答案: A

# 6. JSP技术
- 在JSP中,只有一行代码:`<%=A+B%>`,运行将输出()。
    - A. A+B
    - B. AB
    - C. 131
    - D. 没有任何输出,因为表达式是错误的

    正确答案: D

- 在JSP中,只有一行代码:`<%= 'A'+'B'%>`,运行将输出()。
    - A. A+B
    - B. AB
    - C. 131
    - D. 没有任何输出,因为表达式是错误的

    正确答案: C

- 以下JSP代码运行后的结果为( )
    ```jsp
    <% int i=8;%>
    <%= i+"8" %>
    ```
    - A. i8
    - B. 88
    - C. 16
    - D. 编译错误

    正确答案: B

- test.jsp文件如下所示,运行时,将发生( )。
    ```html
    <html>
        <% String str = null;%>
        str is <%=str%>
    </html>
    ```
    - A. 编译阶段出现错误
    - B. 翻译阶段出现错误
    - C. 执行字节码时发生错误
    - D. 运行后,浏览器上显示:strisnull

    正确答案: D

- 给定以下JSP代码片段,有2个客户依次浏览该JSP,且每个客户只浏览一次,第2个客户会看到浏览器显示( )
    ```js
    <% intx=1;%>
    <%! int x = 10; %>
    x=<%=x%>
    ```
    - A. x=1
    - B. x=2
    - C. x=10
    - D. x=11

    正确答案: A

- 在JSP中,以下的page指令设置了使用的脚本语言是Java,且导入了java.rmi.* 和java.util.* 包.正确的是( )
    - A. `<%@ page Language="Java",import="java.rmi.*;java.uitl.* "%">`
    - B. `<%@ page language="Java" Import="java.rmi.*,java.uitl.* "%">`
    - C. `<%@ page language="Java";import="java.rmi.*;java.uitl.* "%">`
    - D. `<%@ page language="Java" import="java.rmi.* ,java.uitl.* "%>`

    正确答案: D

- JSP页面的page指令主要用于设置该页面的各种属性,page指令的language属性的作用是( )
    - A. 将需要的包或类引入到JSP页面中
    - B. 指定JSP页面使用的脚本语言,默认为Java
    - C. 指定JSP页面采用的编码方式,默认为text/html
    - D. 服务器所在国家编码

    正确答案: B

# 7. EL和JSTL
- EL表达式,`${10mod3}`,执行结果为( )
    - A. 10 mod 3
    - B. 1
    - C. 2
    - D. null

    正确答案: B

- EL表达式:${(10*10) ne 100}的值是( )
    - A. 0
    - B. true
    - C. false
    - D. 1

    正确答案: C

- 关于EL表达式`${(1==2)?3:4}`的运算结果正确的是( )
    - A. true
    - B. false
    - C. 3
    - D. 4

    正确答案: D

- 在请求中没有包含名为user的参数时,使用如下语句: `${user}`,则会出现( )
    - A. 编译报错
    - B. 运行出错
    - C. null
    - D. 什么都没有

    正确答案: D

- Jsp页面中有如下语句:
    ```java
    request.setAttribute("user", "tom");
    session.setAttribute("user","bob");
    ```
    使用`${user}`则显示( )
    - A. null
    - B. tom
    - C. bob
    - D. 啥也没有

    正确答案: B

- Jsp页面中有如下语句:
    ```java
    pageContext.setAttribute("user","tom");
    request.setAttribute("user","bob");
    ```
    显示"bob",则可以使用( )
    - A. ${request.getAttribute("user")}
    - B. ${param.user}
    - C. ${user}
    - D. ${requestScope.user}

    正确答案: D

- 下面选项中,与
    ```java
    request.getAttribute("p")
    ```
    等效的EL表达式是()
    - A. `$<request.p>`
    - B. `$[requestScope.p]`
    - C. `$(request.p)`
    - D. `${requestScope.p}`

    正确答案: D

- EL表达式:`${user.loginName}`执行效果等同于( )
    - A. `<%=user.getLoginName()%>`
    - B. `<%user.getLoginName();%>`
    - C. `<%=user.loginName%>`
    - D. `<%user.loginName;%>`

    正确答案: A

- 阅读下面代码片段:c_ifjsp:
    ```jsp
    <body>
        <c:if test="${1==1}" > hello world </c:if>
    </body>
    ```
    当在浏览器访问该c_ifjsp时的效果是( )
    - A. 浏览器空白,控制台有信息显示
    - B. 浏览器报错,控制台出现异常
    - C. 浏览器显示:helloworld,控制台正常
    - D. 浏览器正常,控制台显示:helloworld

    正确答案: C

- 以下哪句代码可以正确导入核心标签库()
    - A. `<% page import="c"%>`
    - B. `<% page prefix ="c" uri = "/WEB-INF/c.tld"%>`
    - C. `<% taglib prefix ="c" import = "/WEB-INF/c.tld" %>`
    - D. `<% taglib prefix ="c" uri = "/WEB-INF/c.tld"%>`

    正确答案: D

- 以下哪个标签实现了switch功能( )
    - A. `<c:if>`
    - B. `<c:switch>`
    - C. `<c:choose>与<c:when>`
    - D. `<C:case>`

    正确答案: C

# JavaBean与JSP开发模型
- 假设创建JavaBean的类中有一个int型的属性num,下列哪个是正确的设置该属性的方法( )
    - A. `public void setNum(int num) { this.num = num;}`
    - B. `public setNum(int num) {this.num = num;}`
    - C. `public voidsetNum(int num) {this.num = num; }`
    - D. `void setNum(int num) {this.num = num;}`

    正确答案: A

- 关于MVC模式说法正确的是( )
    - A. 用来将代码分开的方法
    - B. 将显示、流程控制、业务逻辑分开, 提高了维护性
    - C. 增加了代码的复杂度
    - D. 只用java才有的模型

    正确答案: B

- 下面关于MVC的说法不正确的是( )
    - A. M表示Model层,是存储数据的地方
    - B. View表示视图层,负责向用户显示外观
    - C. Controller是控制层,负责控制流程
    - D. 在MVC架构中jsp通常做控制层

    正确答案: D

- JSPModel2模型就是MVC设计模式,其中实现控制器角色的是( )
    - A. JSP
    - B. JS
    - C. Servlet
    - D. JavaBean

    正确答案: C

- JavaWeb中,MVC模型的M、V、C分别用___, ___, ___
表示()
    - A. Jsp、servlet、java bean
    - B. Html、java bean、jsp
    - C. Java bean、jsp、servlet
    - D. servlet、html、jsp

    正确答案: C

# 9. Serviet高级
- 使用Servlet过滤器时,需要在web.xml通过( )元素将过滤器映射到Web资源。
    - A. `<filter>`
    - B. `<filter-mapping>`
    - C. `<servlet>`
    - D. `<servlet-mapping>`

    正确答案: B

- 在web.xml中使用( )标签配置过滤器
    - A. `<filter>`和`<filter-mapping>`
    - B. `<filter-name>`和`<filter-class>`
    - C. `<filter>`和`<filter-class>`
    - D. `<filter-pattern>`和`<filter>`

    正确答案: A

- 在Filter配置信息中,不属于dispatcherTypes元素的可选值是( )
    - A. INCLUDE
    - B. FORWARD
    - C. RESPONSE
    - D. REQUEST

    正确答案: C

- 下列接口中,用于调用过滤器链中下一个过滤器的是( )
    - A. Filter接口
    - B. FilterChain接口
    - C. FilterConfig接口
    - D. ServletResponse接口

    正确答案: B

- 下列关于文件上传说法错误的是()
    - A. 在表单页面中,需要使用`<inputtype="file">`标签在jsp
    页面中添加文件上传输入项
    - B. `<inputtype="file">`标签的必须要设置input输入项的name属性
    - C. `<inputtype="file">`标签必须把将表单页面的method属性设置为get方式
    - D. `<inputtype="file">`标签的enctype属性设置为"multipart/form-data"类型

