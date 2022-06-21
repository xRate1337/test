    <!-- https://mvnrepository.com/artifact/org.cyclonedx/cyclonedx-maven-plugin -->
<dependency>
    <groupId>org.cyclonedx</groupId>
    <artifactId>cyclonedx-maven-plugin</artifactId>
    <version>2.7.0</version>
</dependency>

<!-- https://mvnrepository.com/artifact/io.github.pmckeown/dependency-track-maven-plugin -->
<dependency>
    <groupId>io.github.pmckeown</groupId>
    <artifactId>dependency-track-maven-plugin</artifactId>
    <version>1.1.3</version>
</dependency>


        <profiles>
          <profile>   
          <id>dtrack</id>               
            <build>
            <plugins>
            
                <plugin>
        <groupId>org.cyclonedx</groupId>
        <artifactId>cyclonedx-maven-plugin</artifactId>
        <version>2.7.0</version>
        <executions>
            <execution>
                <goals>
                    <goal>makeAggregateBom</goal>
                </goals>
            </execution>
        </executions>
        <configuration>
            <projectType>library</projectType>
            <schemaVersion>1.4</schemaVersion>
            <includeBomSerialNumber>true</includeBomSerialNumber>
            <includeCompileScope>true</includeCompileScope>
            <includeProvidedScope>true</includeProvidedScope>
            <includeRuntimeScope>true</includeRuntimeScope>
            <includeSystemScope>true</includeSystemScope>
            <includeTestScope>true</includeTestScope>
            <includeLicenseText>false</includeLicenseText>
            <outputReactorProjects>true</outputReactorProjects>
            <outputFormat>all</outputFormat>
            <outputName>bom</outputName>
        </configuration>
   </plugin>
            
            <plugin>
            <groupId>io.github.pmckeown</groupId>
            <artifactId>dependency-track-maven-plugin</artifactId>
            <version>1.1.3</version>
            <configuration>
                <dependencyTrackBaseUrl>http://localhost:8081</dependencyTrackBaseUrl>
                <apiKey>e01KDH8A5gyn0NmkPqHkrleSSLQShrLW</apiKey>
            </configuration>
                    <executions>
            <execution>
                <goals>
                    <goal>upload-bom</goal>
                </goals>
            </execution>
        </executions>
            </plugin>
            </plugins>
       </build>
       </profile>
       
</profiles>
