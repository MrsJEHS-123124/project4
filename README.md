# Soul-Fuel
* Soul-Fuel is a spiritually uplifting web application built with:
  -React, Express, and MySQL.
* Soul-Fuel offers categorized scripture verses to guide and encourage users in their day to day lives, 
  powered by full-stack development with purpose driven design created so that adding new features will
  be a simple and easy task in the future. 

# Features
* Browse scripture verses by category
* Responsive design for desktop and mobile device
* API-connected backend with dynmaic verse  rendering
* Expandable architecture for adding future features such as:
  - Prayer Requests and even Pastoral support like couseling to help prevent suicide, or get resources to 
    people fighting substance abuse or depression! (Big Hopes to Help People In the Future)


# Technologies Used
* Frontend: React.js, Bootstrap 5, Custom CSS
* Backend: Express.js, Node.js, RESTful Routes
* Database: MySQL, Sequelize or Manual Schema, Relational Tables

# Installation
1. Clone The Repository
2. Install Dependencies
   Frontend: 'npm install' in cd client
   Backend:  'npm install' in cd server
3. Start the Backend   
   'nodemon server' in cd server
4. Start the Frontend 
   'npm start' in cd client
5. Vist the App
   Open 'http://localhost:3000' in your browser

# Future Enhancements
* Guided prayer request form
* AI-driven encouragement and mentorship tools 
* Pastoral couseling integration
* Resource Libraries and Connections (substance use rehab ceneters, mental health recourses, ect..)      
* Searchable Verse Library

# Creator 
** Jessica E.H. Smith **
Full-stack Developer in training
Connect with me on [LinkedIn]www.linkedin.com/in/jessicaehsmith

# License 
* This project is open-source and available for personal or educational use. All spiritual content and scripture 
  is used respectfully for encouragement  purposes.

## Database Script
```
CREATE TABLE `categories` (
  `id` int NOT NULL AUTO_INCREMENT,
  `name` varchar(100) NOT NULL,
  PRIMARY KEY (`id`)
) 

CREATE TABLE `users` (
  `id` int unsigned NOT NULL AUTO_INCREMENT,
  `username` varchar(50) NOT NULL,
  `email` varchar(100) NOT NULL,
  `password` varchar(255) NOT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `username` (`username`),
  UNIQUE KEY `email` (`email`)
) 

CREATE TABLE `verses` (
  `id` int NOT NULL AUTO_INCREMENT,
  `category_id` int DEFAULT NULL,
  `verse_text` text,
  PRIMARY KEY (`id`),
  KEY `category_id` (`category_id`),
  CONSTRAINT `verses_ibfk_1` FOREIGN KEY (`category_id`) REFERENCES `categories` (`id`)
) 
```