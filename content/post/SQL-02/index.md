---
title: SELECT from Nobel Tutorial
slug: SQL-02
date: 2024-09-02 00:00:00+0000

categories:
    - SQL
tags:
    - Learning
weight: 1       # You can add weight to some posts to override the default sorting (date descending)
---

## 1
Change the query shown so that it displays Nobel prizes for 1950.
```sql
SELECT yr, subject, winner
  FROM nobel
 WHERE yr = 1950
```

## 2
Show who won the 1962 prize for literature.
```sql
SELECT winner
  FROM nobel
 WHERE yr = 1962
   AND subject = 'literature'
```

## 3
Show the year and subject that won 'Albert Einstein' his prize.
```sql
SELECT yr, subject
FROM nobel
where winner = 'Albert Einstein'
```

## 4
Give the name of the 'peace' winners since the year 2000, including 2000.
```sql
SELECT winner
FROM nobel
WHERE yr >= '2000' AND subject = 'peace'
```

## 5 
Show all details (**yr**, **subject**, **winner**) of the literature prize winners for 1980 to 1989 inclusive.
```sql
SELECT yr, subject, winner
FROM nobel
where (yr >=1980 AND yr <= 1989) 
   AND subject = 'literature' 
```

## 6
Show all details of the presidential winners:

- Theodore Roosevelt
- Woodrow Wilson
- Jimmy Carter
- Barack Obama
```sql
SELECT * FROM nobel
 WHERE winner IN ('Theodore Roosevelt',
                  'Woodrow Wilson',
                  'Jimmy Carter',
                  'Barack Obama')
```

## 7
Show the winners with first name John
```sql
SELECT winner
FROM nobel
where winner LIKE 'John%'
```

## 8
Show the year, subject, and name of physics winners for 1980 together with the chemistry winners for 1984.
```sql
SELECT yr, subject, winner
FROM nobel
WHERE (yr = '1980' AND subject = 'physics')
   OR (yr = '1984' AND subject = 'chemistry')
```

## 9
Show the year, subject, and name of winners for 1980 excluding chemistry and medicine
```sql
SELECT yr, subject, winner
FROM nobel
WHERE yr = '1980'
AND subject NOT IN ('chemistry', 'medicine')
```

## 10
Show year, subject, and name of people who won a 'Medicine' prize in an early year (before 1910, not including 1910) together with winners of a 'Literature' prize in a later year (after 2004, including 2004)
```sql
SELECT *FROM nobel
WHERE (yr < '1910' AND subject = 'medicine')
   OR (yr >= '2004' AND subject = 'literature')
```

## 11
Find all details of the prize won by PETER GRÜNBERG

Non-ASCII characters

The u in his name has an **umlaut**. You may find this link useful [https://en.wikipedia.org/wiki/%C3%9C#Keyboarding](https://en.wikipedia.org/wiki/%C3%9C#Keyboarding)
```sql
SELECT *FROM nobel
WHERE winner = 'Peter Grünberg'
```

## 12
Find all details of the prize won by EUGENE O'NEILL

Escaping single quotes

You can't put a single quote in a quote string directly. You can use two single quotes within a quoted string.
```sql
SELECT *FROM nobel
WHERE winner = "Eugene O'neill"
```

## 13
Knights in order

List the winners, year and subject where the winner starts with **Sir**. Show the the most recent first, then by name order.
```sql
SELECT winner, yr, subject
FROM nobel
WHERE winner LIKE 'Sir%'
ORDER BY yr DESC, winner
```

## 14
The expression **subject IN ('chemistry','physics')** can be used as a value - it will be **0** or **1**.The expression subject IN ('chemistry','physics') can be used as a value - it will be 0 or 1.

Show the 1984 winners and subject ordered by subject and winner name; but list chemistry and physics last.
```sql
SELECT winner, subject
  FROM nobel
 WHERE yr = 1984
 ORDER BY subject IN ('chemistry','physics') ASC
```

Practice from [SQLZOO](https://sqlzoo.net/wiki/SELECT_from_Nobel_Tutorial)