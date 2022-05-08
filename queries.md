# SQL Teaching Tutorial

## Lesson 1

```sql
select *
from family_members;
```

```sql
select id, name, gender, species, num_books_read
from family_members;
```

## Lesson 2

```sql
select name, species
from family_members;
```

## Lesson 3

```sql
select *
from family_members
where species = 'dog';
```

## Lesson 4

```sql
select *
from family_members
where num_books_read > 190;
```

```sql
select id, name, gender, species, num_books_read
from family_members
where num_books_read > 190;
```

## Lesson 5

```sql
select *
from family_members
where num_books_read >= 180;
```

```sql
select id, name, gender, species, num_books_read
from family_members
where num_books_read >= 180;
```

## Lesson 6

```sql
select * from friends_of_pickles where species = 'dog' and height_cm < 45;
```

## Lesson 7

```sql
select * from friends_of_pickles where species = 'dog' or height_cm < 45;
```

## Lesson 8

```sql
select * from friends_of_pickles where species != 'dog' and species != 'cat';
select * from friends_of_pickles where species not in ('dog', 'cat');
```

## Lesson 9

```sql
select distinct species from friends_of_pickles where height_cm > 50;
```

## Lesson 10

```sql
select * from friends_of_pickles order by height_cm desc;
```

## Lesson 11

```sql
select * from friends_of_pickles order by height_cm desc limit 1;
```

## Lesson 12

```sql
select count(*) from friends_of_pickles;
```

## Lesson 13

```sql
select count(*) from friends_of_pickles where species = 'dog';
```

## Lesson 14

```sql
select sum(num_books_read) from family_members;
```

## Lesson 15

```sql
select avg(num_books_read) from family_members;
```

## Lesson 16

```sql
select max(num_books_read) from family_members;
```

## Lesson 17

```sql
select max(height_cm), species from friends_of_pickles group by species;
```

## Lesson 18

```sql
select * from family_members where num_books_read = (select max(num_books_read) from family_members);
```

## Lesson 19

```sql
select * from family_members where favourite book is not null;
```

## Lesson 20

```sql
select * from celebs_born where birthdate > '1980-09-01';
```

## Lesson 21

```sql
select character.name, character_actor.actor_name
from character
inner join character_actor
on character.id = character_actor.character_id;
```

## Lesson 22

```sql
select character.name, actor.name
from character
inner join character_actor
on character.id = character_actor.character_id
inner join actor
on actor.id = character_actor.actor_id;
```

## Lesson 23

```sql
select character.name, tv_show.name
from character
inner join character_tv_show
on character.id = character_tv_show.character_id
inner join tv_show
on character_tv_show.tv_show_id = tv_show.id
where character.name != 'Willow Rosenberg'
and tv_show.name != 'How I Met Your Mother';
```

## Lesson 24

```sql
select character.name, actor.name
from character
left join character_actor
on character.id = character_actor.character_id
left join actor
on character_actor.actor_id = actor.id; 
```

## Lesson 25

```sql
select c.name as , a.name
from character as c
left join character_actor as ca
on c.id = ca.character_id
left join actor as a
on ca.actor_id = a.id;
```

## Lesson 26

```sql
select c.name as character, a.name as actor
from character as c
left join character_actor as ca
on c.id = ca.character_id
left join actor as a
on ca.actor_id = a.id;
```

## Lesson 27

```sql
select t2.name as employee_name, t1.name as boss_name
from employees as t1
inner join employees as t2
on t1.id = t2.boss_id;
```

## Lesson 28

```sql
select id, name
from robots
where name like "%Robot 20%";
```

## Lesson 29

```sql
select *,
case
when species = 'human' then 'talk'
when species = 'dog' then 'bark'
when species = 'cat' then 'meow' 
else 'voice' end as sound
from friends_of_pickles;
```

## Lesson 30

```sql
select *
from robots
where substr(location, -2) = 'NY';
```

## Lesson 31

```sql
select distinct name, coalesce(tank, gun, sword)  as weapon from fighters;
```
