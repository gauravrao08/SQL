```
1. How to create Role

Create Role Role_Dev_FullRights;
GRANT SHOW DATABASES ON *.* to Role_Dev_FullRights;
GRANT ALL ON db1.* to Role_Dev_FullRights;
GRANT ALL ON db2.* to Role_Dev_FullRights;

2. How to assign user to Role
CREATE USER 'name'@'IP' IDENTIFIED BY 'password';
GRANT 'Role_Mis' TO 'name'@'IP';

2.1
SET DEFAULT ROLE Role_Dev_FullRights FOR 'name'@'IP';     #will work on latest version only, if this work then user can skip step3 and login directly

3. Login into Server
set Role Role_Mis;

4. Grants for  three roles

Role_Dev_FullRights
MariaDB [(none)]> SHOW GRANTS for Role_Dev_FullRights;
+------------------------------------------------------------+
| Grants for Role_Dev_FullRights                             |
+------------------------------------------------------------+
| GRANT SHOW DATABASES ON *.* TO 'Role_Dev_FullRights'       |
| GRANT ALL PRIVILEGES ON `db1`.* TO 'Role_Dev_FullRights'    |
| GRANT ALL PRIVILEGES ON `db2`.* TO 'Role_Dev_FullRights' |
+------------------------------------------------------------+
```
