# 🌱 Agri-Energy Connect

**Agri-Energy Connect** is a web application designed to connect farmers and employees, enabling efficient management of agricultural products while promoting sustainable farming practices. Built as a university project, this app provides a user-friendly platform for farmers to manage products and employees to oversee farmer profiles, with a focus on eco-friendly agriculture. The app features a modern, responsive UI with consistent styling across all pages, secure authentication, and role-based access control.

📅 **Last Updated**: May 13, 2025  
📍 **Developed by**: Joshua Ryan Pillay 
🎓 **Purpose**: Campus project submission

---

## 📑 Table of Contents

- [🌱 Agri-Energy Connect](#-agri-energy-connect)
  - [📑 Table of Contents](#-table-of-contents)
  - [✨ Features](#-features)
  - [🛠️ Technologies Used](#️-technologies-used)
  - [📦 Prerequisites](#-prerequisites)
  - [⚙️ Installation](#️-installation)
    - [1. Clone the Repository](#1-clone-the-repository)
    - [2. Set Up the Database](#2-set-up-the-database)
    - [3. Configure the Connection String](#3-configure-the-connection-string)
    - [4. Install Dependencies](#4-install-dependencies)
    - [5. Apply Migrations](#5-apply-migrations)
    - [6. Run the Application](#6-run-the-application)
  - [🚀 Usage](#-usage)
    - [User Roles](#user-roles)
    - [Sample Credentials](#sample-credentials)
    - [Key Pages](#key-pages)
  - [🎨 UI Design](#-ui-design)
  - [📸 Screenshots](#-screenshots)
  - [🤝 Contributing](#-contributing)
  - [📜 License](#-license)
  - [📞 Contact](#-contact)

---

## ✨ Features

Agri-Energy Connect offers a range of features to support sustainable agriculture:

- **🌍 User Authentication**:
  - Secure login and registration for farmers and employees.
  - Role-based access control (Farmers and Employees).

- **👨‍🌾 Farmer Management**:
  - Employees can view a list of farmers, add new farmers, and see detailed farmer profiles (Name, Email, Phone, Address).
  - Includes a styled "Details" page for each farmer.

- **🌾 Product Management**:
  - Farmers can add, view, and delete agricultural products.
  - Filter products by category, start date, and end date.
  - Displays product name, category, production date, and associated farmer.

- **📜 Privacy Policy**:
  - A detailed privacy policy outlining data collection, usage, sharing, security practices, and contact information.

- **🎨 Modern UI Design**:
  - Consistent design across all pages with teal-to-cyan gradients (`#40c4ff` to `#00bcd4`) and deep navy blue accents (`#0288d1` to `#01579b`).
  - Card layouts, hover effects, and subtle fade-in animations for a dynamic user experience.
  - Responsive design for seamless use on desktops, tablets, and mobile devices.

- **🔒 Security**:
  - Anti-forgery tokens to prevent CSRF attacks.
  - Role-based authorization to restrict access to sensitive actions (e.g., only farmers can add/delete products, only employees can manage farmers).

---

## 🛠️ Technologies Used

- **Backend**:
  - ASP.NET Core 8 (C#)
  - Entity Framework Core (ORM)

- **Frontend**:
  - Razor Pages
  - Bootstrap 5 (CSS Framework)
  - Font Awesome 6.5.2 (Icons)
  - jQuery (for form validation and interactions)

- **Database**:
  - SQL Server (via SSMS)

- **Other**:
  - Markdown (for this README)

---

## 📦 Prerequisites

Before setting up the project, ensure you have the following installed:

- **Visual Studio 2022** (with ASP.NET and web development workload)
- **SQL Server** (e.g., SQL Server Express) and **SQL Server Management Studio (SSMS)**
- **.NET 8 SDK** (or later)
- **Git** (to clone the repository)

---

## ⚙️ Installation

Follow these steps to set up Agri-Energy Connect on your local machine.

### 1. Clone the Repository
Clone the project from GitHub to your local machine:

```bash
git clone https://github.com/yourusername/agri-energy-connect.git
cd agri-energy-connect
2. Set Up the Database
The database script (AgriEnergyConnect.sql) is included in the repository. To set it up:

Open SQL Server Management Studio (SSMS) and connect to your SQL Server instance.
Go to File > Open > File… and select AgriEnergyConnect.sql from the repository.
If the script specifies a file path for the database files (e.g., C:\Program Files\Microsoft SQL Server\...), modify the path to match your SQL Server data directory (e.g., C:\Your\SQL\Server\Data\Path\).
Click Execute (or press F5) to run the script. This will create the AgriEnergyConnect database with tables (Farmers, Products, etc.) and sample data.
Refresh the "Databases" node in Object Explorer to confirm the database is created.


3. Configure the Connection String
Open appsettings.json in the project root and update the connection string to match your SQL Server instance:

json

Copy
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=your_server_name;Database=AgriEnergyConnect;Trusted_Connection=True;"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "AllowedHosts": "*"
}
Replace your_server_name with your SQL Server instance name (e.g., localhost or .\SQLEXPRESS if using SQL Server Express).
If using SQL Server Authentication, replace Trusted_Connection=True with User Id=your_username;Password=your_password;.


4. Install Dependencies
Open the project in Visual Studio 2022:

Right-click the solution in Solution Explorer and select Restore NuGet Packages to install dependencies (e.g., Entity Framework Core, ASP.NET Core Identity).
Ensure the following packages are installed (check AgriEnergyConnect.csproj):
Microsoft.EntityFrameworkCore.SqlServer
Microsoft.EntityFrameworkCore.Design
Microsoft.AspNetCore.Identity.EntityFrameworkCore


5. Apply Migrations (Optional)
If you modify the database schema, apply migrations to update the database:

bash

Copy
dotnet ef migrations add InitialCreate
dotnet ef database update
However, since the provided .sql script already sets up the database, you can skip this step unless you make changes to the models.

6. Run the Application
In Visual Studio, press F5 (or click the "Run" button) to build and run the application.
The app should launch in your default browser at https://localhost:7111 (port may vary).
You’ll be redirected to the login page if not authenticated.
🚀 Usage
User Roles
Farmer:
Can add, view, and delete products.
Access the Products page to manage agricultural products.
Employee:
Can view, add, and see details of farmer profiles.
Access the Farmers page to manage farmers.
Sample Credentials
For testing purposes, you can use the following credentials (included in the database script):

Farmer:
Email: alice@example.com
Password: P@ssw0rd123!
Employee:
Email: test2@example.com
Password: P@ssw0rd123!
Key Pages
Login/Register: /Identity/Account/Login and /Identity/Account/Register for user authentication.
Homepage: / displays a welcome message, user role, and informational cards.
Farmers: /Farmers (employees only) to manage farmer profiles with view, add, and details functionality.
Products: /Products to view, add, and delete agricultural products, with filtering by category and date.
Privacy Policy: /Home/Privacy for privacy information.


🎨 UI Design
The Agri-Energy Connect web app features a modern, consistent UI design across all pages:

Color Scheme:
Teal-to-cyan gradients (#40c4ff to #00bcd4) for headers and backgrounds.
Deep navy blue gradients (#0288d1 to #01579b) for navbars, buttons, and accents.
Complementary blues (#0277bd, #01579b) for headings and interactive elements.
Layout:
Card-based design with rounded corners, shadows, and hover effects (lifting on hover).
Centered layouts for forms (login, register, create pages) with branding elements (company name, tagline, welcome message).
Responsive tables and forms for a seamless experience on all devices.
Animations:
Subtle fade-in animations for headers, cards, and content sections.
Icons:
Font Awesome 6.5.2 icons for buttons and section headings (e.g., fa-globe, fa-tree, fa-tools, fa-trash-alt).
Pages Styled:
Homepage: Hero section, informational cards, and call-to-action section.
Login/Register: Centered cards with side informational cards and image placeholders.
Farmers: Styled index table, create form, and details page.
Products: Styled index page with filter form and table, create form with validation.
Privacy Policy: Detailed content in a card layout with section icons.


📸 Screenshots
Homepage	Login Page	Products Page
		

🤝 Contributing
Contributions are welcome! To contribute to Agri-Energy Connect:

Fork the repository.
Create a new branch (git checkout -b feature/YourFeature).
Make your changes and commit (git commit -m "Add your feature").
Push to the branch (git push origin feature/YourFeature).
Open a Pull Request on GitHub.
Please ensure your code follows the project’s coding style and includes appropriate documentation.

📜 License
This project is licensed under the MIT License. See the LICENSE file for details.

📞 Contact
For questions, feedback, or support, feel free to reach out:

Email: jrpillay7@gmail.com
GitHub: Joshua29115
Thank you for exploring Agri-Energy Connect! 🌍



## References

Griffiths, I. (2019) *Programming C# 8.0*. Sebastopol, CA: O’Reilly Media.
Mrzygłód, K., 2022. Azure for Developers. 2nd ed. August: [Meeta Rajani]
ChatGPT by OpenAI (2025) ChatGPT (Version 4.5). Available at:([https://chatgpt.com/](https://chatgpt.com/share/68246417-0794-800a-82fd-9bff07ee4447)) (Accessed: 13 May 2025).
