# AutoScout Team Data

This repository is the shared data store for FTC AutoScout team accounts.

## Important: public repository

This repository is intentionally public so AutoScout can use GitHub's free repository storage. **Anyone can view, download, copy, and retain anything committed here.** This includes:

- Team account numbers
- Password verification records (salted PBKDF2-SHA256 hashes, not plaintext passwords)
- Match notes and team notes
- Uploaded scouting photos
- Saved scouting sessions

Do not store private, sensitive, or personally identifying information here. Use scouting observations about robots and matches only. Do not reuse a personal password as a team password.

## How it works

The AutoScout Cloudflare Worker writes team data into folders created automatically as teams register:

```
teams/
  12928/
    account.json
    match-notes.json
    team-notes.json
    photos/
    sessions/
```

The repository starts empty apart from this README. The Worker creates each team's files as needed.

## Limits

GitHub and Cloudflare free plans have usage, request, and storage limits. This is intended for normal FTC team scouting use, not unlimited storage or guaranteed uptime.

## Administration

Keep the GitHub write token, password pepper, and registration key in Cloudflare Worker secrets only. Never commit those values to this repository or to the AutoScout website repository.
