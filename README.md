# bt: a bitorrent library for the shell

bt is a shell utility for dealing with bittorrent-related
things. Use it from the command line, put it in your scripts, it's alright.

Right now, bt is implemented in python (3), and really only deals with .torrent
(AKA metainfo) files. Actually creating torrents is coming soon(tm), so
use `transmission-create` until then.

## Installation

Clone this repository, run `pip[3] install`, then you should be good.

## Usage

    bt --help

## Examples

Add a [BEP39-compliant][1] update URL, using the ever-useful [`jq`][0]:

    bt bj example.torrent | jq ".info.\"update-url\" = \"$URL\"" |\
    bt jb > example-updateable.torrent

[1]: http://www.bittorrent.org/beps/bep_0039.html
[0]: http://stedolan.github.io/jq/
