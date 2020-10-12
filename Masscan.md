
# MASSCAN: Mass IP port scanner

This is an Internet-scale port scanner. It can scan the entire Internet
in under 6 minutes, transmitting 10 million packets per second,
from a single machine.

It's input/output is similar to `nmap`, the most famous port scanner.
When in doubt, try one of those features.

Internally, it uses asynchronous tranmissions, similar to port scanners
like  `scanrand`, `unicornscan`, and `ZMap`. It's more flexible, allowing
arbitrary port and address ranges.

## Building

On Debian/Ubuntu, it goes something like this:
````
$ sudo apt-get install git gcc make libpcap-dev
$ git clone https://github.com/robertdavidgraham/masscan
$ cd masscan
$ make
````
This puts the program in the `masscan/bin` subdirectory. You'll have to
manually copy it to something like `/usr/local/bin` if you want to
install it elsewhere on the system.

The source consists of a lot of small files, so building goes a lot faster
by using the multi-threaded build:
```
$ make -j
````
For more info. visit: https://github.com/robertdavidgraham/masscan/blob/master/README.md

## Usage

Usage is similar to `nmap`. To scan a network segment for some ports:
````
$ masscan -p80,8000-8100 10.0.0.0/8
````
This will:
* scan the 10.x.x.x subnet, all 16 million addresses
* scans port 80 and the range 8000 to 8100, or 102 addresses total
* print output to `<stdout>` that can be redirected to a file

To see the complete list of options, use the `--echo` feature. This
dumps the current configuration and exits. This output can be used as input back
into the program:
``````
$ masscan -p80,8000-8100 10.0.0.0/8 --echo > xxx.conf
$ masscan -c xxx.conf --rate 1000
``````

Reference: https://github.com/robertdavidgraham/masscan
