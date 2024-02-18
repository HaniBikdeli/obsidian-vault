
All servlets generally extend the HttpServlet class which itself extends the GenericSerlvet class which implements the Servlet interface.

Servlet interface:
```java
package jakarta.servlet;  
  
import java.io.IOException;  
  
public interface Servlet {  
    void init(ServletConfig var1) throws ServletException;  
  
    ServletConfig getServletConfig();  
  
    void service(ServletRequest var1, ServletResponse var2) throws ServletException, IOException;  
  
    String getServletInfo();  
  
    void destroy();  
}
```

this interface consists of 5 methods:
1. This method initializes the servlet.
2. This method is used to get an instance of ServletConfig class which includes the configuration properties needed to initialize the servlet. 
3. This method does the request processing in the servlet.
4. The getServletInfo method is method which can return a String and can be used for debugging purposes.
5. This method is used to destroy the servlet.

(!) Note that all servlet objects are singleton.