## Rustscan 

Rustscan is a flexible port scanner built in Rust and is both faster and provides accurate results its support for Nmap is seamless and it provides better customizations such as changing flags for Nmap scan, saving the output in Nmap’s XML format.

## Installation guide :

```````
cargo install rustscan
```````
Also check installation guide at:
https://github.com/RustScan/RustScan

We can use basic scanning commands:

```````
rustscan scanme.nmap.org --ulimit 5000
```````

User also have other options:

``````
$ rustscan -h
USAGE:
    rustscan [FLAGS] [OPTIONS] [addresses]... [-- <command>...]

FLAGS:
        --accessible    Accessible mode. Turns off features which negatively affect screen readers
    -g, --greppable     Greppable mode. Only output the ports. No Nmap. Useful for grep or outputting to a file
    -h, --help          Prints help information
    -n, --no-config     Whether to ignore the configuration file or not
        --no-nmap       Turns off Nmap
        --top           Use the top 1000 ports
    -V, --version       Prints version information

OPTIONS:
    -b, --batch-size <batch-size>    The batch size for port scanning, it increases or decreases the speed of scanning.
                                     Depends on the open file limit of your OS.  If you use 65535 it will scan every port
                                     at the same time. Although, your OS may not support this [default: 4500]
    -p, --ports <ports>...           A list of comma separed ports to be scanned. Example: 80,443,8080
    -r, --range <range>              A range of ports with format start-end. Example: 1-1000
        --scan-order <scan-order>    The order of scanning to be performed. The "serial" option will scan ports in
                                     ascending order while the "random" option will scan ports randomly [default:
                                     serial]  [possible values: Serial, Random]
    -t, --timeout <timeout>          The timeout in milliseconds before a port is assumed to be closed [default: 1500]
    -u, --ulimit <ulimit>            Automatically ups the ULIMIT with the value you provided

ARGS:
    <addresses>...    A list of comma separated CIDRs, IPs, or hosts to be scanned
    <command>...      The Nmap arguments to run. To use the argument -A, end RustScan's args with '-- -A'. Example:
                      'rustscan -T 1500 127.0.0.1 -- -A -sC'. This command adds -Pn -vvv -p $PORTS automatically to
                      nmap. For things like --script '(safe and vuln)' enclose it in quotations marks \"'(safe and
                      vuln)'\"")
```````
Reference link : https://github.com/RustScan/RustScan
