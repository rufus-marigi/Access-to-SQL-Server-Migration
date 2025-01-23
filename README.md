# Access to SQL Server Migration Project

## Overview
This project demonstrates the migration of a Microsoft Access database to SQL Server using SQL Server Migration Assistant (SSMA). The goal was to enhance the database's performance, scalability, and security, while optionally maintaining Microsoft Access as the front-end interface.

---

## Prerequisites

### Software and Tools
- Microsoft Access
- SQL Server (2019 or later)
- SQL Server Management Studio (SSMS)
- SQL Server Migration Assistant (SSMA) for Access

### System Requirements
- Administrative privileges on the source Access database and SQL Server instance.
- Access to the network or server where SQL Server is hosted.
- ODBC driver installed for SQL Server.

---

## Migration Steps

### 1. Preparation
1. **Backup** the original Access database.
2. Ensure SQL Server is properly configured:
   - Enable TCP/IP in SQL Server Configuration Manager.
   - Open port 1433 in the firewall for remote access.

### 2. Install SQL Server Migration Assistant (SSMA)
1. Download and install SSMA for Access from the official Microsoft website.

### 3. Launch SSMA and Create a New Project
1. Open SSMA.
2. Go to `File > New Project` and configure the following:
   - **Project Name**: Descriptive name (e.g., `AccessToSQL`).
   - **SQL Server Version**: Select the version you are migrating to.

### 4. Connect to Access Database
1. Click `Add Databases` in the toolbar.
2. Browse to your Access database file (.accdb or .mdb).
3. Provide the password if the database is protected.

### 5. Connect to SQL Server
1. Click `Connect to SQL Server` in the toolbar.
2. Enter the following details:
   - **Server Name**: Enter the IP address or server name (e.g., `192.168.100.100`).
   - **Authentication**: Select `SQL Server Authentication` and provide valid credentials.
   - **Database**: If the dropdown is empty, manually type the database name.
3. Click `Connect` to verify the connection.

### 6. Convert Schema
1. Right-click the Access objects (tables, queries) and select `Convert Schema`.
2. Review the converted schema in the SQL Server Metadata Explorer.
3. Resolve any warnings or errors in the Output pane.

### 7. Migrate Data
1. Right-click the converted database objects and select `Migrate Data`.
2. Monitor the progress in the Output pane to ensure successful data transfer.

### 8. Post-Migration Validation
1. Open SSMS and connect to the SQL Server instance.
2. Verify the migrated tables and data:
   - Run queries to check row counts and sample data.
   - Test relationships and constraints.

### 9. Optional: Link Access Front-End to SQL Server
1. Open the Access database.
2. Go to `External Data > Linked Table Manager`.
3. Relink tables using an ODBC connection configured for the SQL Server instance.

### 10. Optimize Performance
1. Use SQL Server Profiler or Dynamic Management Views (DMVs) to identify slow queries.
2. Add indexes or optimize queries for better performance.

---

## Challenges and Resolutions

| **Challenge**                          | **Resolution**                                  |
|----------------------------------------|------------------------------------------------|
| SSL certificate error during connection| Enabled "Trust Server Certificate" in SSMA.    |
| Blank database dropdown in SSMA        | Manually entered the database name.            |
| Access Linked Table Manager grayed out | Ensured database was in a trusted location.    |

---

## Outcomes
- Successfully migrated all data, tables, and relationships to SQL Server.
- Optional Access front-end linked to SQL Server for seamless use.
- Improved database scalability and security.

---

## Next Steps
1. Train end-users on the new system setup.
2. Schedule regular backups of the SQL Server database.
3. Monitor and optimize performance as needed.

---

## Author
- **Name**: Rufus Kinuthia
- **Role**: Full-Stack Developer
- **Location**: Kenya
- **Contact**: rufuskinuthia2@gmail.com
