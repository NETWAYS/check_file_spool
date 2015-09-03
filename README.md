check_file_spool
================

Nagios/Icinga plugin to check if a spool directory contains old files, that might not have been processed.

## Modes

Two modes are possible:

### seen (default)

Records when a filename is seen for the first time, and records that timestamp in a `seenfile`.

The age is calculated by the time since the file has been seen first.

This avoids problems when the timestamp of the spoolfile is not touched by the spooling daemon.

### mtime

Checks the file age based on the file's modification time.

## Usage

Here are a few examples.

```
check_file_spool -p /var/spool/mydaemon/import -w 60 -c 120

check_file_spool -p /var/spool/mydaemon/export -w 60 -c 120 -m mtime

check_file_spool -p /var/spool/mydaemon/import -w 60 -c 120 --seenfile /data/cluster/tmp/check_file_spool
```

See `--help` for all arguments.

## License

    Copyright (c) 2015 NETWAYS GmbH <info@netways.de>
    Copyright (c) 2015 Markus Frosch <markus.frosch@netways.de>

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.
