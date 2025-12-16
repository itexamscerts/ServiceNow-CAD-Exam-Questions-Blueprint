## 🧠 CAD (Certified Application Developer) Exam Study Guide

This study guide summarizes the key topics tested in the **[CAD (Certified Application Developer)](https://www.itexamscerts.com/servicenow/cad-dumps.html)** exam.  
The content is based on publicly available resources, official ServiceNow learning paths, and feedback from exam candidates.  
It is ideal for **last-minute revision** and for reinforcing concepts that frequently appear in real **CAD exam scenarios**.

🎯 **Looking for updated CAD exam practice questions and dumps?**  
👉 CAD Practice Questions – itexamscerts.com


## Designing and Creating an Application

### Determine if an application is a good fit for ServiceNow

#### Good fit

If an application has one of these characteristics, it is (usually) a good fit for the ServiceNow Platform.

- Simple forms  
- Task management  
- Request fulfillment  
- Excel-driven processes  
- Repeatable processes  
- 3rd party integrations  
- Orchestration of multiple systems  
- Single experience from functions in multiple systems  
- Web and mobile access to the same apps and data simultaneously  

#### Bad fit

- Unstructured data  
- Unrepeatable processes  
- Requires graphics processing  
- Streaming audio or video  
- Highly customized UI  

### Anatomy of application

Visual representation of the different components and applications consists of:

![cad1](https://github.com/user-attachments/assets/1601e08b-0221-4064-9bb5-45fe8f8c21e4)

---

## Creating application

*Menu:*  
System Applications > Studio > (Click on **Create Application**)  
Other Option: System Applications > My Company Applications > (Click on **Create new**)

*Guided Application Creator / Guided App Creator*

Guides you through the creation process of a Scoped Application.

*Roles*

Roles allowing to use Guided App Creator

- `sn_g_app_creator.app_creator`: Allows to create applications with private scope  
- `sn_g_app_creator.global`: Allows to create applications in global scope  

*System Properties*

- `sn_g_app_creator.allow_global`: Allows all users with `sn_g_app_creator.app_creator` role to create applications in the global scope  

*Panes*

- **Info Pane**
  - **Application Details**
    - Name: Your application’s name  
    - Description: Your application’s description  
    - **Advanced Settings:**
      - Scoped: Private scope (namespace) for your code  
      - Global: “Bucket” for custom code in Global scope (namespace)  
      - Scope: Unique identifier for the application, limited to 18 characters (Value is automatically populated)
  - **Roles**
    - Roles: select an existing role to restrict access to an application. Only users with the role can access the application.
    - Or use “Create new Role” to create a new role for the application
  - **Application Formats**
    - Mobile: Supports users who work from mobile device  
    - Classic: Supports users who work via lists and forms  

- **Data Pane**
  - **Creating Tables**
    - You can select an existing table or create a new table
  - **Creating a new Table**
    - Upload spreadsheet: Use a `.XLSX` spreadsheet to add fields to a table  
    - Extend a table: Start from an existing ServiceNow table and add fields  
    - Create table from scratch: Define table fields  
    - Manage Access: Grant access to tables by role and set role permissions  

- **Design Pane**
  - Here you can adjust the prefilled values which will be created into Application Menu and Module(s)

---

## Design and implement a data model

*Menu:*  
System Definition > Tables

*Creating a table*

Described in this document are the licensing limitations when creating custom tables:  
ServiceNow – Custom Table Guide

*Creating a table (Default Fields)*

ServiceNow automatically adds the following fields when a table is created:

![cad4](https://github.com/user-attachments/assets/8931c9dd-e71e-49c9-81a1-561653b13ca0)

---

## Creating a table (Configuration Options)

When creating a table you have the following options:

- **Extensible:** Can table be extended? (Used in child table, in field **Extends table**)  
- **Extends table:** When table should extend from other table (e.g. task, cmdb_ci)  
- **Create access controls:** If checked, will create access controls (ACLs). This must be selected for Scoped Applications  
- **User role:** Creates a role to access the table  
- **Create module:** Creates Module  
- **Create mobile module:** Creates Module for Mobile  
- **Add module to menu:** Add to existing Menu “point”, or create new  
- **New menu name:** If “create new” is selected, you can enter a new menu name here  

### Extend or not?

| Criteria | Extend |
|--------|--------|
| A table exists with fields similar to what is needed | Yes |
| No similar table exists | No |
| Table will contain sample or seeded data that is used only for reference by the application | No |
| The scripts and workflow for an existing table are useful for the application | Yes |
| You prefer to script the application logic yourself and not inherit logic | No |
| You want to use the approval workflow activities (must extend the Task table for all approval activities except the User Approval activity) | Yes |

**Conclusion:**  
If a developer creates a new table from scratch they have complete control over the table's columns and the business logic. For example, for reference data to associate to in another table, or for processes that are dissimilar from pre-existing tables and business logic contained on those tables.

---

## Create modules

They can be automatically created when a table is created (see above), or manually with more configuration options as described below.

### Application Menu vs. Module

![cad6](https://github.com/user-attachments/assets/f3cdd67c-9e76-4a81-b827-41b29e3f4cc5)

# Configuration Options

When creating a module you have the following options:

- **Title**: Module name  
- **Application menu**: Under which application module appears  
- **Order**: In increments of 100's defines order of Modules underneath Application menu  
- **Hint**: Shown to user when hovered over module  
- **Roles**: Restrict module access to specified roles  
- **Active**: Defines whether module appears in "All" menu  
- **Override application menu roles**: Roles here grant access to users who are not authorized to access the application menu  
- **Link Type**: Type of link for module. Separator is used to create "Application menu" in "All" Menu.  
- **Table**: Name of table this module is part of  
- **View name**: Specifies the view in which module opens  
- **Filter**: Used for lists. Specifies filter  

**ServiceNow Product Documentation – Module Link Types**

---

# Use Application scope

The first decision in a development process according to best practice should be whether to put the application in a private scope or global scope

---

## Private Scope

- Default behavior  
- Private application scope  
- Only applications in same scope have full access to create, modify and remove or run application data  
- can use source control (git / company registry)  
- can use delegated development (for non-admin users)  

---

## Global Scope

- Can not integrate with source control  
- Can not use delegated development  

### Only create if:

- application has to delete global data  
- application needs change application access settings on multiple default tables to function  
- application needs access to APIs only available in global scope. Creating a globally scoped passthrough script (bypass measure by passing functions calls to Global-only APIs) would not meet this requirement.

✅ Pro Tip: For updated CAD questions and practice tips, bookmark: https://www.itexamscerts.com/servicenow/cad-dumps.html


