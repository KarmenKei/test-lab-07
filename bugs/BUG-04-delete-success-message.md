# BUG-04: Delete action displays an incorrect success message

**Severity:** Low  
**Category:** User feedback / UI  
**Status:** Reproduced (confirm in browser before submitting)

## Environment
- Application: Reading List v2.0
- Browser: Firefox on macOS
- URL: `http://localhost:3000`

## Steps to reproduce
1. Open the reading list.
2. Add a temporary book.
3. Click `Устгах` on that book.
4. Observe the success message displayed above the table.

## Expected result
The selected book is deleted, and the application displays a confirmation message indicating deletion, such as `Ном устгагдлаа`.

## Actual result
The application displays `Ном нэмэгдлээ` (“Book added”) after the delete action, which incorrectly describes the operation performed.

## Evidence
- Screenshot: `../screenshots/delete-success-message.png`
- Session notes: `session-notes.txt`

## Impact
The incorrect confirmation message can confuse users about whether the application added or deleted a book.

## Reproducibility
Record the number of successful reproductions after testing in the browser.