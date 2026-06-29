# Setup Instructions to Run EduManage on a New Device

To run this project on a new laptop, your friend needs to perform the following steps:

## 1. Install Prerequisites
Make sure the following software is installed on the laptop:
* **.NET 8.0 SDK** (Download from [dotnet.microsoft.com](https://dotnet.microsoft.com/download/dotnet/8.0))
* **Microsoft SQL Server** (SQL Server Express Edition is recommended, or LocalDB/Full SQL Server)
* **SQL Server Management Studio (SSMS)** or **Azure Data Studio** (optional, to run database scripts visually)

---

## 2. Set Up the Database
Your friend needs to execute the database script to create the tables, views, triggers, and seed data:
1. Open the command prompt or terminal in the project's root directory.
2. Run the following command (replace `localhost\SQLEXPRESS` with their local SQL Server instance name if it differs):
   ```powershell
   sqlcmd -S localhost\SQLEXPRESS -i EduManageDB.sql
   ```
   *Alternatively, they can open the `EduManageDB.sql` script in SSMS/Azure Data Studio and click **Execute**.*

---

## 3. Update the Database Connection String
If their local SQL Server instance name is different (e.g., if they are using LocalDB or a default instance rather than `SQLEXPRESS`), they must update the connection string:
1. Open `appsettings.json`.
2. Change the `DefaultConnection` value:
   ```json
   "ConnectionStrings": {
     "DefaultConnection": "Server=<THEIR_SQL_SERVER_INSTANCE>;Database=EduManageDB;Trusted_Connection=True;TrustServerCertificate=True;"
   }
   ```
   * *For LocalDB, it would look like:* `Server=(localdb)\\MSSQLLocalDB;Database=EduManageDB;...`
   * *For a default local server instance, it would look like:* `Server=localhost;Database=EduManageDB;...`

---

## 4. Run the Application
1. Open a terminal/PowerShell in the project root directory.
2. Build the project to verify all dependencies restore correctly:
   ```powershell
   dotnet build
   ```
3. Start the application:
   ```powershell
   dotnet run
   ```
4. Open the web browser and navigate to **`http://localhost:5000`** to log in.
