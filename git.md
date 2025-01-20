# Notes on Git

These notes were taken while reading the book [Pro Git](https://git-scm.com/book/en/v2) by Scott Chacon & Ben Straub. This is not meant to be an introduction to git (for that read the book), but rather a 'cheatsheet' that I can refer back to.

Date: Sun 19 Jan 2025 09:19:49 GMT

## First-Time Git Setup

Config file lives in ~/.gitconfig or ~/.config/git/config. This is user-wide (system-wide in /etc/gitconfig). For repository-specific config use .git/config. More specific config overrides more general ones.

```bash
git config --system <key> <value>   # Set key = value system-wide
git config --global <key> <value>   # Set key = value user-wide
git config --local <key> <value>    # Set key = value repository-wide

git config --show-origin <key>      # Check value of key (and where it was set)
git config --list --show-origin     # List current configuration and where it was set
```

When first installing git, you want to do something like this:

```bash
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

## Getting Help

If you are unsure of any git command, use the following.

```bash
git help <verb>   # Open man-page of <verb>
git <verb> -h     # Display a summary of man-page
```

## Getting a Git Repository
