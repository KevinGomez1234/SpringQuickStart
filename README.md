# SpringQuickStart
Starting a quick SpringBoot application manually
# Setting up your Springboot application
- Start by generating a maven archetype
`$ mvn archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4`
- Either use the parent pom or import a bill of materials in the <dependencyManagment> element
```
    <dependencies>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-framework-bom</artifactId>
            <version>4.3.8.RELEASE</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>
```
- Some important dependencies and their purpose
```
    <!-- For application context -->
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-context</artifactId>
		</dependency>
    <!-- For rest template -->
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-web</artifactId>
		</dependency>
      <!-- For autoconfigure for registering beans -->
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-autoconfigure</artifactId>
		</dependency>
		 <!-- for springbootapplication annotation -->
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
```

# Troubleshooting
- If you get class version errors downgrade your java-compiler and target `<maven.compiler.source>1.8</maven.compiler.source>
		<maven.compiler.target>1.8</maven.compiler.target>` to 1.8 to be safe, this is usually due to your jdk version being incompatible with your builds... 
