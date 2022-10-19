# 2023-ServletJSP
-----------------

## Web Application Architecture
------------------------------------------------------------------------------------
The web application architecture describes the interactions between
 - applications
 - databases
 - middleware systems on the web. 
 
 It ensures that multiple applications work simultaneously. Let us understand it with a simple example of opening a webpage.
 
 ### How does it work?
 ----------------------------------------------------------------------------------
Server-side Code - The code that is on the server and responds to the HTTP requests
he server-side code is responsible for creating the page that the user requested as well as storing different types of data,
including user profiles and user input. It is never seen by the end-user.

Client-side Code - The code that is in the browser and responds to some user input.
A combination of CSS, HTML, and JavaScript is used for writing the client-side code. This code is parsed by the web browser. 
 Unlike the server-side code, client-side code can be seen as well as modified by the user. It reacts to user input.
 
 ### Client Side Processing
 Client-side processing
– Some processing needs to be “executed” by
the browser, either to form the request for the
dynamic Web page or to create or display the
dynamic Web page.
Eg. Javascript code to validate user input

• Client-side processing
– CSS
– HTML
– JavaScript
– Adobe Flex
– Microsoft Silverlight
 
 ### Server Side Processing
 In server-side processing, the Web server:
– Receives the dynamic Web page request
– Performs all of the processing necessary to
create the dynamic Web page
– Sends the finished Web page to the client for
display in the client’s browser

• Server-side
processing
– PHP
– ASP
– ASP.NET
– Perl
– J2EE
– Python, e.g. Django
– Ruby, e.g. Ruby on Rails
– ColdFusion 



## Http 
------------------------------------------------------------------------------------
https://developer.mozilla.org/en-US/docs/Web/HTTP/Messages 
**Http reuqest Message **
<img width="667" alt="image" src="https://user-images.githubusercontent.com/27730844/196683733-a2a575fb-9800-4e21-ba86-9338f85de017.png">



**Http Response Message**
<img width="664" alt="image" src="https://user-images.githubusercontent.com/27730844/196683844-7dc24619-16a2-462a-9c1b-87e2c8e05731.png">

https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol 

<img width="784" alt="image" src="https://user-images.githubusercontent.com/27730844/196682819-585f036d-7015-450a-aab4-dd2bcf30cc47.png">

GET requests can be cached
GET requests remain in the browser history
GET requests should never be used when dealing with sensitive data
GET requests have length restrictions
GET requests are only used to request data (not modify)
----------------------------------------------------
POST requests are never cached
POST requests do not remain in the browser history
POST requests have no restrictions on data length

## Options to create Web Application

##3 CGI(Common Gateway Interface)
------------------------------------------------------------------------------------
CGI technology enables the web server to call an external program and pass HTTP request information to the external program to process the request

** Disadvantages:** 
If the number of clients increases, it takes more time for sending the response.
For each request, it starts a process, and the web server is limited to start processes.
It uses platform dependent language

##3 Servlet
------------------------------------------------------------------------------------
1. Better Performance
2. Robust
3. Secure
4. Portability



### What is Servlet

1. Servlet technology is used to create a web application
2. Servlet is a technology which is used to create a web application.
3. Servlet is an API that provides many interfaces and classes including documentation.
4. Servlet is an interface that must be implemented for creating any Servlet.
5. Servlet is a class that extends the capabilities of the servers and responds to the incoming requests. It can respond to any requests.
6. Servlet is a web component that is deployed on the server to create a dynamic web page

<img width="505" alt="image" src="https://user-images.githubusercontent.com/27730844/196682481-55a3ca18-b815-40b2-b945-ce610f363f1f.png">

### Servlet API
---------------
1. javax.servlet - Protocol Specific
2. javax.servlet.http - Http Protocol Specific

**javax.servlet**
_Interfaces_
Servlet
ServletRequest
ServletResponse
RequestDispatcher
ServletConfig
ServletContext

_Class_
GenericServlet
ServletInputStream
ServletOutputStream

**javax.servlet.http**

_interfaces_
HttpServletRequest
HttpServletResponse
HttpSession
HttpSessionListener

_Classes_
HttpServlet
Cookie

## Servlet Life Cycle
------------------------------------------------------------------------------------
There are mainly three life cycle methods of a servlet, which we can describe as:

init()
service()
destroy()

<img width="687" alt="image" src="https://user-images.githubusercontent.com/27730844/196686656-d5ecbcfd-e615-4351-95bb-bac0c7f940e9.png">

1. Servlet class is loaded.
  - The classloader is responsible to load the servlet class. The servlet class is loaded when the first request for the servlet is received by the web container.
  
2. Servlet instance is created.
 -  The web container creates the instance of a servlet after loading the servlet class. The servlet instance is created only once in the servlet life cycle.
 
3. init method is invoked.
 - it initialises the servlet. Servlet. init() indicates that the servlet instance was created successfully.Servlet container calls the Servlet.init() method to denote that this Servlet instance is successfully instantiated and is ready for the service.
public void init(ServletConfig config) throws ServletException {    //initialization code }

4. service method is invoked.
- The web container calls the service method each time when request for the servlet is received. If servlet is not initialized, it follows the first three steps as described above then calls the service method. If servlet is initialized, it calls the service method.

public void service(ServletRequest request, ServletResponse response)   
  throws ServletException, IOException  
  
8. destroy method is invoked.
The web container calls the destroy method before removing the servlet instance from the service. It gives the servlet an opportunity to clean up any resource for example memory, thread etc. 
 public void destroy()  

## Ways to create Servlet ?
1. By implementing Servlet interface,
2. By inheriting GenericServlet class, (or)
3. By inheriting HttpServlet class

## Software Requirement
------------------------------------------------------------------------------------
 - Eclipse : https://www.eclipse.org/downloads/download.php?file=/technology/epp/downloads/release/2022-09/R/eclipse-jee-2022-09-R-macosx-cocoa-x86_64.dmg
 - Java 8 
 - Maven 3.8.1 : https://mkyong.com/maven/how-to-install-maven-in-windows/
 - Tomcat 9: https://tomcat.apache.org/download-90.cgi


## Enviornment Setup
------------------------------------------------------------------------------------
1. Download the eclipse and click on Eclipse icon.

## Lab: Create a Hello Servlet
------------------------------------------------------------------------------------
1. Create "Dynamic Web Project" -> HelloServlet
2. You will find the following project structure
<img width="284" alt="image" src="https://user-images.githubusercontent.com/27730844/196420493-056e895a-3010-474e-805c-b546c23acf9d.png">
3. Rc-> Configure -> Convert to Maven -> Finish
4. Create a new Servlet -> Rc the src -> Select new -> Others-> Servlet-> Next-> packagename: com.hello -> class: HelloServlet
 <img width="430" alt="image" src="https://user-images.githubusercontent.com/27730844/196421450-f535fdcf-be5d-4844-be7c-92bcc3133deb.png">
5. Run it -> Rc-> Run 
6. Add a Web Deployment Descriptor

```
<web-app>  
  
<servlet>  
<servlet-name>hi</servlet-name>  
<servlet-class>com.hello.HelloServlet</servlet-class>  
</servlet>  
  
<servlet-mapping>  
<servlet-name>hi</servlet-name>  
<url-pattern>/welcome</url-pattern>  
</servlet-mapping>  
  
</web-app>

```

# JSP
------------------------------------------------------------------------------------
## What is JSP
------------------------------------------------------------------------------------

## Advantage of JSP over Servlet
------------------------------------------------------------------------------------

## Life cycle of JSP
------------------------------------------------------------------------------------

## Implicit Objects
------------------------------------------------------------------------------------

## JSP API
------------------------------------------------------------------------------------

## JSP Scriplet elements
------------------------------------------------------------------------------------
### Scriplet tags
### Expression Tags
### declaration tags

## implicit objects
------------------------------------------------------------------------------------


## Declarative Elements
------------------------------------------------------------------------------------

## Action Elements
------------------------------------------------------------------------------------


## JSP CRUD
------------------------------------------------------------------------------------

##  Lab: Accept the username and Display the Hello.jsp on button click
------------------------------------------------------------------------------------

## Lab: Create Login page and display message the accordingly.
------------------------------------------------------------------------------------


## Lab: Create a Employee list page.
------------------------------------------------------------------------------------


## WebServices
----------------------------------------------------------------------------------------------------------------------------------
Web Service is a software system
designed to support machine-to-machine
interaction over a network.

• Web services are frequently just Internet
Application Programming Interfaces (API)
that can be accessed over a network. 

Web Services are platform-independent and
language-independent, since they use standard
XML languages.

• Most Web Services use HTTP for transmitting
messages (such as the service request and
response).
• Style of Use
– RPC
– SOAP
– REST

## XML
--------------------------
XML is a universally agreed markup metalanguage primarily used for information
exchange.
! The two primary building blocks of XML are
elements and attributes.
› Elements are tags and have values.
› Elements are structured as a tree.
› Alternatively, elements may have both attributes as
well as data
› Attributes help you to give more meaning and
describe your element more efficiently and clearly. 

```
<?xml version=\"1.0\" encoding=\"UTF-8\"?>
<person>
<id type="integer">1111</id>
<last_name>Smith</last_name>
<first_name>John</first_name>
<address>
<city>New York</city>
<street>21 2nd Street</street>
<postal_code type="integer">10021</postal_code>
<state>NY</state>
</address>
</person> 
```

### JSON
---------------------------------------------
- JSON is a lightweight computer
data interchange format.
- JSON is based on a subset of the JavaScript programming
language.
- It is considered to be a languageindependent data format.
- It serves as an alternative to the
use of the XML format


{
 "firstName": "John",
 "lastName": "Smith",
 "address": {
 "street": "21 2nd Street",
 "city": "New York",
 "state": "NY",
 "postalCode": 10021
 },
 "phoneNumbers": [
 "212 555-1234",
 "646 555-4567"
 ]
 } ```
```
