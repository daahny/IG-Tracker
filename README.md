# IG Tracker

Are you petty about others unfollowing you on Instagram? Do you not have a way to effectively track losers that unfollow you? Or cool people that follow you? **IG Tracker** is the solution.

This repo contains a set of scripts that use python's `instaloader` module to log into a pre-configured bot account, then pull a list of followers which is then stored and compared to against followers from future executions. An email is then sent to inform you of any differences in followers.

## Prerequisites

- An Instagram bot account
- An email bot account
- Python's `instaloader` module installed
- If your Instagram is private, your bot account must be following your Instagram

## Setup

1. Create `bot/` directory in `users/`
2. Add SMTP and IG credentials/arguments to `smtp.json` and `ig.json` respectively in `users/bot`
   - Use templates in `templates/smtp.json` and `templates/ig.json`
3. Run `tools/adduser.py` to create a user directory in `users/` with necessary user data


### Directory Structure
```
users/
├─ bot/
│  ├─ smtp.json
│  ├─ ig.json
├─ mary/
│  ├─ mary_followers.txt
│  ├─ mary_args.json
├─ bob/
│  ├─ bob_followers.txt
│  ├─ bob_args.json
```

## Usage

- The first time you run `igtracker.py`, a file will be created in the `users/<user>/` directory with a list of current followers
- Subsequent runs will extract followers from your Instagram and compare this set of followers to followers in the `users/<user>/<user>_followers.txt` file

Run using `python3 igtracker.py -u | --users [ users ... ]`
