# Cypress Crash Course Repository

Welcome to the **Cypress Crash Course** repository! This project is designed to help you get started with **Cypress**, a powerful end-to-end testing framework for modern web applications. Whether you're a beginner or an experienced developer, this repository provides a hands-on guide to writing, running, and automating tests using Cypress.

---

## 🚀 Key Features
- **Beginner-Friendly**: Step-by-step tutorials and examples to help you learn Cypress from scratch.
- **Real-World Examples**: Practical test cases for web applications, including form submissions, UI interactions, and API testing.
- **Modular and Organized**: Clean and well-structured codebase for easy understanding and reuse.
- **Comprehensive Documentation**: Each test case includes detailed explanations and comments.

---

## 🛠️ Technologies and Tools Used
- **Testing Framework**: Cypress
- **Programming Language**: JavaScript
- **Tools**: Cypress Test Runner, Node.js, npm
- **Other Libraries**: Mocha (for assertions), Chai (for BDD/TDD assertions)

---

## 📂 Repository Structure
Here’s an in-depth overview of the repository structure:

```
Cypress-crash-course/
├── cypress/
│   ├── fixtures/            # Test data (e.g., JSON files)
│   ├── integration/         # Test scripts
│   ├── plugins/             # Custom plugins and configurations
│   ├── support/             # Reusable functions and commands
├── node_modules/            # Installed dependencies
├── cypress.json             # Cypress configuration file
├── package.json             # Project dependencies and scripts
├── README.md                # This file
```

### **In-Depth Sub-Folder Descriptions**

#### **1. `cypress/fixtures/`**
   - **Purpose**: This folder contains static test data used in your Cypress tests. Fixtures are typically JSON files that store data like user credentials, API responses, or form inputs.
   - **Example Files**:
     - `users.json`: Contains sample user data for login tests.
     - `api-responses.json`: Stores mock API responses for testing.

#### **2. `cypress/integration/`**
   - **Purpose**: This folder contains all your test scripts. Each file in this directory represents a test suite or a specific test case.
   - **Example Files**:
     - `login.spec.js`: Tests the login functionality of a web application.
     - `form.spec.js`: Tests form submissions and validations.
     - `api.spec.js`: Tests REST API endpoints.

#### **3. `cypress/plugins/`**
   - **Purpose**: This folder is used to extend Cypress functionality by adding custom plugins or modifying the default behavior of Cypress.
   - **Example Files**:
     - `index.js`: Custom plugin to integrate with other tools or frameworks.
     - `browserify.js`: Example plugin for bundling JavaScript files.

#### **4. `cypress/support/`**
   - **Purpose**: This folder contains reusable functions, custom commands, and global configurations that can be used across multiple test files.
   - **Example Files**:
     - `commands.js`: Custom Cypress commands (e.g., `cy.login()` for reusable login functionality).
     - `index.js`: Global configurations and imports for all test files.

#### **5. `node_modules/`**
   - **Purpose**: This folder contains all the dependencies installed via npm. It is automatically generated when you run `npm install`.

#### **6. `cypress.json`**
   - **Purpose**: This file contains the configuration settings for Cypress, such as base URL, viewport size, and environment variables.
   - **Example Configuration**:
     ```json
     {
       "baseUrl": "https://example.com",
       "viewportWidth": 1280,
       "viewportHeight": 720
     }
     ```

#### **7. `package.json`**
   - **Purpose**: This file defines the project dependencies, scripts, and metadata. It is used by npm to manage the project.
   - **Example Scripts**:
     ```json
     {
       "scripts": {
         "test": "cypress run",
         "open": "cypress open"
       }
     }
     ```

---

## 🧑‍💻 Getting Started

### Prerequisites
- Node.js (v12 or higher)
- npm (Node Package Manager)
- A modern web browser (e.g., Chrome, Firefox)

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/waseemofficial/Cypress-crash-course.git
   cd Cypress-crash-course
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Open Cypress Test Runner:
   ```bash
   npx cypress open
   ```

---

## 🧑‍💻 Example Test Cases

### 1. **Login Test**
   - **Description**: Automates the login process for a web application.
   - **File**: `cypress/integration/login.spec.js`
   - **Code**:
     ```javascript
     describe('Login Test', () => {
       it('should log in successfully', () => {
         cy.visit('/login');
         cy.get('#username').type('testuser');
         cy.get('#password').type('password123');
         cy.get('#login-button').click();
         cy.url().should('include', '/dashboard');
       });
     });
     ```

### 2. **Form Submission Test**
   - **Description**: Tests the submission of a contact form.
   - **File**: `cypress/integration/form.spec.js`
   - **Code**:
     ```javascript
     describe('Form Submission Test', () => {
       it('should submit the form successfully', () => {
         cy.visit('/contact');
         cy.get('#name').type('John Doe');
         cy.get('#email').type('john.doe@example.com');
         cy.get('#message').type('This is a test message.');
         cy.get('#submit-button').click();
         cy.get('.success-message').should('be.visible');
       });
     });
     ```

### 3. **API Testing**
   - **Description**: Tests a REST API endpoint.
   - **File**: `cypress/integration/api.spec.js`
   - **Code**:
     ```javascript
     describe('API Test', () => {
       it('should return a 200 status code', () => {
         cy.request('GET', 'https://jsonplaceholder.typicode.com/posts/1')
           .then((response) => {
             expect(response.status).to.eq(200);
             expect(response.body).to.have.property('title');
           });
       });
     });
     ```

---

## 📸 Screenshots

### Cypress Test Runner
![Cypress Test Runner](https://via.placeholder.com/600x300.png?text=Cypress+Test+Runner+Interface)

### Test Execution
![Test Execution](https://via.placeholder.com/600x300.png?text=Test+Execution+Output)

---

## 📜 License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments
- The Cypress team for creating an amazing testing framework.
- The open-source community for providing valuable resources and tools.

---
