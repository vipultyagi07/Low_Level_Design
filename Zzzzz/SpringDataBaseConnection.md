 # A. Database-connection -MY Sql
 
    spring.datasource.url=jdbc:mysql://localhost:3306/databse_name
    spring.datasource.username=root(username)
    spring.datasource.password=root(password)
    spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# B. JPA Setting

    spring.jpa.database-platform=org.hibernate.dialect.MySQLDialect
    spring.jpa.hibernate.ddl-auto=none   
    spring.jpa.show-sql=true
    spring.jpa.properties.hibernate.format_sql=true

