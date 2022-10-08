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

## To roll back any changes

```
create the liquibase.rollback-file file in Spring Boot and generate a rollback script for changes associated with changesets
```

## To roll back any changes

```
create the liquibase.rollback-file file in Spring Boot and generate a rollback script for changes associated with changesets
Ex:
-- rollback drop table test_table;
```
