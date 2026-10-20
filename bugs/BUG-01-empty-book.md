# BUG-01: Empty book records can be created

**Severity:** Medium
**Category:** Input validation / Data integrity
**Status:** Reproduced

## Environment
- Application: Reading List v2.0
- Browser: Firefox on macOS
- URL: http://localhost:3000

## Steps to reproduce
1. Open the add-book form.
2. Leave the title, author, and year fields empty.
3. Submit the form.
4. Repeat the submission.

## Expected result
The application rejects empty submissions and does not create records.

## Actual result
The application displays "Ном нэмэгдлээ", creates blank rows with year 0, and increases the book counter.

## Evidence
- Screenshot: ../screenshots/empty-book-submission.png
- Session notes: session-notes.txt

## Reproducibility
Reproduced twice.