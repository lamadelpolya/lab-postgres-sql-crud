![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Answers

## Iteration 2

**1. Add the `solid` and `chartjs` libraries as new rows to the `jslibraries` table.**

<!-- Your Query Goes Here -->

<br>

Get all the fields of the library that was released earliest (first).**

<!-- Your Query Goes Here -->
SELECT * from jslibraries
ORDER by release_date ASC
LIMIT 1;

<br>

**3. Get all the fields of the library that was released most recently (last).**

<!-- Your Query Goes Here -->
SELECT * from jslibraries
ORDER by release_date DESC
LIMIT 1;

<br>

**4. All the libraries released before 2015.**

<!-- Your Query Goes Here -->
SELECT * from jslibraries
Where release_date < '2016-05-30';

<br>

**5. Get the `name` and the `release_date` of the libraries without a licence.**

<!-- Your Query Goes Here -->
SELECT name, release_date FROM jslibraries
WHERE licence IS NULL;

<br>

**6. Get the `name` and the `stars` from all CSS Framework libraries.**

<!-- Your Query Goes Here -->
SELECT name, stars FROM jslibraries

WHERE type LIKE '%CSS%';

<br>

**7. Get the `name` of the libraries where the main technology is Typescript.**

<!-- Your Query Goes Here -->
SELECT name FROM jslibraries
WHERE main_technology = 'typescript';

<br>

**8. Get the `name` and the `type` of all the libraries with more than 1000 contributors.**

<!-- Your Query Goes Here -->
SELECT name, type FROM jslibraries
WHERE contributors > 1000
;

<br>

**9. Get the total number of `stars` of all the libraries.**

<!-- Your Query Goes Here -->
SELECT SUM(stars) FROM jslibraries
;

<br>

**10. Get the average number of `contributors` for all the libraries.**

<!-- Your Query Goes Here -->
SELECT AVG(contributors) FROM jslibraries
;

<br>

**11. Update the `licence` field of the libriaries without a licence to store `'unknown'` instead of `NULL`.**

<!-- Your Query Goes Here -->
UPDATE jslibraries
SET licence = 'unknown'
WHERE licence IS NULL;

<br>

**12. Update the `used_by` field of the libraries that don't have this information to store `'unknown'` instead of `NULL`.**

<!-- Your Query Goes Here -->
UPDATE jslibraries
SET used_by = 0
WHERE used_by IS NULL;

OR 

ALTER TABLE jslibraries
ALTER COLUMN used_by TYPE VARCHAR;

UPDATE jslibraries
SET used_by = 'unknown'
WHERE used_by IS NULL;

<br>

**13. Update all the records to capitalize the string provided in the `main_technology` field.**

<!-- Your Query Goes Here -->
UPDATE jslibraries
SET main_technology = UPPER(main_technology);

<br>

**14. Delete all the records where `licence` is `'unknown'`.**

<!-- Your Query Goes Here -->
DELETE FROM jslibraries
WHERE licence = 'unknown';

<br>

**15. Delete all the records with 10000 or less `stars`.**

<!-- Your Query Goes Here -->
DELETE FROM jslibraries
WHERE stars <= 10000;

<br>

**16. Delete all the records with less than 100 `releases`.**

<!-- Your Query Goes Here -->
DELETE FROM jslibraries
WHERE releases < 100;

<br>
Footer
