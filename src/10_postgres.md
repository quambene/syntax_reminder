# Postgres

- [Operators](#operators)
- [Create](#create)
- [Insert](#insert)
- [Update](#update)
- [Delete](#delete)
- [Read](#read)
- [Alter](#alter)


### Operators

```sql
# Comparison operators
= # equal
!= # not equal
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
on conflict (id) do update set first_name = table_name.first_name,
                               last_name  = table_name.last_name;
```

### Update

```sql
# Update single rows
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
