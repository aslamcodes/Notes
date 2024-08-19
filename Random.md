Multipliex - Combine different inputs into one output

# Scratch
- Scalar valued vs Table valued function
- using stored procedure to sync two tables
```sql
create or alter procedure sync
(
	@debug_fl int = 0
)
as 
begin
	print 'Employee table sync'
end

execute sync 
execute sync @debug_fl 

```
- The production should be clean.
- Snoflake schema, fact table
## Task
- SRC table and sync it to target
- Sync all the actions from both table, like a identical twins
- soft delete the record on target table

if new record - insert into 
if modified - insert!

- Sync both the tables
- 