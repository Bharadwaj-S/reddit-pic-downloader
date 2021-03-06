# Reddit picture downloader

This Python script downloads the top images from a subreddit and automatically deletes pictures that are older than a specified number of days. Can be combined with a cron job to automatically download images every day.

## How to use
### 1. Get Client ID and Secret from Reddit
See https://github.com/reddit-archive/reddit/wiki/OAuth2-Quick-Start-Example#first-steps

### 2. Create required_info.py
Create a file `required_info.py` and open it in your favorite text editor

Add the following information to it:
```
CLIENT_ID = <Client ID from Reddit App>
SECRET = <Secret from Reddit App>
SUBREDDIT = "<name of subreddit e.g. pics, earthporn etc."
LOG_FILE_NAME = "desired/path/to/log/file"
DEST_DIR = "path/to/where/pics/should/be/stored"
CLEANUP_DAYS = <Number of days after which the pics should be deleted"
TRASH_PATH = "path/to/Trash (usually Windows - C:\$Recycle.Bin, OSX - Users/<your username>/.Trash, Linux - ~/.local/share/Trash)"
```

### 3. Automating the download
#### On Linux and MacOS
Open your terminal and type `crontab -e`. Here, enter the line `0 0 * * * /path/to/script.py`

This video is a quick intro to crontab if you've never used it before https://www.youtube.com/watch?v=QZJ1drMQz1A
