We can use servlets to manipulate the date given through the request to return a desired response.

Lets say we want the user to send his/her name through the request parameters of a servlet and then print the names that are given.

```java
protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {  
    String firstName = req.getParameter("fname");  
    String lastName = req.getParameter("lname");  
  
    resp.setContentType("text/html");  
    resp.getWriter().println("<h1>Hello " + firstName + " " + lastName);  
}
```

Now if we add the fname as hani and lname as bikdeli prams to the end of our url we get the message : Hello hani bikdeli

We can also get the same parameters from a form. Lets say we have a form like below:

```html
<form action="reqproc" method="post">  
    <p>  
        firstname: <input type="text" name="fname"/>  
    </p>  
    <p>  
        lastname: <input type="text" name="lname">  
    </p>  
    <p>  
        <input type="submit" placeholder="submit">  
    </p>  
</form>
```

And that we have implemented the POST method from HttpServlet with the same code as the GET method:
```java
@Override  
protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {  
    String firstName = req.getParameter("fname");  
    String lastName = req.getParameter("lname");  
  
    resp.setContentType("text/html");  
    resp.getWriter().println("<h1>Hello " + firstName + " " + lastName);  
}
```

We can then enter the firstname and the lastname and see the same result as the GET method.