# Postgres

- [Data types](#data-types)
- [Operators](#operators)
- [Create](#create)
- [Insert](#insert)
- [Update](#update)
- [Delete](#delete)
- [Read](#read)
- [Alter](#alter)
- [Constraints](#constraints)
- [Performance](#performance)

### Data types

```sql
bool
char
smallint, int2
integer, int, int4, serial
bigint, int8, bigserial
real, float4
double precision, float8
varchar
interval
int4range, int8range, tsrange, tstzrange, daterange, numrange
bytea
timestamptz
timestamp
date
time
timetz
```

### Operators

```sql
# Comparison operators
= # equal
!= # not equal
!= all (array [1, 2]) # not in array
is null
is not null
```

### Create

```sql
create table if not exists table_name
(
    id         serial primary key,
    first_name varchar not null
);

create type Color as enum ('red', 'green', 'blue');
```

### Insert

```sql
insert into table_name (id, first_name)
values (1, 'Peter'),
       (2, 'Anna');

insert into table_name (id, first_name)
values (1, 'Peter'),
       (2, 'Anna')
on conflict do nothing;

insert into table_name (id, first_name, last_name)
values (1, 'Peter', 'Müller'),
       (2, 'Anna', 'Meier')
on conflict (id) do update set first_name = excluded.first_name,
                               last_name  = excluded.last_name;
```

### Update

```sql
# Update single row
update table_name
set first_name = 'Peter',
    last_name  = 'Müller'
where id = 1;

# Update multiple rows
update table_name t
set first_name = u.first_name
from (values (1, 'Peter'),
             (2, 'Anna')
     ) u(id, first_name)
where u.id = t.id;

# Update multiple rows
update table_name t
set my_value = true
from (select unnest(array [1, 2, 3])) as u(id)
where t.id = u.id;
```

### Delete

```sql
delete
from table_name
where id = 1;
```

### Read

```sql
select * from table_name;

# subquery
select * from (select id, name from table_name) sub;

# case
select case when table1.name is null then table2.name else table1.col1 end as name
from table1
full outer join table2 on table1.id = table2.id;

# joins
inner join
left outer join, left join
right outer join, right join
full outer join
cross join
natural join

```

### Alter

```sql
alter table table_name
    add column last_name varchar not null;

alter table table_name
    drop column first_name;

alter table table_name
    alter column first_name drop not null;

alter table table_name
    alter column first_name set not null;
```

### Constraints

```sql
alter table table_name add constraint table_name_column_name_unique unique (column_name);
alter table table_name drop constraint table_name_column_name_unique;

# Show constraints
select * from pg_catalog.pg_constraint;
select * from information_schema.columns where table_name = 'column_name';
```

### Performance

```sql
explain select * from table_name;
explain (analyse true, buffers true) [query]
```
