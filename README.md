# 🚖Taxi Service🚕

Web-application that supports authentication, registration and other CRUD operations.

## 🚀 Features

- Authentication
- Create and delete car manufacturer
- Create and delete cars
- Create and delete drivers
- Add drivers to specific cars
- View all cars belonging to the current driver
- View all cars, drivers, manufacturers

## 🔧Structure
#### Project has N-Tier Architecture:
| Layer                            | Assignment                                                                                                                                 |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| Controllers (Presentation layer) | Receives requests from the client, transmits them to the service layer, and returns JSP pages in response.                                 |
| Services (Application layer)     | Receives requests from the controller layer, transmits them to the DAO layer, <br/>receives a response from the DAO, and executes business |
| DAO (Data access layer)          | Receives requests from the service layer, transfers them to the database, and executes SQL queries                                         |


| Controller                    | Path                  | Action                                |
|-------------------------------|-----------------------|---------------------------------------|
| LoginController               | /login                | authentication                        |
| LogoutController              | /logout               | invalidate current session            |
|                               |                       |                                       |
| AddCarController              | /cars/add             | adds a new car                        |
| AddDriverToCarController      | /cars/drivers/add     | adds a driver to a certain car        |
| DeleteCarController           | /cars/delete          | deletes car                           |
| GetAllCarsController          | /cars                 | views all cars                        |
|                               |                       |                                       |
| AddDriverController           | /drivers/add          | adds a driver                         |
| DeleteDriverController        | /drivers/delete       | deletes driver                        |
| GetAllDriversController       | /drivers              | views all drivers                     |
| GetMyCurrentCarsController    | /drivers/cars         | views all cars for the current driver |
|                               |                       |                                       |
| AddManufacturersController    | /manufacturers/add    | adds new manufacturer                 |
| DeleteManufacturerController  | /manufacturers/delete | deletes manufacturer                  |
| GetAllManufacturersController | /manufacturers        | views all manufacturers               |
|                               |                       |                                       |
| IndexController               | / & /index            | show all corresponding pages          |

#### DataBase architecture:
<img src="DB_EER_Diagram.png" alt="database architecture">

## ⚙️Used technologies
- Java 18
- JDBC
- JSP
- JSTL 1.2
- Maven 4.0.0
- MySQL 8.0.28
- Servlet Api 4.0.1
- Tomcat 9.0.76

## 🔨How to run and test this web application?
1. Install the necessary software: JDK, Maven, MySQL, and Tomcat.
2. Download this project to your computer.
3. Create a database using either a local MySQL installation or a remote database. Execute the schema provided in the init_db.sql file to set up the necessary tables and structure for the project.
4. Change the settings in the `ConnectionUtil` file to your personal ones.
    ```
    private static final String URL = "jdbc:mysql://localhost:3306/taxi_service_db"; //or your other URL
    private static final String USERNAME = "YOUR USERNAME";
    private static final String PASSWORD = "YOUR PASSWORD";
    private static final String JDBC_DRIVER = "com.mysql.cj.jdbc.Driver"; //or any other driver you need
    ```
5. Set up the configuration for Tomcat.
6. Run the project
 