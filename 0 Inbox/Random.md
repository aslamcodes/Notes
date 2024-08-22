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

# Data Lakes
- ![[Screenshot 2024-08-19 at 3.10.34 PM.png]]
- Understand the data of a business and bring more insights
- All the data accumulated needs a centralised system
- Model the data with schemas
- create reports out of it
- It doesn't have to be one data warehouse, a enterprise can have 
# Data Lakes
- Data lake isnt as strict as data warehouse, a data lake can have csv files and stuffs
- There is no objectives for datalakse
- Mostly storage and compute are seperated
- chrom
> Operational means transactional

# The differences
![[Screenshot 2024-08-19 at 3.25.06 PM.png]]
In data lake, when you want to solve a business problem, we have to process the data and make sense of it.


# ADF
## What is ADF
- Factory which data comes in and comes out, can perform data movement and transformations 
# Activities
- Data movement
- Data Transformation
- Control flow activity
## Components
- pipeline
- activity
- dataets
- linked serviers
- triggers
## Pipeline
- We can have multiple pipelines

## Linked services
- Concoction with other services such as blob storage, sql servers
- Datasets are something that 
## Triggers
- Specify when a pipeline will be kicked off
## Integration Runtime
- Computing infrastructure used by ADF