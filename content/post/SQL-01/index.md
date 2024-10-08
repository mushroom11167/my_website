---
title: SELECT basics
slug: SQL-01
date: 2024-09-05 00:00:00+0000

categories:
    - SQL
tags:
    - Learning
weight: 1       # You can add weight to some posts to override the default sorting (date descending)
---

## 1
The example uses a WHERE clause to show the population of 'France'. Note that strings should be in 'single quotes';

Modify it to show the population of Germany
```sql
SELECT population FROM world
  WHERE name = 'Germany'
```

## 2
Checking a list The word **IN** allows us to check if an item is in a list. The example shows the name and population for the countries 'Brazil', 'Russia', 'India' and 'China'.

Show the **name** and the **population** for 'Sweden', 'Norway' and 'Denmark'.
```sql
SELECT name, population FROM world
  WHERE name IN ('Sweden', 'Norway', 'Denmark')
```

## 3
Which countries are not too small and not too big? `BETWEEN` allows range checking (range specified is inclusive of boundary values). The example below shows countries with an area of 250,000-300,000 sq. km. Modify it to show the country and the area for countries with an area between 200,000 and 250,000.
```sql
SELECT name, area FROM world
  WHERE area BETWEEN 200000 AND 250000
```

Practice from [SQLZOO](https://sqlzoo.net/wiki/SELECT_basics)