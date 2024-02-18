We can use initialization parameters to set values to certain variables and instance variables.

```java
  
@WebServlet(name = "requestProcessingServlet", urlPatterns = "/reqproc", initParams = {  
        @WebInitParam(name = "applicationName", value = "someNameForTheApplication")  
})  
public class RequestProcessingServlet extends HttpServlet {  
  
    private String applicationName;  
  
    @Override  
    public void init(ServletConfig config) throws ServletException {  
        applicationName = config.getInitParameter("applicationName");  
    }  
  
    @Override  
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {  
        String firstName = req.getParameter("fname");  
        String lastName = req.getParameter("lname");  
  
        resp.setContentType("text/html");  
        resp.getWriter().println("<h1>Hello " + firstName + " " + lastName + "<br/>" + applicationName);  
    }
}
```