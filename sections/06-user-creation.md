
# 6. User Creation

## Creation Code

The following SQL commands are used to create a database user and assign the required privileges and roles.

```sql
CREATE USER maliha IDENTIFIED BY maliha;

GRANT UNLIMITED TABLESPACE TO maliha;

CREATE ROLE Registration_INFO;

GRANT CREATE TABLE TO Registration_INFO;

GRANT CREATE VIEW TO Registration_INFO;

GRANT CREATE SEQUENCE TO Registration_INFO;

GRANT CONNECT, RESOURCE, SELECT_CATALOG_ROLE TO maliha;

GRANT Registration_INFO TO maliha;
```

---

[Back to Table of Contents](../README.md)
