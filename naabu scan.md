# naabu port scanning

Naabu is a great tool from project discovery that is used to scan ports with fair accuracy and speed and with its ease of usability we can easily run it along with other tools from project discovery like subfinder or httpx. The basic host scanning command looks like this:
````
 $ naabu -host scanme.nmap.org -o output.txt
````
## Installation: 
naabu is written in go lang. User need previous setup of go lang.
### Using go lang.
```````
GO111MODULE=on go get -u -v github.com/projectdiscovery/naabu/v2/cmd/naabu
```````
### Using github :
```````
git clone https://github.com/projectdiscovery/naabu.git
```````

User can also specifies command syntax according to need 
````
$ naabu --help
 Usage of naabu:
  -Pn
        Use ping probes for verification of host
  -debug
        Enable debugging information
  -exclude string
        Specifies a comma-separated list of targets to be excluded from the scan (ip, cidr)
  -exclude-file string
        This offers the same functionality as the -exclude option, except that the excluded targets are provided in a newline-delimited file
  -exclude-ports string
        Ports to exclude from enumeration
  -hL string
        File containing list of hosts to enumerate ports
  -host string
        Host to find ports for
  -json
        Write output in JSON lines Format
  -nC
        Don't Use colors in output
  -o string
        File to write output to (optional)
  -oD string
        Directory to write enumeration results to (optional)
  -ports string
        Ports to enumerate for on hosts (top-1000, full, custom, default: top-100)
  -ports-file string
        File containing ports to enumerate for on hosts
  -rate int
        Rate of port scan probe requests (default 1000)
  -retries int
        Number of retries for the port scan probe (default 1)
  -silent
        Show only host:ports in output
  -t int
        Number of concurrent goroutines for resolving (default 10)
  -timeout int
        Millisecond to wait before timing out (default 700)
  -v    Show Verbose output
  -verify
        Validate the ports again
  -version
        Show version of naabu
````

Reference link: https://github.com/projectdiscovery/naabu
