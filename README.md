Hevelian Build Tools
===============

### Usage:
```xml
...
<build>
	<plugins>
		...
		<plugin>
			<groupId>org.apache.maven.plugins</groupId>
			<artifactId>maven-checkstyle-plugin</artifactId>
			<version>${checkstyle.version}</version>
			<dependencies>
				<dependency>
					<groupId>com.hevelian.build-utils</groupId>
					<artifactId>build-tools</artifactId>
					<version>1.0.0-SNAPSHOT</version>
				</dependency>
				<dependency>
					<groupId>com.puppycrawl.tools</groupId>
					<artifactId>checkstyle</artifactId>
					<version>10.14.2</version>
				</dependency>
			</dependencies>
			<executions>
				<execution>
					<phase>process-sources</phase>
					<goals>
						<goal>check</goal>
					</goals>
				</execution>
			</executions>
			<configuration>
				<failOnViolation>true</failOnViolation>
				<failsOnError>true</failsOnError>
				<violationSeverity>warning</violationSeverity>
				<configLocation>hevelian-checkstyle.xml</configLocation>
				<suppressionsFileExpression>checkstyle-suppressions.file</suppressionsFileExpression>
				<suppressionsLocation>hevelian-checkstyle-suppressions.xml</suppressionsLocation>
			</configuration>
		</plugin>
		...
	</plugins>
</build>
```
Try to use the exact version of the `build-tools` dependency instead of `-SNAPSHOT`. In other case the build might fail when a newer version appears.
