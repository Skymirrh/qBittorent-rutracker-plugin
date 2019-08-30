qBittorrent RuTracker plugin
===============================

qBittorrent search engine plugin for RuTracker. In case [rutracker.org](https://rutracker.org) is DNS blocked, the plugin will try to reach [official RuTracker mirrors](http://rutracker.wiki/%D0%A7%D1%82%D0%BE_%D0%B4%D0%B5%D0%BB%D0%B0%D1%82%D1%8C,_%D0%B5%D1%81%D0%BB%D0%B8_%D0%B2%D0%B0%D0%BC_%D0%B7%D0%B0%D0%B1%D0%BB%D0%BE%D0%BA%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD_%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF_%D0%BD%D0%B0_rutracker.org#.D0.97.D0.B5.D1.80.D0.BA.D0.B0.D0.BB.D0.B0_rutracker.org) instead.

It follows the [writing plugin guide recommandations](https://github.com/qbittorrent/search-plugins/wiki/How-to-write-a-search-plugin).

Installation
------------
Python 3.6 required.
* [Download the latest release.](https://github.com/Skymirrh/qBittorrent-RuTracker-plugin/releases/latest)
* Install package via pip (fresh virtualenv recommended)
* Rum module via `python3 -m qbit_rutracker --dest=. --ini=qbittorrent-rutracker.ini`
  Destination could be:
  * Windows: `%localappdata%\qBittorrent\nova3\engines\`
  * Linux: `~/.local/share/data/qBittorrent/nova3/engines/`
  * OS X: `~/Library/Application Support/qBittorrent/nova3/engines/`
* Add your RuTracker credentials in ini file.
* RuTracker search engine should now be available in qBittorrent.

Troubleshooting
---------------
If you get no results from RuTracker when you search something, please:
  * Check that at least one mirror from the list of [official RuTracker mirrors](http://rutracker.wiki/%D0%A7%D1%82%D0%BE_%D0%B4%D0%B5%D0%BB%D0%B0%D1%82%D1%8C,_%D0%B5%D1%81%D0%BB%D0%B8_%D0%B2%D0%B0%D0%BC_%D0%B7%D0%B0%D0%B1%D0%BB%D0%BE%D0%BA%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD_%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF_%D0%BD%D0%B0_rutracker.org#.D0.97.D0.B5.D1.80.D0.BA.D0.B0.D0.BB.D0.B0_rutracker.org) is working.
  * Check that you are not captcha-blocked (try to manually connect to the website: after logging in once, the captcha will disappear and the script will work).
  * Check that the script credentials are correct (try to manually connect to the website by copy/pasting username and password from `rutracker.py`).
  * If it still does not work, follow the steps for reporting a bug below.

Bug reporting
-------------
* Find your qBittorrent version (see qBittorrent title bar).
* Find your Python version (run `python --version` from command prompt).
* Navigate to qBittorrent search engines directory:
  * Windows: `%localappdata%\qBittorrent\nova3\engines\`
  * Linux: `~/.local/share/data/qBittorrent/nova3/engines/`
  * OS X: `~/Library/Application Support/qBittorrent/nova3/engines/`
  * *Note: If you use Python 2 instead of Python 3, replace `nova3` with `nova`.*
* Edit `rutracker.py` and replace `logger.setLevel(logging.WARNING)` with `logger.setLevel(logging.INFO)`.
* Move to parent directory (`cd ..` or manual browsing to `nova3`).
* From the `nova3` directory, run `python nova2.py rutracker all archlinux` in a command prompt.
* [Create a new issue](https://github.com/Skymirrh/qBittorrent-RuTracker-plugin/issues/new) and fill out the form with the information above.