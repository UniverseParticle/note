# note
personal note

<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>

	<groupId>com.gosuncn</groupId>
	<artifactId>JDAS</artifactId>
	<version>1.0.0</version>
	<packaging>jar</packaging>

	<name>JDAS</name>
	<description>Demo project for Spring Boot</description>

	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>1.5.8.RELEASE</version>
		<relativePath/> <!-- lookup parent from repository -->
	</parent>

	<properties>
		<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
		<project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
		<java.version>1.8</java.version>
		<maven.build.timestamp.format>yyyyMMddHHmmss</maven.build.timestamp.format>
	</properties>


	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-data-jpa</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>

		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>test</scope>
		</dependency>

		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-jms</artifactId>
		</dependency>

		<dependency>
			<groupId>org.apache.qpid</groupId>
			<artifactId>qpid-client</artifactId>
			<version>0.32</version>
		</dependency>

		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-jms</artifactId>
			<version>4.3.8.RELEASE</version>
		</dependency>
		<dependency>
			<groupId>com.alibaba</groupId>
			<artifactId>fastjson</artifactId>
			<version>1.2.13</version>
		</dependency>
		<dependency>
			<groupId>org.apache.geronimo.specs</groupId>
			<artifactId>geronimo-jms_1.1_spec</artifactId>
			<version>1.1.1</version>
		</dependency>

		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
		</dependency>
		<dependency>
			<groupId>mysql</groupId>
			<artifactId>mysql-connector-java</artifactId>
		</dependency>
	</dependencies>

	<scm>
		<connection>scm:svn:http://172.17.0.2/svn/C3M-DPCS/trunk/source/BGSever/DAS</connection>
		<developerConnection>scm:svn:http://172.17.0.2/svn/C3M-DPCS/trunk/source/BGSever/DAS</developerConnection>
		<tag>HEAD</tag>
		<url>http://172.17.0.2/svn/C3M-DPCS/trunk/source/BGSever/DAS</url>
	</scm>


	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
			<plugin>
				<artifactId>maven-compiler-plugin</artifactId>
				<configuration>
					<source>1.7</source>
					<target>1.7</target>
				</configuration>
			</plugin>
			<plugin>
				<groupId>org.codehaus.mojo</groupId>
				<artifactId>buildnumber-maven-plugin</artifactId>
				<version>1.4</version>
				<executions>
					<execution>
						<phase>validate</phase>
						<goals>
							<goal>create</goal>
						</goals>
					</execution>
				</executions>
				<configuration>
					<doCheck>false</doCheck>
					<doUpdate>true</doUpdate>
				</configuration>
			</plugin>
			<plugin>
				<groupId>org.apache.maven.plugins</groupId>
				<artifactId>maven-jar-plugin</artifactId>
				<configuration>
					<archive>
						<manifestEntries>
							<alikoubeiserver-svn-version>${buildNumber}</alikoubeiserver-svn-version>
						</manifestEntries>
					</archive>
				</configuration>
			</plugin>
		</plugins>
		<finalName>${project.artifactId}-${project.version}.${buildNumber}</finalName>
	</build>
</project>
