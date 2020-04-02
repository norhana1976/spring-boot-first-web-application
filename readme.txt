My First Spring Boot Application
---------------------------------


1.0   	How to start web application in spring boot
-------------------------------------------------
1. go to start.spring.io
2. Create groupID = com.in28minutes.springboot.web; artifactID = spring-boot-first-web-application
3. generate, download zip file
4. import in eclipse > maven > existing maven file > pom.xml
5. go to src/main/java/springbootwebapplication.java file, run java application

2.0	How to create java application message in web browser
------------------------------------------------------------
1. create new class > in same package > add logincontroller
2. put @Controller, @RequestMapping("/login"), @ResponseBody annotation
controller --> must have @controller annotation
to redirect to controller --> use @RequestMapping
to write the response message --> use @ResponseBody
3. Click on each annotation to "import" the binding annotations.
4. use "logging.level.org.springframework.web = DEBUG" utk debug code
5. Run LoginController file in java application / web browser to see the output message.

3.0	How to Redirect to JSP file
------------------------------------
1. In the controller file, only use @Controller, @RequestMapping annotations. Remove @ResponseBody as we don;t want to write the message but to redirect to jsp page.
2. In src/main/resources/application.properties, add:
spring.mvc.view.prefix: /WEB-INF/jsp/
spring.mvc.view.suffix: .jsp
Thsi is to set the path for jsp file.
3. In pom.xml, add dependency:
<dependency>
            <groupId>org.apache.tomcat.embed</groupId>
            <artifactId>tomcat-embed-jasper</artifactId>
            <scope>provided</scope>
        </dependency>
This is so the tomcat server will know this dispatcher servlet need to redirect.
4. Once pom file is changed, stop the console, start back the java application.
5. type: http://localhost:8080/login in browser, will see that it redirect to login.jsp file




