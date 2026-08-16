# Treasure Hunt Standalone

## Google Sheet columns

Required:
- No
- Question
- Answer

Recommended:
- Clue
- Explanation
- Source

Optional:
- Category

## Connect Google Sheets

In Google Sheets:
1. Create the question bank.
2. File -> Share -> Publish to web.
3. Select the worksheet.
4. Select CSV.
5. Copy the published CSV URL.
6. Open index.html.
7. Replace PASTE_YOUR_GOOGLE_SHEET_CSV_URL_HERE with that URL.

The site will then load the sheet directly.

## Hosting

This is a plain static website. It can be hosted on Cloudflare Pages or GitHub Pages.

No Canva SDK is required.

## Important

A published Google Sheet is publicly readable. Do not store confidential information in it.
