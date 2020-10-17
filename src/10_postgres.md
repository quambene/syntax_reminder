# Postgres

### Create

```postgres
create table if not exists table_name
(
    id         serial primary key,
    first_name varchar not null
);

create type Color as enum ('red', 'green', 'blue');

insert into table_name (id, first_name)
values (1, 'Peter'),
       (2, 'Anna');
```

### Update

```postgres
update table_name t
set first_name = u.first_name
from (values (1, 'Pete'),
             (2, 'Anne')
     ) u(id, first_name)
where u.id = t.id;
```

### Delete

```postgres
delete
from table_name
where id = 1;
```

### Read

```postgres
select * from table_name;
```

### Alter

```postgres
alter table table_name
    add column last_name varchar not null;

alter table table_name
    drop column first_name;

alter table table_name
    alter column first_name drop not null;

alter table table_name
    alter column first_name set not null;
```
