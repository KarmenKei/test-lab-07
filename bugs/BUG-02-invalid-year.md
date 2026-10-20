# BUG-02: Invalid publication years are accepted

**Severity:** Medium
**Category:** Input validation / Data integrity
**Status:** Reproduced

## Environment
- Application: Reading List v2.0
- Browser: Firefox on macOS
- URL: http://localhost:3000

## Steps to reproduce
1. Open the add-book form.
2. Enter a title and author.
3. Enter abc as the year and submit.
4. Repeat using -1 as the year.

## Expected result
The application rejects non-numeric and negative years without creating records.

## Actual result
The abc submission creates a record displaying NaN. The -1 submission creates a record displaying -1. Both display "Ном нэмэгдлээ".

## Evidence
- Screenshot: ../screenshots/invalid-year.png
- Session notes: session-notes.txt

## Reproducibility
Reproduced with two invalid year values.