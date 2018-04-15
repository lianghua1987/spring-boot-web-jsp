Embedded Servlet container, can be packaged to jar.
pros: easy to use, light weight
cons: not support JSP


External Servlet Container: Install Tomcat -- Package .war
Steps:

* Create a .war project using Springboot initializer
    * Project Structure
    * Web -> Add Deployment Descriptors: web.xml
    * Change web resource directory to src/main/webapp/WEB-INF/web.xml
    
* Embedded Tomcat scope change to "provide"

* Create new class 
public class ServletInitializer extends SpringBootServletInitializer {
 
         @Override
         protected SpringApplicationBuilder configure(SpringApplicationBuilder application) {
             return application.sources(SpringBootWebJspApplication.class);
         }
 
 }
* Add following to application.properties(controller only return file name)
spring.mvc.view.prefix=/WEB-INF/
spring.mvc.view.suffix=.jsp

* Start server