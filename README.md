# liquidbasestarter
LiquidBase  DB  Changelog   Starter

##  Docs
- https://www.baeldung.com/liquibase-refactor-schema-of-java-app
- https://docs.liquibase.com/tools-integrations/springboot/using-springboot-with-maven.html
- https://reflectoring.io/database-migration-spring-boot-liquibase/


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

## application.properties

```
spring.liquibase.change-log=classpath:liquibase-changeLog.xml   *.sql or xml or json or yaml
spring.liquibase.enabled=false

```

## liquibase.properties

```
Windows example: changelog-file: ..\path\to\changelog.sql
Linux example: changelog-file: ../path/to/changelog.sql

url=jdbc:mysql://localhost:3306/oauth_reddit
username=tutorialuser
password=tutorialmy5ql
driver=com.mysql.jdbc.Driver
outputChangeLogFile=src/main/resources/liquibase-outputChangeLog.xml
```
## Changelog example

```xml

<?xml version="1.0" encoding="UTF-8"?>
<databaseChangeLog
	xmlns="http://www.liquibase.org/xml/ns/dbchangelog"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xmlns:ext="http://www.liquibase.org/xml/ns/dbchangelog-ext"
	xmlns:pro="http://www.liquibase.org/xml/ns/pro"
	xsi:schemaLocation="http://www.liquibase.org/xml/ns/dbchangelog
		http://www.liquibase.org/xml/ns/dbchangelog/dbchangelog-latest.xsd
		http://www.liquibase.org/xml/ns/dbchangelog-ext http://www.liquibase.org/xml/ns/dbchangelog/dbchangelog-ext.xsd
		http://www.liquibase.org/xml/ns/pro http://www.liquibase.org/xml/ns/pro/liquibase-pro-latest.xsd">
    <changeSet id="1" author="Liquibase">
    <createTable tableName="test_table">
           <column name="test_id" type="int">
                 <constraints primaryKey="true"/>
           </column>
           <column name="test_column" type="varchar"/>
    </createTable>
    </changeSet>
</databaseChangeLog>
```
## Generate a ChangeLog From an Existing Database

```
mvn liquibase:generateChangeLog
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
