## 📕 ServiceNow CAD Exam Dumps – Application Scope & Security

This section covers important **ServiceNow CAD exam topics** related to application scope, access control, runtime permissions, and script protection, aligned with real **[CAD exam dumps](https://www.itexamscerts.com/servicenow/cad-dumps.html)** and exam-oriented practice questions.


# Security and Restricting Access

Restrict access to applications and application modules

---

## Application Menu

Go to **System Definition → Application Menus**  
or  
**Studio → Application Explorer → Navigation → Application Menus → [Your App]**

Click **Edit roles** and assign only the roles permitted to view the application.  
Users without those roles won’t see it.

---

## Application Module

Navigate to **System Definition → Modules**  
or via  
**Studio → Application Explorer → Navigation → Modules → [Module]**

In the **Visibility (roles)** field, add the roles that should have access.  
Users without those won’t see the module.

---

## Manually and automatically create, test, and debug Access Controls

### Create ACLs

**Manually**
- With the `security_admin` role you can elevate yourself
- Now create ACLs

**Automatically**
- When creating a table you can select a checkbox and ACLs are created

---

### Test ACLs

- Impersonate as User and access a table / record / field
- Or use **"Access Analyzer"**
- Or use **"Debug Security Rules"** Module

---

### Debug ACLs

- Same as above

---

## Debug Security Rules Output

## Icon Descriptions

| Icon | Description |
|-----|------------|
| A green checkmark (Green checkmark) | Indicates the table or field passed the criteria. |
| A red x icon (Red x icon) | Indicates the table or field did not pass. |
| An empty gray circle icon (Grey circle icon) | Indicates the ACL evaluation did not need to be performed. |
| A blue checkmark, x, or empty circle | Indicates that the ACL was taken from a cached result of a previous ACL check. The icons mean the same as the above. |

---

## ACL Execution Order

From most specific (field), to most generic (record)

- If a user fails a table ACL rule, the user is denied access to all fields in the table, even if the user passes a field ACL rule.
- If a user passes a table ACL rule, but fails a field ACL rule, the user cannot access the field described by the field ACL rule.
- Order in General: Table evaluated first, then field
- Order in ACL: Roles, Condition, Script

---

## Use GlideSystem methods to script security

### Important methods

**Server-Side: GlideSystem (gs)**

- getUser()
- getUserID()
- getUserName()
- hasRole()
- isLoggedIn()
- isInteractive()
- getSession()

---

## Other Scripted Security Methods

The client-side GlideUser (`g_user`) API has these methods:

- hasRole()
- hasRoleExactly()
- hasRoleFromList()
- hasRoles()

The client-side API methods can be used in any client-side script, such as Client Scripts and UI Policy scripts. Client-side security is the easiest security to break. Do not depend on client-side scripts to secure sensitive data.

---

The server-side GlideSystem (`gs`) API has these methods:

- getUser()
- getUserID()
- getUserName()
- hasRole()
- isLoggedIn()
- isInteractive()
- getSession()

---

The server-side GlideElement API has methods to check whether a user's role allows them to access the associated GlideRecord(s):

- canCreate()
- canRead()
- canWrite()

## Use Application Scope to protect application artifacts

---

## Application design and runtime

**JavaScript Mode**  
Configurable which JavaScript version the scope supports (ES2021 / ES5)

**Runtime Access Tracking**

- **None**  
  Automatically accept all requests for cross-scope resources, without logging
- **Tracking**  
  Automatically accept all requests for cross-scope resources, with logging
- **Enforcing**  
  Manual authorization by an administrator for cross-scope requests, with logging

**Restrict Table Choices**  
Restrict which cross scope tables can be seen by the application

**Important:**  
After installation, the system no longer tracks new runtime access requests. Only during development.

Runtime access requests / grants are stored in related list **"Cross-scope privilege"**

---

## Table design and runtime

### Records

**Accessible from**
- All application scopes
- This application scope only

**Can read**
- Required for all other options to be available
- Allow other applications to read from this table
- If this + accessible from → Other Applications can create Business Rules

**Can write**
- Allow other applications to write values to this table

**Can create**
- Allow script object from other applications to create records on this table

**Can delete**
- Allow script object from other applications to delete records from this table

**Allow access to this table via web services**
- Allow inbound webservice queries on this table
- User still needs correct permissions, even without checkbox

---

### Configuration

**Allow configuration**
- Accessible from needs to be set to **"All application scopes"**
- Allows applications in other scopes to create the following on this table:
  - Business Rules
  - UI Actions
  - Client Scripts
  - Add fields (extended fields are in different scope)

---

## Script protection policy

You can protect your script with the following options:

- **None**  
  Allow other application developers to customize your script
- **Read-only**  
  Allow other application developers read-only access
- **Protected**  
  Prevent other application developers from access and customization

**Important:**  
This is only enforced on instances where application not developed, and for Store-Apps.  
For all others you can just remove the Protection Policy.

---
**Review more ServiceNow CAD certification domains and access updated [CAD dumps PDF](https://www.itexamscerts.com/servicenow/cad-dumps.html) resources through our dedicated CAD exam study hub.**
---
