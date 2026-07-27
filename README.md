# DailyPapers 📜

A daily collection of arXiv papers from **cs.CL** (Computation and Language) and **cs.IR** (Information Retrieval).

Papers are fetched via the [arXiv API](https://info.arxiv.org/help/api/tou.html) using [arxiv.py](https://github.com/lukasschwab/arxiv.py), saved as Markdown files organized by date, and updated automatically through GitHub Actions.

## Browse

Find papers by date using the interactive calendars:

- [cs.CL calendar](calendar/calendar_CL.md)
- [cs.IR calendar](calendar/calendar_IR.md)

## Run locally

Requires Python 3.x.

```bash
pip install arxiv
python arxiv_collect.py --catalog cs.CL --start_date 2026-07-01 --end_date 2026-07-27 --order descending
```

| Flag | Description |
|---|---|
| `--catalog` | arXiv category (`cs.CL`, `cs.IR`, etc.) |
| `--start_date` | Start of date range (`YYYY-MM-DD`) |
| `--end_date` | End of date range (`YYYY-MM-DD`) |
| `--order` | `ascending` or `descending` |

To regenerate the calendar files after fetching:

```bash
python calendar_generator.py
```

## How it works

A cron job runs daily at 02:00 UTC via GitHub Actions. It picks up from the last collected date, fetches new papers for both categories, regenerates the calendars, and commits the results.

See [`.github/workflows/update_papers.yml`](.github/workflows/update_papers.yml) for the workflow.

## Disclaimer

If there are any concerns regarding copyright or content, please open an issue or contact the repository owner directly.

## License

This project is licensed under the [MIT License](LICENSE).
