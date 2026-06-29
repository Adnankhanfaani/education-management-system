# How to Run the EduManage Project

This is a C# ASP.NET Core MVC application that uses Entity Framework Core with Microsoft SQL Server.

---

## Prerequisites

1. **.NET SDK**: Ensure that the .NET SDK (version 8.0 or newer) is installed.
2. **Microsoft SQL Server**: Ensure that Microsoft SQL Server (specifically the `SQLEXPRESS` instance) is installed and running on your machine.

---

## Step 1: Database Setup and Connection String

The application is configured to connect to a SQL Server database named `EduManageDB` on your local `SQLEXPRESS` instance.

The connection string in [appsettings.json](file:///d:/Web%20Development/EduManage/appsettings.json) has been configured as follows:
```json
"DefaultConnection": "Server=localhost\\SQLEXPRESS;Database=EduManageDB;Trusted_Connection=True;TrustServerCertificate=True;"
```

### Apply Migrations (Only needed if there are database changes)
To apply the database schema (create tables, columns, etc.), open your terminal in the project root directory and run:
```powershell
dotnet ef database update
```
*(Note: This step has already been completed for your current migrations, and the `EduManageDB` database has been successfully created and updated.)*

---

## Step 2: Running the Web Application

To start the local development server, run the following command in your terminal from the project root directory (`d:\Web Development\EduManage`):

```powershell
dotnet run
```

Alternatively, if you want the application to automatically rebuild and reload when you make code changes, you can use:
```powershell
dotnet watch
```

---

## Step 3: Accessing the Application

Once the server has started, it will output logs indicating it is listening. You can access the application by opening your browser and navigating to:

* **URL**: [http://localhost:5000](http://localhost:5000)
