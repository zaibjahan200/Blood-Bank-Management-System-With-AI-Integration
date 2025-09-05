# Blood Bank Management System

A comprehensive Java-based desktop application for efficient blood bank management.

***

This Blood Bank Management System is a robust and user-friendly application developed in Java, designed to streamline the process of managing blood donations, and inventory, and searching for donors. The application provides a centralized platform for blood bank administrators to handle day-to-day operations with ease.

## Key Features

- **Donor Management**: Easily add new donors, update their information, and manage their records.
- **Blood Inventory Control**: Keep track of the blood stock with features to increase or decrease inventory levels.
- **Advanced Search**: Quickly find donors based on their location or blood group.
- **Secure Access**: The system is protected by a login screen to ensure that only authorized personnel can access the data.

## Technologies Used

- **Java Swing**: For the graphical user interface.
- **MySQL**: As the database for storing all the information.
- **JDBC**: For database connectivity.

## Getting Started

To get the application up and running, follow these simple steps.

### Prerequisites

- **Java Development Kit (JDK)**: Ensure you have JDK 8 or a later version installed.
- **MySQL**: A running instance of the MySQL database server.
- **MySQL Connector/J**: The official JDBC driver for MySQL.

### Installation

1. **Clone the repository**:
   ```sh
   git clone https://github.com/your-username/blood-bank-management-system.git
   ```
2. **Database Setup**:
   - Create a new database in MySQL named `bbms`.
   - The application uses the following credentials by default:
     - **Username**: `root`
     - **Password**: `root`
   - You can modify the database configuration in `src/Project/ConnectionProvider.java`.

   - **Database Schema**: You need to create two tables in the `bbms` database: `donor` and `stock`. Use the following SQL commands to create them:

     ```sql
     CREATE TABLE donor (
       donorId INT NOT NULL,
       name VARCHAR(255),
       fatherName VARCHAR(255),
       motherName VARCHAR(255),
       DOB VARCHAR(20),
       MobileNo VARCHAR(20),
       gender VARCHAR(10),
       email VARCHAR(255),
       bloodGroup VARCHAR(5),
       city VARCHAR(255),
       address TEXT,
       PRIMARY KEY (donorId)
     );

     CREATE TABLE stock (
       bloodGroup VARCHAR(5) NOT NULL,
       units INT,
       PRIMARY KEY (bloodGroup)
     );
     ```

   - **Initial Stock Data**: After creating the `stock` table, you need to populate it with the available blood groups.

     ```sql
     INSERT INTO stock (bloodGroup, units) VALUES
     ('A+', 0),
     ('A-', 0),
     ('B+', 0),
     ('B-', 0),
     ('O+', 0),
     ('O-', 0),
     ('AB+', 0),
     ('AB-', 0);
     ```

3. **Run the Application**:
   - Open the project in your favorite Java IDE (e.g., NetBeans, Eclipse).
   - Locate and run the `Login.java` file to start the application.
   - Use the following credentials to log in:
     - **Username**: `Admin`
     - **Password**: `admin`

## Contributing

Contributions are welcome! If you have any suggestions or improvements, feel free to fork the repository and submit a pull request.
