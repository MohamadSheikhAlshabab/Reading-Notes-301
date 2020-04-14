# Read13

____________

## Sending form data :

  - Client/server architecture:
    - At it's most basic, the web uses a client/server architecture that can be summarized as follows
    - a client (usually a web browser) sends a request to a server (most of the time a web server like Apache, Nginx, IIS, Tomcat, etc.),using the HTTP protocol. 
    - The server answers the request using the same protocol.
    - ![link](https://developer.mozilla.org/files/4291/client-server.png)
    
 - On the client side: defining how to send the data:
   
   - The <form> element defines how the data will be sent.
   - All of its attributes are designed to let you configure the request to be sent when a user hits a submit button.
   - The two most important attributes are action and method.
   
   - The action attribute:
      - The action attribute defines where the data gets sent. 
      - Its value must be a valid relative or absolute URL.
      - If this attribute isn't provided, the data will be sent to the URL of the page containing the form — the current page.
      
   - The method attribute:
     - The method attribute defines how data is sent.
     -  The HTTP protocol provides several ways to perform a request; HTML form data can be transmitted via a number of different methods.
     - the most common being the GET method and the POST method.
     
  - The GET method:
    - The GET method is the method used by the browser to ask the server to send back a given resource.
    
  - The POST method:
    - It's the method the browser uses to talk to the server when asking for a response that takes into account the data provided in the body of the HTTP requestز
   
 - Viewing HTTP requests: you need to use tools such as the Firefox Network Monitor or the Chrome Developer Tools.
  1. Open the developer tools.
  2. Select "Network"
  3. Select "All"
  4. Select "foo.com" in the "Name" tab
  5. Select "Headers"
  
  This can be very important for two reasons:
  1. If you need to send a password (or any other sensitive piece of data), never use the GET method or you risk displaying it in the URL bar, which would be very insecure.
  2. If you need to send a large amount of data, the POST method is preferred because some browsers limit the sizes of URLs. In addition, many servers limit the length of URLs they accept.
  
  
 - Summary
   - As we'd alluded to above, sending form data is easy, but securing an application can be tricky. Just remember that a front-end developer is not the one who should define the security model of the data.It's possible to perform client-side form validation, but the server can't trust this validation because it has no way to truly know what has really happened on the client-side.

   - If you've worked your way through these tutorials in order, you now know how to markup and style a form, do client-side validation, and have some idea about submitting a form.
