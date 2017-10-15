# UtilityJars Repository
A collection of all my Utility JARS which are used frequently for development

## DBConnect.jar
This JAR contains the common code for making connection to the Database. It also provides the handle for INSERT, UPDATE, DELETE and QUERY.

### How to use DBConnect.jar
- Add JAR to your classpath.
- Create `db.properties` file under `src/main/resources` folder of your project.
- Insert below provided values to your properties file:
  * `db.driver=com.mysql.jdbc.Driver`
  * `db.url=jdbc:mysql://localhost:3306/test`
  * `db.username=root`
  * `db.password=`
- That is all

### How to perform Insert Queries
```
public void itShouldInsertDataIntoTheDatabase() throws SQLException {
    InsertImpl insertHandler = new InsertImpl();
		String sql = "INSERT INTO sn_roles (ROLE_NAME) VALUES (?) ";
		insertHandler.prepareStmt(sql);
		insertHandler.addParams("Boss");
		boolean flag = insertHandler.execute();
 }
 ```
 
 ### How to Perform Select Queries
 ```
 public void itShouldConnectToDatabaseAndExecuteSelectQuery() throws SQLException {
    QueryImpl queryHandler = new QueryImpl();
		String sql = "SHOW TABLES";
		queryHandler.prepareStmt(sql);
		ResultSet rs = queryHandler.executeQuery();
 }
 ```
