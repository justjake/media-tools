# media-tools

Home media center automation for automatically sorting torrent downloads.
Recently re-written for a new FreeBSD +
[rtorrent](https://github.com/rakshasa/rtorrent) setup. Since Spotify pretty
much ended music downloading, I have little interest in Beets for the new
system.

What these configs do:

1. moves completed files from /torrents/downloading to /torrents/seeding
2. automatically files finished torrents by copying their contents into
   /media/{TV Shows,Movies,Anime}
3. is easily extensible by editing the `rtorrent-started` and
   `rtorrent-postprocess` shell scripts.

## setup

1. Install [FileBot](https://www.filebot.net/). I use the portable
   installation. Make sure `filebot` is available as a command in your `PATH`.

2. clone this repo, then symlink everything in ./bin into your `$PATH`.

3. Either copy rtorrent.rc to ~/.rtorrent.rc, or adjust your existing
   .rtorrent.rc to call `rtorrent-started` on boot, and `rtorrent-postprocess`
   when a download is finished. You should look over rtorrent.rc for more
   details.

4. adjust ./bin/media-tools-common to match your system. eg, change the
   `COPY_DESTINATION` variable from my /media to wherever you want to file your
   stuff.

## rtorrent config

rtorrent is an asshole to configure for the first time. I usually refer to the
rtorrent source code to figure out what commands and properties I can access.
