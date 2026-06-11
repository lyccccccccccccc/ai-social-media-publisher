# AI Social Media Publisher

A sanitized portfolio version of an automated social media publishing workflow. The project pulls image assets from OneDrive, generates Instagram captions with OpenAI, uploads media to WordPress, publishes posts or stories through the Meta Graph API, archives processed files, and can send SMTP alert emails when jobs fail.

## Features

- Publishes Instagram feed posts and stories from OneDrive folders.
- Generates captions from asset filenames using the OpenAI API.
- Uploads media to WordPress before publishing.
- Archives successful and failed assets into configured OneDrive folders.
- Includes health checks, token checks, and optional email alerts.
- Provides GitHub Actions workflows for scheduled or manual runs.

## Project Structure

- `post_publisher.py`: feed post workflow.
- `story_publisher.py`: story workflow.
- `wordpress_media.py`: WordPress media upload helper.
- `health_check.py`: environment and API connectivity checks.
- `token_maintenance.py`: Meta token validity check.
- `alert_email.py`: SMTP alert helper.
- `.github/workflows/`: GitHub Actions automation.
- `.env.example`: placeholder configuration template.

## Setup

1. Create a virtual environment.
2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Copy `.env.example` to `.env` and replace placeholders with your own credentials.
4. Keep `.env` private. It is intentionally ignored by Git.

## Required Services

- Microsoft Graph API access for OneDrive.
- Meta Graph API access for Instagram publishing.
- OpenAI API access for caption generation.
- WordPress application password for media uploads.
- Optional SMTP account for alerts.

## Common Commands

```bash
python health_check.py
python post_publisher.py
python story_publisher.py
python token_maintenance.py
python send_test_alert.py
```

Set `DRY_RUN=true` while testing to skip live Instagram publishing.

## Security Notes

This repository is prepared for portfolio use. Real credentials, private account identifiers, emails, domains, client names, generated media, logs, and cache folders should not be committed. Use GitHub repository secrets for workflow configuration.
