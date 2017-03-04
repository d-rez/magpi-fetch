# magpi-fetch
### Fetch and send new MagPi issues to Dropbox to be downloaded by your ebook reader.

---

I enjoy my monthly MagPi on my ebook reader. However, remembering about it, downloading, connecting my reader and copying the file seemed like a tedious thing to do. Since I have a Raspberry Pi running at home lazily, I decided to add one more thing to the not-so-long list of its tasks.

This will work with all Pocketbooks and ebook readers supporting Dropbox folder sync. It lets the e-book sync files automatically with a remote folder - all you have to do is push files to it. The code can also be adjusted to download files locally and use e.g. some e-mail services. Note, however, that lots of them limit max filesize to 10MB.

The config file contains all known issues that won't be re-synchronized. If it's missing it will be created in the script directory and optionally log to a file (see --help). To keep it running regularly just add it to your monthly crontab and automation will take over

You will probably want to remove my_secrets imports and definitions and replace them with your own API keys / Dropbox folder or simply create these files yourself.

##Usage:

    ./magpi.py --help

##Schedule:
Simply add it to your crontab somewhere close to usual MagPi release dates. You might want to use `--log_file --debug` params.

Remember to either edit your credentials in the file itself (see config section) or put them in a separate `my_secrets.py` file

##Requires:

* Python3
* `sudo pip3 install dropbox`
* `sudo pip3 install beautifulsoup4`
