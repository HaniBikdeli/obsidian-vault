
In order to write a servlet and implement its different methods we need to create a class and extend the HttpServlet class.

We can then override one of the methods and write our own implementation.

```java
public class ServletBasics extends HttpServlet {  
  
    @Override  
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {  
		resp.getWriter().write("Hello world");
    }  
}
```

This implementation writes a string in response to the GET request. But we are not done yet as we have not specified a path for this servlet.

We can specify a path for our serlvet by these 2 methods:
1. using the @WebServlet Annotation
```java
@WebServlet(name = "ServletBasics", urlPatterns = "/servlet-basics")  
public class ServletBasics extends HttpServlet {
}
```
2. using the web.xml file
```xml
<servlet>  
    <servlet-name>servletBasics</servlet-name>  
    <servlet-class>dev.hanibikdeli.jakartaeewebprofile.serlvetbasics.ServletBasics</servlet-class>  
</servlet>  
<servlet-mapping>  
    <servlet-name>servletBasics</servlet-name>  
    <url-pattern>/servlet-basics</url-pattern>  
</servlet-mapping>
```

This way we have specified a name and a path for our servlet.