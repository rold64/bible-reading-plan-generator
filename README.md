# Bible Reading Plan Generator

A browser-based Bible reading plan generator that creates custom reading schedules for any date range, book selection, and plan format. It can generate a printable or downloadable plan in calendar, list, week, book, or circular layouts and supports multiple Bible orders and translations.

## Overview

This project is a single-page web app built around a set of JavaScript data files and a small PHP wrapper. The app lets users:

- choose a reading window (start date + number of days)
- pick books or testaments from the Bible
- choose a reading order such as traditional, chronological, alternate/Tanakh, or M'Cheyne
- divide reading by chapters, words, or pericopes
- select specific weekdays
- include optional extras like a daily Psalm, daily Proverb, section colors, daily stats, and reading links
- export the generated plan as PDF, CSV, or iCal
- print the final plan

The site is live at: https://www.biblereadingplangenerator.com/

## Features

- Multi-format output:
  - Calendar
  - List
  - Weeks
  - Books
  - Circle (slices)
  - Circle (calendar)
- Reading orders:
  - Traditional
  - Chronological
  - Alternate / Tanakh
  - M'Cheyne
- Bible data support for multiple languages and translations
- Optional daily Psalm and Proverb additions
- Optional stats and reading links
- PDF, CSV, and iCal export
- Print-friendly HTML layout
- URL-driven preset generation so plans can be shared easily

## Tech Stack

- PHP for the page shell and document title logic (`index.php`, `title.php`)
- JavaScript/jQuery for UI interactions and generation logic (`app.js`, `plans.js`, `renderers.js`, `helpers.js`)
- Static Bible data files (`bible.data.js`, `bible.data.languages.js`, `bible.data.wordcounts.js`, `bible.reference.js`, `bible.plans.js`, `bible.pericopes.js`)
- Front-end styling in `style.css`

## Repository Structure

```text
.
├── app.js                     # Main app logic and event handlers
├── bible.data.js             # Core Bible book metadata
├── bible.data.languages.js   # Translated names/data for languages
├── bible.data.wordcounts.js  # Word count metadata
├── bible.pericopes.js         # Pericopes data
├── bible.plans.js            # Bible plan definitions and order data
├── bible.reference.js        # Reference lookups
├── bible.wordcounts.js       # Word count helpers
├── helpers.js                # Utility helpers
├── index.php                 # Primary web page
├── title.php                 # Dynamic page title generation
├── plans.js                  # Plan-building logic
├── renderers.js              # Output renderers for different formats
├── style.css                 # App styles
├── LICENSE                   # MIT license
├── *.png                     # App icons/assets
├── jquery.min.js             # jQuery dependency
├── jspdf.min.js              # PDF generation dependency
├── filesaver.min.js          # File saving utility
└── old/                      # Older project files
```

## Local Development

Because the app uses a PHP entry point and browser-side JavaScript, it can be served with any PHP-enabled web server.

### Run locally

From the repository root:

```bash
php -S localhost:8000
```

Then open:

```text
http://localhost:8000/
```

The project is static enough that a simple PHP local server is sufficient for development and testing.

## Example Usage

The app supports URL parameters for generated plans. Examples:

```text
/?start=01-01&books=OT,NT&logic=words
/?total=40&format=calendar&order=traditional&daysofweek=2,3,4,5,6,7&books=JHN&lang=en&logic=pericopes
/?format=list&total=180&books=OT&order=chronological
```

These URLs generate sample reading plans with different time frames, orders, and formats.

## Output and Export

The generated plan can be:

- viewed directly in the browser
- printed
- saved as CSV
- exported as ICS for calendar apps
- rendered into a PDF

## License

This project is licensed under the MIT License. See `LICENSE` for details.

## Credits

The project is authored by John Dyer and is hosted at `biblereadingplangenerator.com`.

## Notes

This is a data-heavy, front-end-driven tool. The Bible and plan metadata are bundled into JavaScript files, so the app is meant to behave like a self-contained reading planner rather than a backend service.
