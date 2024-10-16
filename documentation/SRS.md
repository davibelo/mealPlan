# Software Requirements Specification (SRS)

## 1. Introduction

### 1.1 Purpose
The purpose of this document is to provide a detailed description of the system being developed, which allows users to register, manage recipes, and generate a shopping list based on selected recipes and desired quantities. This document will outline the system's functionality, constraints, performance expectations, and design decisions. It will serve as a blueprint for development and guide the project from initial planning through to deployment.

### 1.2 Scope
This system is a web application that allows users to:
- Register and log in to the system.
- Create and manage their personal recipes, including adding ingredients, quantities, and instructions.
- Select multiple recipes and specify desired final weight for each one.
- Automatically calculate required ingredient quantities and generate a consolidated grocery list.
- Save and export the grocery list.

The system is intended to be responsive, accessible via desktop and mobile browsers. It will be developed using Django for the backend and React for the frontend, and will use PostgreSQL for data storage.

### 1.3 Definitions, Acronyms, and Abbreviations
- **SRS**: Software Requirements Specification.
- **API**: Application Programming Interface.
- **CRUD**: Create, Read, Update, Delete.

### 1.4 References
- Agile Development Practices.
- React and Django Documentation.

---

## 2. Overall Description

### 2.1 Product Perspective
The system is a standalone web application that provides recipe management and shopping list functionality. It will integrate with third-party services such as email providers for user authentication and password recovery.

### 2.2 Product Features
- **User Authentication**: Registration, login, logout, and password recovery via email.
- **Recipe Management**: Users can add, edit, view, and delete recipes.
- **Recipe Selection**: Users can select recipes and specify the desired final weight of the dish.
- **Grocery List Generation**: Based on selected recipes and weights, the system will calculate ingredient quantities and generate a consolidated shopping list.
- **Export Options**: Users can export grocery lists in formats such as PDF.

### 2.3 User Classes and Characteristics
- **Regular Users**: Can register, log in, manage recipes, and generate shopping lists.
- **Admin Users**: Can manage the platform, user accounts, and monitor overall system health.

### 2.4 Operating Environment
The system will run in a browser environment and be compatible with:
- **Browsers**: Chrome, Firefox, Safari, and Edge (latest versions).
- **Operating Systems**: Windows, macOS, Linux, iOS, and Android.
- **Database**: PostgreSQL.
- **Backend**: Django (Python).
- **Frontend**: React (JavaScript).

### 2.5 Design and Implementation Constraints
- The system must be responsive, supporting both desktop and mobile layouts.
- The database will be PostgreSQL, and the system should be designed to handle up to 1000 concurrent users.
- The system should ensure security and comply with data protection standards.

### 2.6 Assumptions and Dependencies
- Users will have internet access to use the system.
- The system depends on third-party email services for password recovery.
- It is assumed that the majority of users will access the system via modern web browsers.

---

## 3. Specific Requirements

### 3.1 Functional Requirements

#### 3.1.1 User Authentication
- **FR1.1**: The system must allow users to register with an email and password.
- **FR1.2**: Users must be able to log in and log out of the system.
- **FR1.3**: Users must be able to recover their password by providing their email.

#### 3.1.2 Recipe Management
- **FR2.1**: Users must be able to create a recipe by providing a title, list of ingredients with quantities, final weight of the recipe, and instructions.
- **FR2.2**: Users must be able to view their list of recipes.
- **FR2.3**: Users must be able to edit or delete recipes they have created.

#### 3.1.3 Recipe Selection and Quantity Adjustment
- **FR3.1**: Users must be able to select one or more recipes from their list.
- **FR3.2**: Users must be able to specify the desired final weight of each recipe.
- **FR3.3**: The system must automatically adjust the ingredient quantities based on the specified final weight.

#### 3.1.4 Grocery List Generation
- **FR4.1**: The system must generate a grocery list based on selected recipes and quantities.
- **FR4.2**: The grocery list must consolidate common ingredients across recipes.
- **FR4.3**: Users must be able to save grocery lists for future reference.

#### 3.1.5 Export Grocery List
- **FR5.1**: The system must allow users to export grocery lists in PDF format.

---

### 3.2 Non-Functional Requirements

#### 3.2.1 Performance
- **NFR1.1**: The system must respond to user requests within 2 seconds under normal load conditions.
- **NFR1.2**: The system must support up to 1000 concurrent users.

#### 3.2.2 Security
- **NFR2.1**: User passwords must be stored using strong encryption (e.g., bcrypt).
- **NFR2.2**: The system must use HTTPS for all communications.
- **NFR2.3**: The system must be protected from common web vulnerabilities (e.g., CSRF, XSS).

#### 3.2.3 Usability
- **NFR3.1**: The system must have a responsive design that works on both desktop and mobile devices.
- **NFR3.2**: The interface must be user-friendly and intuitive.

#### 3.2.4 Scalability
- **NFR4.1**: The system must be able to scale horizontally to handle increased traffic.
- **NFR4.2**: The architecture must allow easy addition of new features without significant refactoring.

---

## 4. System Models

### 4.1 Use Case Diagram
A high-level use case diagram would illustrate:
- **Actors**: Users and Admins.
- **Use Cases**: Register, login, manage recipes, select recipes, generate grocery list, export grocery list.

### 4.2 Class Diagram
A class diagram would represent entities like User, Recipe, Ingredient, and ShoppingList, with relationships and attributes.

---

## 5. Glossary
- **Recipe**: A collection of ingredients with instructions to prepare a dish.
- **Grocery List**: A consolidated list of ingredients required to prepare selected recipes.
- **Ingredient**: A single food item used in a recipe, along with its quantity and unit of measurement.
