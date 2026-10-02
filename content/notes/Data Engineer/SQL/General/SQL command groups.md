
SQL จะถูกแบ่งกลุ่มคำสั่งตามการใช้งานหลักเป็น 5 กลุ่ม
1. Data Definition Language (DDL): ไว้จัดการ schema
	1. **CREATE**: ใช้สร้าง table
	2. **ALTER**: เปลี่ยนโครงสร้างของ table ที่มีอยู่
	3. **DROP**: ลบข้อมูลและตัว table จาก database
	4. **TRUNCATE**: ลบข้อมูลทั้งหมดใน table แต่ table ยังอยู่
2. Data Manipulation Language (DML): ไว้จัดการ data โดยตรง
	1. **INSERT**: To add new rows of data into a table.
	2. **UPDATE**: To change existing data within a table.
	3. **DELETE**: To remove specific rows from a table.
3. Data Query Language (DQL): ไว้ดึงข้อมูลออกมาแสดงผล
	1. **SELECT**: The primary command for querying data. It is often used with clauses like `GROUP BY` to summarize information.
	2. FROM
4. Data Control Language (DCL): ไว้จัดการความปลอดภัยกับสิทธิเข้าถึง
	1. **GRANT**: Gives specific permissions to users.
	2. **REVOKE**: Removes previously granted permissions.
5. 5. Transaction Control Language (TCL): ไว้ควบคุม data integrity สำหรับ DML ที่ซับซ้อน
	1. **COMMIT**: Saves all changes made during the current transaction permanently.
	2. **ROLLBACK**: Reverts the database to its previous state if an error occurs.
	3. **SAVEPOINT**: Sets a point within a transaction to which you can later roll back