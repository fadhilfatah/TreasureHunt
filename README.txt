# Treasure Hunt Standalone v3

This version is a standalone static website. It has no Canva dependency.

## Google Sheet structure

### Existing columns

Keep these columns:

| Column | Purpose |
|---|---|
| No | Internal question number. It is NOT shown to players. |
| Question | The question shown to the player. |
| A | Answer choice 1 |
| B | Answer choice 2 |
| C | Answer choice 3 |
| D | Answer choice 4 |
| Answer | Correct choice: A, B, C or D |
| Clue | Optional clue shown with the question |
| Explanation | Explanation shown after the player answers |
| Source | Source of the question |

### Recommended columns to add

Add these two columns:

| Column | Example | Purpose |
|---|---|---|
| Difficulty | Easy / Medium / Hard | Lets the player filter by difficulty |
| Question Type | Language / Anagram question / Logic / etc. | Lets the player filter by question type |

You can add other metadata columns later if useful, but these two are required for the new filtering feature.

## Player flow

1. The player lands on the setup page.
2. They choose 5 or 10 questions.
3. They may choose:
   - Difficulty
   - Source
   - Question Type
4. Each filter's picklist is automatically populated from the unique values in that Google Sheet column.
5. The player clicks Start Hunt.
6. The game randomly selects the requested number of questions from the matching pool.
7. The four answer choices are randomly repositioned.
8. A/B/C/D labels are NOT displayed to the player.
9. After answering:
   - Correct answer is highlighted.
   - Incorrect selection is marked incorrect.
   - Feedback simply says "Incorrect."
   - Explanation and source are displayed.
10. The player proceeds to the next question.
11. At the end, the score is displayed.

## Random Hunt

The "Start Random Hunt" button bypasses all filters and selects 10 questions at random from the entire question bank.

If fewer than 10 valid questions exist, it uses all available questions.

## Restart

The Restart button asks for confirmation before returning to the setup page. The player's current score and progress are lost only after confirmation.

## Google Sheets connection

The HTML is already configured to use the published CSV URL supplied for the question bank.

If you change the spreadsheet, keep it published to the web as CSV.

## Hosting

This is a static HTML website and can be hosted for free on services such as:

- Cloudflare Pages
- GitHub Pages

No server or database is required for the current design.

## Important security note

A Google Sheet published as CSV is publicly readable. Do not put confidential, private, or sensitive information in the question bank.

## Important behaviour

The game only accepts rows where:

- Question is populated
- A, B, C and D are populated
- Answer is A, B, C or D

Difficulty and Question Type are optional in the sense that existing rows without those values remain usable. If a column does not exist at all, its filter will simply contain "Any ...".
