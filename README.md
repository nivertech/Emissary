Emissary
========

For researchers, programmers and news junkies who want personally curated news archives.
Emissary is a web content extractor that has a RESTful API.
Emissary stores the full text of linked articles from RSS feeds or URLs containing links.

Cron for indexing HTTP resources.

--------
<pre>
Emissary is a daemon for periodically extracting
the body text of online articles from sites like news agencies and blogs.

A client library is included to integrate with other programs.

./Emissary --start        (default)
./Emissary --stop         Stop Emissary immediately.
./Emissary --restart
./Emissary --foreground   Don't daemonize.
./Emissary --logfile      Write output to file.
./Emissary --debug        Enable debugging output.
./Emissary --add-user     Add a user to the system.
./Emissary --interactive  Launch interactive shell.
./Emissary --run-as       (defaults to the invoking user)
./Emissary --driver       (defaults to sqlite)
./Emissary --db           (defaults to ./cache.db)
./Emissary --address      (defaults to 127.0.0.1)
./Emissary --port         (defaults to 6362)


Add feeds by writing them to a file and then pipe the file into Emissary:
user@host $ cat feeds.txt
db_limit 5g
# url                    name    minute  hour    day month   weekday
http://feed.tld/rss     'feed'   0       6,12    *   0-11    mon-fri

user@host $ cat feeds.txt | ./Emissary
user@host $ ./Emissary --add-user
user@host $ ./Emissary
user@host $ ./Emissary --interactive

(3,189) > help
</pre>

#### INSTALLATION:
--------
gevent==1.0

dataset==0.3.14

requests==2.1.0

feedparser==5.1.3

goose-extractor==1.0.6


Debian-based systems may require the following:

sudo aptitude install zlib1g-dev libxml2-dev libxslt1-dev python-dev libevent

sudo pip install lxml BeautifulSoup cssselect feedparser gevent requests sqlalchemy dataset
