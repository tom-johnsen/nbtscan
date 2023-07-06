# NBTScan

NBTscan version 1.6 , Forked by Tom Johnsen, original Copyright (C) 1999-2003 Alla Bezroutchko

NBTscan is a program to scan IP networks for NetBIOS name information. It sends NetBIOS status query to each address in supplied range and lists received information in human readable form. For each responded host it lists IP address, NetBIOS computer name, logged-in user name and MAC address (such as Ethernet).

## License

This program is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation; either version 2 of the License, or (at your option) any later version.

## Installation

```shell
./configure
make
sudo make install
```

## Usage

```shell
nbtscan [-v] [-d] [-e] [-l] [-t timeout] [-b bandwidth] [-r] [-q] [-s separator] [-m retransmits] (-f filename) address
    -v              # verbose output. Print all names receivedfrom each host.
    -d              # dump packets. Print whole packet contents.
    -e              # Format output in /etc/hosts format.
    -l              # Format output in lmhosts format. Cannot be used with -v, -s or -h options.
    -t timeout      # wait timeout in milliseconds for a response. Default is 1.
    -b bandwidth    # Output throttling. Slow down outputso that it uses no more that bandwidth bps.Useful on slow links, so that ougoing queriesdon't get dropped.
    -r              # use local port 137 for scans. Win95 boxesrespond to this only. You need to be root to use this option on Unix.
    -q              # Suppress banners and error messages.
    -s separator    # Script-friendly output. Don't print column and record headers, separate fields with separator.
    -h              # Print human-readable names for services, can only be used with -v option.
    -m retransmits  # Number of retransmits. Default 0.
    -f filename     # Take IP addresses to scan from file filename
    -f -            # Makes nbtscan take IP addresses from stdin.
    address         # Can either be single IP like 192.168.1.1 or range of addresses in one of two forms: xxx.xxx.xxx.xxx/xx or xxx.xxx.xxx.xxx-xxx.
```

## Examples

```shell
nbtscan -r 192.168.1.0/24           # Scans the whole C-class network.
nbtscan 192.168.1.25-137            # Scans a range from 192.168.1.25 to 192.168.1.137
nbtscan -v -s ':' 192.168.1.0/24    # Scans C-class network. Prints results in script-friendly format using colon as field separator.
nbtscan -f iplist                   # Scans IP addresses specified in file iplist.
```

## Limitations

Windows version has a certain limitation: you cannot scan Win95 hosts with it because Windows 95 always sends responses to name queries to port 137, and you cannot bind to port 137 under Windows (it is already taken by Windows itself).

When talking to Samba boxes nbtscan always reports the MAC address being 00-00-00-00-00-00. This is because Samba sends that as MAC address. Nbtscan just displays what it gets.
