# TechTFQ-30DaysSQLChallenge-DAY2
going through the challenge of SQL interview questions featured in the TechTFQ channel



In this repository we will be going through the SQL interview questions featured in the following YouTube Playlist [SQL Interview Questions](https://www.youtube.com/watch?v=rM1BVoBke04&list=PLavw5C92dz9Hxz0YhttDniNgKejQlPoAn&index=2).

# **Day 2: The problem statement:**

A Ski resort company is planning to construct a new ski slope using a pre-existing network of mountain huts and trails between them.
A new slope has to begin at one of the mountain huts, have a middle station at another hut connected with the first one by a direct trail, and end at the third mountain hut which is also connected by a direct trail to the second hut.
The altitude of the 3 huts chosen for constructing the ski slope has to be strictly decreasing:

We are given 2 SQL tabes, mountain_huts and trail, with the following structure:

**DDL**
```
create table mountain_huts(
  id integer not null,
  name varchar(40) not null,
  altitude integer not null,
  unique(name),
  unique(id)
);

create table trails(
  hut1 integer not null,
  hut2 integer not null
);

```

**DML**

```
insert into mountain_huts values (1, 'Dakonat', 1900);
insert into mountain_huts values (2, 'Natisa', 2100);
insert into mountain_huts values (3, 'Gajantut', 1600);
insert into mountain_huts values (4, 'Rifat', 782);
insert into mountain_huts values (5, 'Tupur', 1370);
insert into trails values (1, 3);
insert into trails values (3, 2);
insert into trails values (3, 5);
insert into trails values (4, 5);
insert into trails values (1, 5);


```
Each entry in the table trails represents a direct connection between huts with IDs hut1 and hut2. Note that all trails are bidirectional.
Create a query that finds all triplets(startpt,middlept,endpt) representing the mountain huts that may be used for construction of a ski slope.
Output returned by the query can be ordered in any way.


Each entry in the table trails represents a direct connection between huts with IDs hut1 and hut2. Note that all trails are bidirectional.
Create a query that finds all triplets(startpt,middlept,endpt) representing the mountain huts that may be used for construction of a ski slope.
Output returned by the query can be ordered in any way.
Examples:
1.Given the tables:

![image](https://github.com/Highashikata/TechTFQ-30DaysSQLChallenge-DAY2/assets/96960411/4c972ccf-3269-4e8a-a847-997d9e2efaaf)


Your query should return:


![image](https://github.com/Highashikata/TechTFQ-30DaysSQLChallenge-DAY2/assets/96960411/f294a8e1-2123-43e7-9873-cba1eb44ca3b)

Assume that:

- there is no trail going from a hut back to itself;
- for every two huts there is at most one direct trail connecting them;
- each hut from table trails occurs in table mountain_huts;

