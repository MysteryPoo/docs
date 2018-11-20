The [`cockroach dump`](sql-dump.html) command will successfully create a dump file for a table with a [foreign key](foreign-key.html) reference to itself, or a set of tables with a cyclic foreign key dependency (e.g., a depends on b depends on a). That dump file, however, can only be executed after manually editing the output to remove the foreign key definitions from the `CREATE TABLE` statements and adding them as `ALTER TABLE ... ADD CONSTRAINT` statements after the `INSERT` statements.