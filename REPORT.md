## Report On Oracle Database Environment Assignment

**Student: Ineza Sonia**
**ID: 27852 Course: Advanced Database Management (PL/SQL AUCA)**
**Assignment: Oracle Database Environment (CDBs, PDBs & OEM)**

This assignment focused on creating and managing Container and Pluggable Databases (CDBs & PDBs) in Oracle 21c, 
and setting up Oracle Enterprise Manager Express (OEM Express) for database monitoring and administration.

Environment Setup Oracle Version: Oracle Database 21c Enterprise Edition

### Task 1 — Create a Pluggable Database

Connected as SYSDBA and verified root container.
Created the PDB using:

![PDB_1](https://github.com/user-attachments/assets/4fa40f16-9481-463f-8956-0123f9e979bf)


```
CREATE PLUGGABLE DATABASE in_pdb_27852 
ADMIN USER ineza_plsqlauca_27852 IDENTIFIED BY YourPassword 
FILE_NAME_CONVERT = ( 'C:\home\oradata\ORCL\pdbseed', 'C:\home\oradata\ORCL\in_pdb_27852' );
```

Opened and saved state:

```
ALTER PLUGGABLE DATABASE in_pdb_27852 OPEN; ALTER PLUGGABLE DATABASE in_pdb_27852 SAVE STATE;
```

**Result: in_pdb_27852 created and opened successfully.**

### Task 2 — Create and Delete a PDB

Switched to the root container:

```
ALTER SESSION SET CONTAINER = CDB$ROOT;
```


Created another PDB with the required naming format:
![PDB_2](https://github.com/user-attachments/assets/40ad8ed9-7c00-4af0-9fbd-72217e5e900f)


```
CREATE PLUGGABLE DATABASE in_to_delete_pdb_27852 
ADMIN USER in_admin_27852 IDENTIFIED BY YourPassword 
FILE_NAME_CONVERT = ( 'pdbseed', 'in_to_delete_pdb_27852' );
```

Opened the new PDB and confirmed its status:
![PDB_22](https://github.com/user-attachments/assets/e35141a6-6273-42e6-a0ff-226b7ab1f440)


```
ALTER PLUGGABLE DATABASE in_to_delete_pdb_27852 OPEN; 
SELECT name, open_mode FROM v$pdbs WHERE name = 'IN_TO_DELETE_PDB_27852';
```

Deleted the PDB after verification:
![Dropped](https://github.com/user-attachments/assets/8a967dfa-29ea-43b7-bd9c-38428c6549cb)


```
ALTER PLUGGABLE DATABASE in_to_delete_pdb_27852 CLOSE IMMEDIATE; 
DROP PLUGGABLE DATABASE in_to_delete_pdb_27852 INCLUDING DATAFILES;
```

**PDB in_to_delete_pdb_27852 was successfully created, opened, verified, and deleted**
