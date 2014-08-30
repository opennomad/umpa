umpa
====

A tool to sync MPD playlists to an Android phone via MTP

Right now the tools allows syncing of a playlist from MPD in M3U format to an android device.

## Installation

Simply copy the *umpa* script to somewhere, since it is written in bash it should run pretty much anywhere.

You will also need the *gvfs-bin* tools. On Ubuntu that should be as easy as running:

    sudo apt-get install gvfs-bin

## Configuration

create a file in your $HOME called .umpa and populate it with the appropriate locatoins. Here is an example

    PHONE_GUESS="/run/user/${UID}/gvfs/mtp*/Card/Music"
    MUSIC_DIR="/home/matthias/Music"
    PLAYLIST_DIR="/home/matthias/.mpd/Playlists"

The PHONE_GUESS should work and will use your UID to find the mtp device. If you have more than one connected it may fail. This PHONE_GUESS reflects my music which is on the SD card in a directory called Music. You might need to explore your layout.

The MUSIC_DIR is where you keep your music.

The PLAYLIST_DIR is where you tell MPD to keep the playlists.

## Running it

    umpa -s Great_Tunes # leave the .m3u off

you can also add -v for verbose output or -n for a dry-run that doesn't copy anything.
