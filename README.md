# University Management System

A comprehensive Java Swing-based desktop application for managing university operations including student records, faculty management, examination system, and administrative tasks.

## 📸 Application Screenshots

### Login System
![IMG-20250806-WA0050](https://github.com/user-attachments/assets/e5a7a46b-96f8-493d-8ce1-74b8e5351e8a)

*Secure authentication system with username and password*

### Faculty Management
![IMG-20250806-WA0051](https://github.com/user-attachments/assets/edae3c4a-1c78-469e-9a39-fb2842dd5ac9)

*Add new faculty members with comprehensive details*

![Teacher Details]
![IMG-20250806-WA0044](https://github.com/user-attachments/assets/e86c959f-096b-4777-b6d5-d394c6965d4c)

*View and search faculty information*

![Update Teacher]
![IMG-20250806-WA0049](https://github.com/user-attachments/assets/5f8df5d4-de07-4919-81cf-96c3cd344519)

*Modify existing faculty records*

### Main Dashboard
![Main Interface]
![IMG-20250806-WA0046](https://github.com/user-attachments/assets/92cf83ff-0f3f-4834-82f0-d76aaad06fa3)

*University campus view with comprehensive menu system*

### Qualification Selection
![IMG-20250806-WA0048](https://github.com/user-attachments/assets/79de05c7-7a8b-4fdc-9c06-9260cb9b338c)

*Comprehensive qualification options for faculty*

### Search Employee
By id![IMG-20250806-WA0045](https://github.com/user-attachments/assets/a29c3d91-5fb6-4f96-ae25-862633c7a94f)



## 🚀 Features

### Student Management
- **Add New Students**: Register new students with personal and academic details
- **Student Details**: View and search student information
- **Update Student Info**: Modify existing student records
- **Student Leave Management**: Handle student leave requests and approvals

### Faculty Management
- **Add Faculty**: Register new teaching staff
- **Faculty Details**: View faculty information and records
- **Update Faculty Info**: Modify faculty details
- **Teacher Leave Management**: Manage faculty leave requests

### Academic System
- **Enter Marks**: Input student examination scores
- **Examination Details**: View and manage exam information
- **Marks Display**: Show student grades and performance

### Financial Management
- **Fee Structure**: Define and manage fee categories
- **Student Fee Form**: Handle fee payments and records

### System Features
- **Secure Login**: Authentication system for authorized access
- **Splash Screen**: Professional application startup
- **About Section**: Application information and credits

## 🛠️ Technology Stack

- **Language**: Java
- **GUI Framework**: Java Swing
- **Database**: MySQL
- **JDBC Driver**: MySQL Connector/J 8.0.28
- **Additional Libraries**: 
  - JCalendar (Date picker)
  - ResultSet2xml (Data export)

## 📋 Prerequisites

Before running this application, ensure you have:

1. **Java Development Kit (JDK)** - Version 8 or higher
2. **MySQL Server** - Version 5.7 or higher
3. **MySQL Connector/J** - Version 8.0.28 (included in project)
4. **IDE** (Optional) - IntelliJ IDEA, Eclipse, or NetBeans

## 🗄️ Database Setup

### 1. Install MySQL Server
Download and install MySQL Server from [MySQL Official Website](https://dev.mysql.com/downloads/mysql/)

### 2. Create Database
```sql
-- Connect to MySQL as root user
mysql -u root -p

-- Create the database
CREATE DATABASE universitymanagement;

-- Use the database
USE universitymanagement;

-- Create necessary tables (examples)
CREATE TABLE student (
    rollno VARCHAR(20) PRIMARY KEY,
    name VARCHAR(100),
    fname VARCHAR(100),
    classX VARCHAR(10),
    classXII VARCHAR(10),
    aadhar VARCHAR(20),
    email VARCHAR(100),
    phone VARCHAR(15),
    address TEXT,
    course VARCHAR(50),
    branch VARCHAR(50)
);

CREATE TABLE teacher (
    empId VARCHAR(20) PRIMARY KEY,
    name VARCHAR(100),
    fname VARCHAR(100),
    age VARCHAR(10),
    dob VARCHAR(20),
    address TEXT,
    phone VARCHAR(15),
    email VARCHAR(100),
    classX VARCHAR(10),
    classXII VARCHAR(10),
    aadhar VARCHAR(20),
    education VARCHAR(100),
    department VARCHAR(50)
);

CREATE TABLE login (
    username VARCHAR(50) PRIMARY KEY,
    password VARCHAR(50)
);

-- Insert default admin user
INSERT INTO login VALUES ('admin', 'admin');
```

### 3. Database Configuration
The application connects to MySQL with these default settings:
- **Host**: localhost
- **Port**: 3306
- **Database**: universitymanagement
- **Username**: root
- **Password**: 123456

To change these settings, modify the `Conn.java` file:
```java
connection = DriverManager.getConnection("jdbc:mysql://localhost:3306/universitymanagement","root","123456");
```

## 🚀 Installation & Setup

### Method 1: Using IDE (Recommended)

1. **Clone/Download the project**
   ```bash
   git clone <repository-url>
   # or download and extract the ZIP file
   ```

2. **Open in IDE**
   - Open IntelliJ IDEA/Eclipse
   - Import the project folder
   - Ensure JDK is configured

3. **Add Dependencies**
   - The project includes required JAR files
   - Ensure MySQL Connector/J is in the classpath

4. **Run the Application**
   - Navigate to `src/university/management/system/Splash.java`
   - Run the main method

### Method 2: Command Line

1. **Navigate to project directory**
   ```bash
   cd universitymanagment-system-main
   ```

2. **Compile the project**
   ```bash
   javac -cp "src;lib/*" src/university/management/system/*.java
   ```

3. **Run the application**
   ```bash
   java -cp "src;lib/*" university.management.system.Splash
   ```

## 🖥️ Usage

### First Time Setup
1. Start the application
2. The splash screen will appear with animation
3. Login with default credentials:
   - **Username**: admin
   - **Password**: admin

### Main Operations

#### Adding Students
1. Click "Add Student" from main menu
2. Fill in all required fields
3. Submit the form

#### Managing Faculty
1. Access "Add Faculty" option
2. Enter faculty details
3. Save the information

#### Entering Marks
1. Select "Enter Marks"
2. Choose student and subject
3. Input marks and save

#### Viewing Reports
1. Use "Student Details" or "Faculty Details"
2. Search and filter as needed
3. Export data if required

## 📁 Project Structure

```
universitymanagment-system-main/
├── src/
│   ├── icon/                    # Application icons and images
│   └── university/management/system/
│       ├── About.java           # About dialog
│       ├── AddFaculty.java      # Add faculty form
│       ├── AddStudent.java      # Add student form
│       ├── Conn.java           # Database connection
│       ├── EnterMarks.java     # Marks entry form
│       ├── ExaminationDetails.java # Exam details
│       ├── FreeStructure.java  # Fee structure
│       ├── Login.java          # Login system
│       ├── Marks.java          # Marks display
│       ├── Splash.java         # Splash screen
│       ├── StudentDetails.java # Student information
│       ├── StudentFeeForm.java # Fee management
│       ├── StudentLeave.java   # Student leave
│       ├── TeacherDetails.java # Faculty information
│       ├── TeacherLeave.java   # Faculty leave
│       ├── UpdateTeacher.java  # Update faculty
│       ├── main_class.java     # Main application
│       └── updateStudent.java  # Update student
├── lib/                        # External libraries
├── .gitignore
├── universitymanagment system.iml
└── README.md
```

## 🔧 Troubleshooting

### Common Issues

#### Database Connection Error
- Verify MySQL server is running
- Check database credentials in `Conn.java`
- Ensure database `universitymanagement` exists

#### ClassNotFoundException
- Verify MySQL Connector/J is in classpath
- Check if all required JAR files are included

#### GUI Display Issues
- Ensure proper Java version (8+)
- Check system display settings
- Verify Swing components are supported

#### Compilation Errors
- Confirm JDK is properly installed
- Check classpath configuration
- Verify all source files are present

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 👥 Support

For support and questions:
- Create an issue in the repository
- Check the troubleshooting section
- Review the code documentation

## 🔮 Future Enhancements

- Web-based interface
- Mobile application
- Advanced reporting features
- Email notifications
- Backup and restore functionality
- Multi-language support

---

**Note**: This application is designed for educational purposes and small to medium-sized institutions. For large-scale deployment, consider additional security measures and performance optimizations.
