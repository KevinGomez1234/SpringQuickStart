# SpringQuickStart
Starting a quick SpringBoot application manually
# Setting up your Springboot application
- Start by generating a maven archetype
`$ mvn archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4`
- Either use the parent pom or import a bill of materials in the <dependencyManagment> element
```
	<dependencyManagement>
		<dependencies>
			<dependency>
				<!-- Import dependency management from Spring Boot -->
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-dependencies</artifactId>
				<version>2.2.2.RELEASE</version>
				<type>pom</type>
				<scope>import</scope>
			</dependency>
		</dependencies>
	</dependencyManagement>
```
- Some important dependencies and their purpose
```
<!-- https://mvnrepository.com/artifact/org.junit.jupiter/junit-jupiter-api -->
		<dependency>
			<groupId>org.junit.jupiter</groupId>
			<artifactId>junit-jupiter-api</artifactId>
			<scope>test</scope>
		</dependency>
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-context</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-web</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-autoconfigure</artifactId>
		</dependency>
		<!-- https://mvnrepository.com/artifact/org.springframework.boot/spring-boot-starter-web -->
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
		<dependency>
			<groupId>com.fasterxml.jackson.dataformat</groupId>
			<artifactId>jackson-dataformat-xml</artifactId>
			<version>2.11.1</version>
		</dependency>
		<dependency>
			<groupId>org.springframework.retry</groupId>
			<artifactId>spring-retry</artifactId>
			<version>1.2.5.RELEASE</version>
		</dependency>
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-aspects</artifactId>
			<version>5.2.8.RELEASE</version>

		</dependency>
		<!-- https://mvnrepository.com/artifact/org.springframework.boot/spring-boot-starter-test -->
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>
```

#Maven plugin
```
				<plugin>
					<groupId>org.springframework.boot</groupId>
					<artifactId>spring-boot-maven-plugin</artifactId>
				</plugin>
```

# Troubleshooting
- If you get class version errors downgrade your java-compiler and target `<maven.compiler.source>1.8</maven.compiler.source>
		<maven.compiler.target>1.8</maven.compiler.target>` to 1.8 to be safe, this is usually due to your jdk version being incompatible with your builds... 
