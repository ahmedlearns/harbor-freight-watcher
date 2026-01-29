# Harbor Freight Price Watcher

Monitors Harbor Freight product prices and sends email alerts when they drop below your threshold.

## Setup

1. Fork this repo
2. Add secrets in **Settings > Secrets and variables > Actions**:
   - `EMAIL_RECIPIENTS` - comma-separated emails
   - `SMTP_USER` - Gmail address
   - `SMTP_PASS` - Gmail App Password ([create one here](https://myaccount.google.com/apppasswords))

3. Edit `watchlist.json` to add items:

```json
{
  "items": [
    {
      "name": "Some Tool",
      "url": "https://www.harborfreight.com/some-tool-12345.html",
      "threshold": 29.99
    }
  ]
}
```

Runs hourly via GitHub Actions. Trigger manually from Actions tab to test.

## Local Testing

```bash
pip install -r requirements.txt
EMAIL_RECIPIENTS=you@email.com python hf_watcher.py
```
