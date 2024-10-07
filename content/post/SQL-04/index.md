---
title: SELECT within SELECT Tutorial
slug: SQL-04
date: 2024-09-11 00:00:00+0000

categories:
    - SQL
tags:
    - Learning
weight: 1       # You can add weight to some posts to override the default sorting (date descending)
---

## 1 
List each country **name** where the **population** is larger than that of 'Russia'.
```
world(name, continent, area, population, gdp)
```

```sql
SELECT name FROM world
  WHERE population >
     (SELECT population FROM world
      WHERE name='Russia')

```

## 2
Show the countries in Europe with a per capita GDP greater than 'United Kingdom'.Show the countries in Europe with a per capita GDP greater than 'United Kingdom'.
Per Capita GDP
The per capita GDP is the gdp/population
```sql
SELECT name
FROM world
WHERE continent = 'Europe' AND gdp/population
> (SELECT gdp/population FROM world WHERE name = 'United Kingdom')
```

## 3
List the **name** and **continent** of countries in the continents containing either **Argentina** or **Australia**. Order by name of the country.
```sql
SELECT name, continent FROM world
WHERE (continent = 'South America' OR continent = 'Oceania')
ORDER BY name ASC
```

## 4
Which country has a population that is more than United Kingdom but less than Germany? Show the name and the population.
```sql
SELECT name, population 
FROM world
WHERE population > (SELECT population FROM world WHERE name = 'United Kingdom') 
AND population < (SELECT population FROM world WHERE name = 'Germany')
```

Practice from [SQLZOO](https://sqlzoo.net/wiki/SELECT_within_SELECT_Tutorial)