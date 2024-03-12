# IG Tracker

Are you petty about others unfollowing you on Instagram? Do you not have a way to effectively track losers that unfollow you? Or cool people that follow you? **IG Tracker** is the solution.

This repo contains a set of scripts that use python's `instaloader` module to log into a pre-configured bot account, then pull a list of followers which is then stored and compared to against followers from future executions. An email is then sent to inform you of any differences in followers.

## Prerequisites

- An Instagram bot account
- An email bot account
- Python's `instaloader` module installed
- If your Instagram is private, your bot account must be following your Instagram

## Setup

1. Rename `templates/sample_args.json` to `templates/args.json`
2. Configure `templates/args.json` with your instagram bot settings and your email bot settings
3. Run `tools/adduser.py` to create a user directory in `users/` and files with required user data

## Usage

- The first time you run `ig-tracker.py`, a file will be created in the `users/<user>/` directory with a list of current followers
- Subsequent runs will extract followers from your Instagram and compare this set of followers to followers in the `users/<user>/<user>_followers.txt` file

Run using `python3 ig-tracker.py -u|--users [ users ... ]`
