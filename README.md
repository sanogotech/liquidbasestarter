# liquidbasestarter
LiquidBase  DB  Changelog   Starter

##  Docs
- https://www.baeldung.com/liquibase-refactor-schema-of-java-app
-https://docs.liquibase.com/tools-integrations/springboot/using-springboot-with-maven.html


## Dependencies

```

<parent>
         <groupId>org.springframework.boot</groupId>
         <artifactId>spring-boot-starter-parent</artifactId>
         <version>2.5.3</version>
         <relativePath/> <!-- lookup parent from repository -->
</parent>

          <dependency>
                 <groupId>org.liquibase</groupId> 
                 <artifactId>liquibase-core</artifactId>
       </dependency>
       
       <dependency>
                 <groupId>org.springframework.boot</groupId>
                 <artifactId>spring-boot-starter-data-jpa</artifactId>
       </dependency>
```

## To roll back any changes

```
create the liquibase.rollback-file file in Spring Boot and generate a rollback script for changes associated with changesets
```

## liquibase.properties

```
Windows example: changelog-file: ..\path\to\changelog.sql
Linux example: changelog-file: ../path/to/changelog.sql
```

## Generate a ChangeLog From Diffs Between Two Databases


```
mvn liquibase:diff

```

* liquibase.properties
```
changeLogFile=src/main/resources/liquibase-changeLog.xml
url=jdbc:mysql://localhost:3306/oauth_reddit
username=tutorialuser
password=tutorialmy5ql
driver=com.mysql.jdbc.Driver
referenceUrl=jdbc:h2:mem:oauth_reddit
diffChangeLogFile=src/main/resources/liquibase-diff-changeLog.xml
referenceDriver=org.h2.Driver
referenceUsername=sa
referencePassword=
```

## To roll back any changes

```
create the liquibase.rollback-file file in Spring Boot and generate a rollback script for changes associated with changesets
Ex:
-- rollback drop table test_table;
```
