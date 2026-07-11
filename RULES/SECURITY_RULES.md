# Security Rules

## Sensitive information

Never commit:

- Passwords
- API keys
- Access tokens
- Private certificates
- Service account keys
- Internal company credentials
- Personally identifiable information
- Confidential company datasets

Use sample or anonymized data for development.

## Frontend limitations

Anything shipped to a browser must be treated as visible to the user.

Never place a secret in:

- HTML
- CSS
- Client-side JavaScript
- Public JSON
- GitHub Pages source code

## Access control

Do not treat a hidden button or hidden URL as authorization.

When authentication or permissions matter, enforce them in the backend.

## Google Apps Script

- Use the minimum required permissions.
- Document who the web app executes as.
- Document who may access the web app.
- Do not expose unrestricted write endpoints without validation.
- Protect spreadsheet identifiers and operational data when necessary.

## Data handling

- Collect only data required for the stated purpose.
- Define retention and deletion expectations when records may be sensitive.
- Do not log confidential content unnecessarily.
- Show safe error messages to users.
