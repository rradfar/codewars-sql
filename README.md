![SQL](images/sql-logo.png)

# [Codewars](https://www.codewars.com/) SQL Solutions

## Challenges

|  Kyu  | Questions                                 |
| :---: | :---------------------------------------- |
|   8   | [Century From Year](#century-from-year)               |
|   8   | [Even or Odd](#even-or-odd)               |
|   8   | [Keep Hydrated](#keep-hydrated)               |
|   8   | [Opposite Number](#opposite-number)       |
|   7   | [Sum of Odd Numbers](#sum-of-odd-numbers) |

---

## Century From Year

The first century spans from the year 1 up to and including the year 100, The second - from the year 101 up to and including the year 200, etc.

You are given a table `years` with a column `yr` for the year. Return a table with a column `century` which is the century that the given year is in.

Examples:

```
yr = 1705 -> century = 18
yr = 1900 -> century = 19
yr = 1601 -> century = 17
yr = 2000 -> century = 20
```

<details><summary>Solution</summary>

```sql
SELECT CEILING(yr/100.00) AS century FROM years;
```
</details>

---

**[⬆ Back to Top](#challenges)**

## Even or Odd

You will be given a table, `numbers`, with one column `number`. Return a table with a column `is_even` containing "Even" or "Odd" depending on `number` column values.

Examples:

```
number = -1 -> is_even = 'Odd'
number = 0 -> is_even = 'Even'
number = 1 -> is_even = 'Odd'
number = 2 -> is_even = 'Even'
```

<details><summary>Solution</summary>

```sql
SELECT
  CASE
    WHEN number % 2 = 0 THEN 'Even'
    ELSE 'Odd'
  END
AS is_even
FROM numbers;
```
</details>

---

**[⬆ Back to Top](#challenges)**

## Keep Hydrated!

Nathan loves cycling. Because Nathan knows it is important to stay hydrated, he drinks 0.5 liters of water per hour of cycling. You get given the time in hours and you need to return the number of liters Nathan will drink, rounded to the smallest value.

Examples:

```
time = 3 -> liters = 1
time = 6.7 -> liters = 3
time = 11.8 -> liters = 5
```

Given the table `cycling` which contains columns `id` and `hours`, you have to return 3 columns: `id`, `hours` and `liters`.

<details><summary>Solution</summary>

```sql
SELECT *, FLOOR(hours / 2) AS liters FROM cycling;
```
</details>

---

**[⬆ Back to Top](#challenges)**

## Opposite Number

You are given a table `opposite`, with a column `number`. Return a table with a column `res`.

Examples:

```
number = 1 -> res = -1
number = 14 -> res = -14
number = -34 -> res = 34
```

<details><summary>Solution</summary>

```sql
SELECT -number AS res FROM opposite;
```
</details>

---

**[⬆ Back to Top](#challenges)**

## Sum of odd numbers

Given the triangle of consecutive odd numbers:

```
             1
          3     5
       7     9    11
   13    15    17    19
21    23    25    27    29
...
```

Calculate the row sums of this triangle from the row index (starting at index 1). The table `nums` contains the integer `n` (the input row index). Return your result in a column `res`.

Examples:

```
n = 1 -> res = 1
n = 2 -> res = 8 (because 3 + 5 = 8)
n = 3 -> res = 27 (because 7 + 9 + 11 = 27)
```

<details><summary>Solution</summary>

```sql
SELECT n * n * n AS res FROM nums;
```
</details>

---

**[⬆ Back to Top](#challenges)**
