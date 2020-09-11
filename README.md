# To deploy spring boot on tomcat:

**1. Extends SpringBootServletInitializer :**
Update the @SpringBootApplication class to extend SpringBootServletInitializer, and override the configure method.
syntax:
`````
@Override
    protected SpringApplicationBuilder configure(SpringApplicationBuilder builder) {
        return builder.sources(StartWebApplication.class);
    }
`````
**2. For multiple main classes, make sure tell Spring Boot which main class to start-**
pom.xml
`````<properties>
    <!-- The main class to start by executing java -jar -->
    <start-class>com.mkyong.SpringBootWebApplication</start-class>
</properties>
``````
**3. dependency- provided**
syntax:
`````<dependency>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-tomcat</artifactId>
		<scope>provided</scope>
	</dependency>
`````
 **4. Update packaging to war pom.xml**
`<packaging>war</packaging>`
5. ``mvn install``

###To have our WAR file deployed and running in Tomcat.

1. Copy our WAR file from `target/tomcat-0.0.1-SNAPSHOT.war` to the `tomcat/webapps/` folder
2. From a terminal navigate to tomcat/bin folder and execute
`catalina.bat run` (on Windows)
catalina.sh run (on Unix-based systems)
3. Go to `http://localhost:8080/tomcat-0.0.1-SNAPSHOT/test`

