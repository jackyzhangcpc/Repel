![ ](images/logo.png)

## Table of Contents

 - Overview
 - Installation
 - Functionality
	 - Authentication
	 - Commands
		 - Administrative Commands
		 - Student Commands
- Changelog

## Overview

Repel is an application designed to simplify the management of student grades and school databases, providing an intuitive and user-friendly platform for educators, administrators, and students alike. Repel streamlines complex processes and enhances user experiences, making academic management more efficient and accessible.

To ensure the security and integrity of sensitive student and school data, robust authentication and encryption is implemented into Repel's software architecture.

## Installation

Repel requires the following resources:

 - JDK (latest release, download from: https://www.oracle.com/ca-en/java/technologies/downloads/)
 - VSCode for Java (follow the instructions here to install it: https://code.visualstudio.com/docs/languages/java)
 - GSON (latest release, follow the instructions here to install it: https://github.com/google/gson)
	 - Adding GSON `.jar` file to your VSCode: https://www.youtube.com/watch?v=Kqs84TDnjSE

To install and run Repel, follow these steps:
1. Use the "Download Zip" button available through the main repository page to download the project
2. Navigate to your file manager and unzip the project
3. Open VSCode and click "Open Folder" under the Start menu or under File in the top right. Find the project folder and select.
4. Add the GSON `.jar` file into your VSCode project (https://www.youtube.com/watch?v=Kqs84TDnjSE)
5. In the Explorer (left directory bar), under `src`, click into `Driver.java` and run the code (top right, play button).

## Functionality

In Repel, school administrators play a pivotal role in facilitating secure access for students by assigning them unique IDs (usernames) and passwords to log into the platform. This process ensures that each student has personalized credentials for accessing their academic information and engaging with the platform's features. Additionally, administrators are responsible for maintaining an up-to-date database by adding new students as they join the educational institution.

### Authentication

Repel will ask users to enter their ID and password before allowing access into the platform.  
1. When given the `Enter your ID: ` prompt, enter the ID given to you by your administrator.
2. When given the `Enter your password: ` prompt, enter the password given to you by your administrator.

If this process is successful, you'll be redirected to a student landing page.

### Commands

Commands in Repel will vary depending on the type of account you log in to. Administration accounts have the ability to view and modify student information and grades. Student accounts only have the ability to view their own information.

**Administrative commands include:**

 - `add` - adds a student to the student database
	 - Repel will prompt user to input `student name` and `grade level`
	 - Adding a student to the database will automatically generate a unique ID and password
 - `remove` - removes a student from the student database
	 - Repel will prompt user to input `student id` for removal
	 - All student data will be completely removed
 - `modify` - modify existing student information and grades 
	 - Repel will prompt user to input `student id` for modification
	 - Admins will have the ability to,... 
		 - modify the student's name, grade level, and grades
		 - view student information including grades (highest grade, grade average, all assignments)
 - `view` - view all students and respective IDs in student database 
	 - Admins should use this command to find student IDs for modifying or removing a student
 - `exit` - exit platform

> NOTE: All student IDs are encrypted, as they are the key to accessing
> student information.

**Student commands include:**
- `view` - view student's information (name, grade, id, and password)
- `grades` - view student's grades (assignments, average, and highest grade)
- `exit` - exit platform

## Changelog

### [0.0.1] - 03/07/2024
#### Added
- Administrative account interface
- Student class with name, grade level, grades, and student ID objects
- IOStream class handling inputs and outputs
- Simple navigation and functionality
#### Changed
#### Fixed

---

### [0.0.2] - 03/14/2024
#### Added
- GSON Handling
	- Saving student info into JSON database
#### Changed
#### Fixed
- Removed repeating student IDs

---
### [0.0.3] - 03/27/2024
#### Added
- Authentication and Encryption
	- Log in - added password object to Student class
	- Student IDs encrypted in JSON file
- Student account interface
	- Viewing info and grades
#### Changed
- JSON Handler class implementing encryption and decryption
- Driver code includes authentication before menu UI
#### Fixed