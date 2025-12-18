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
