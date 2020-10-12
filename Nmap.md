### Nmap scanning :

Nmap is mostly used during penetrating test and every pentester should familiar with it. Even it's speed is quite slow it's results are more accurate and well structured compare to others.Also it comes with lots of script that are useful during vulnerability testing called as nmap script engine(nse).

## Installation: 
``````
apt install nmap 
````````
 for unix or other distro. Check installation guide at https://nmap.org/book/install.html

Nmap basic syntax for first 1000 port scanning:
``````
$ nmap -A -T4 IP/host
```````

Nmap comes with lots of user options and scanning methods, check their mannual for more detail: https://nmap.org/book/man.html

If no port range is specified, Nmap scans the 1,000 most popular ports.

- `-p <port1>-<port2>`: Scans a port range
- `-p <port1>,<port2>,...`: Scans a port list
- `-pU:53,U:110,T20-445`: Mix TCP and UDP
- `-r`: Scans linearly (does not randomize ports)
- `--top-ports <n>`: Scan n most popular ports
- `-p-65535`: Leaving off the initial port in range makes Nmap scan start at port 1
- `-p0-`: Leaving off the end port in range makes Nmap scan through p

## Port Status

- Open: This indicates that an application is listening for connections on this port.
- Closed: This indicates that the probes were received but there is no application listening on this port.
- Filtered: This indicates that the probes were not received and the state could not be established. It also indicates that the probes are being dropped by some kind of filtering.
- Unfiltered: This indicates that the probes were received but a state could not be established.
- Open/Filtered: This indicates that the port was filtered or open but Nmap couldn’t establish the state.
- Closed/Filtered: This indicates that the port was filtered or closed but Nmap couldn’t establish the state.

## Scan Types

- `-sn`: Probe only (host discovery, not port scan)
- `-sS`: SYN Scan
- `-sT`: TCP Connect Scan
- `-sU`: UDP Scan
- `-sV`: Version Scan
- `-O`: Used for OS Detection/fingerprinting
- `--scanflags`: Sets custom list of TCP using `URG ACK PSH RST SYN FIN` in any order

## Probing Options

- `-Pn`: Don't probe (assume all hosts are up)
- `-PB`: Default probe (TCP 80, 445 & ICMP)
- `-PS<portlist>` : Checks if ssytems are online by probing TCP ports
- `-PE`: Using ICMP Echo Request
- `-PP`: Using ICMP Timestamp Request
- `-PM`: Using ICMP Netmask Request

## Output Options

- `-oN`: Standard Nmap output
- `-oG`: Greppable format
- `-oX`: XML format
- `-oA`: <basename> Generate Nmap, Greppable, and XML output files using basename for files
  
