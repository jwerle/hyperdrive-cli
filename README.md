hyperdrive-cli
==============

Simpe CLI for a HyperDrive as a quick alternative to
[dat-cli](https://github.com/datproject/dat).

## Installation

```sh
$ npm install hyperdrive-cli -g
```

## Usage

```sh

Usage: hyperdrive: [-hDV] [--help] [--version]
       hyperdrive: <command> [options] -- [pathspec]


Commands:
  init           Initialize a new archive
  info           Show public information about the archive
  stat           Stat a file or directory
  read           Read a range from a file (Requires public key)
  serve          Serve a hyperdrive over HTTP
  write          Write to a file (Requires secret key)
  unlink         Remove a file (Requires secret key)
  download       Download file or entire archive (Requires public key)

Aliases:
  init           i, initialize
  read           get, cat
  serve          http
  write          add, put, set
  unlink         rm, delete, del, remove
  upload         up
  readdir        list, ls, l
  download       down

Options:
  --help, -h     Show this message
  --version, -V  Output program version
  --key, -k      Hyperdrive archive public key
  --debug, -D    Enable debug output (DEBUG=hyperdrive:cli*)
  --start, -S    Range start offset when using ranged streams
  --end, -E      Range end offset when using ranged streams
  --length, -L   Range length when using ranged streams
  --port, -p     Port to bind HTTP server to
  --ram, -M      Store in random access memory
```

## API

### `$ hyperdrive init`

Initialize a new archive

### `$ hyperdrive info`

Show public information about the archive

### `$ hyperdrive stat`

Stat a file or directory

### `$ hyperdrive read`

Read a range from a file (Requires public key)

### `$ hyperdrive write`

Write to a file (Requires secret key)

### `$ hyperdrive serve`

Serve a hyperdrive over HTTP

### `$ hyperdrive unlink`

Remove a file (Requires secret key)

### `$ hyperdrive download`

Download file or entire archive (Requires public key)

## Configuration

This module uses [rc](https://github.com/dominictarr/rc) to allow things
like [hyperdiscovery](https://github.com/karissa/hyperdiscovery) to be
configured. Hyperdrive options like the secret key for hypercore can also be
specified here. Create a `.hyperdriverc` file with your hyperdrive. See below
for an example object.

```js
{
  "drive": {
    "sparse": true,
    "secretKey": "..."
  },

  "discovery": {
    "live": true,
    "dns": {
      "server": ["discovery1.publicbits.org"],
      "domain": "dat.local"
    },
  }
}
```

## License

MIT
