# dumb-mp3-streamer

[![Donate](https://dl.ugjka.net/Donate-PayPal-green.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=UVTCZYQ3FVNCY)

Reads mp3 data from Stdin, and serves them over http (livestream)

```text
Usage: cat *.wav | lame - - | dumb-mp3-streamer [options...]

Options:
    -port       Portnumber for server (max 65535). Default: 8080
    -buffer     Number of seconds of mp3 audio to buffer at start. Default: 10
    -readsize   Number of seconds of mp3 audio to read at once. Default: 1
    -queue      Number of unsent chunks before dropping data. Default: 10
    -writebuff  Write buffer. Default: 32768
    -upnp       Use to forward the port on the router

```

Beware: doing something like `cat *.mp3 | dumb-mp3-streamer` can produce frankenstein streams.
Use [mp3cat](https://tomclegg.ca/mp3cat) instead!

Check the [Wiki](https://github.com/ugjka/dumb-mp3-streamer/wiki) for examples

## Installation

Precompiled binaries available under the releases page

Archlinux: [AUR](https://aur.archlinux.org/packages/dumb-mp3-streamer-git/)

### Manual installation using make

You need the Go compiler installed and make. The Go compliler can be under different names on different distributions. On debian flavors it is named `golang`, on archlinux you need `go` and `go-tools`. Check your distribution's support channels if you can't find it.

Once you have those, then you just run `make` and `sudo make install`

You can also specify an installation prefix e.g. `sudo make prefix=/usr install` if you don't want to install in `/usr/local`
