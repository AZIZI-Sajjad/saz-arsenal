# saz-tcpdump

#plateform/linux
#target/local
#cat/PRIVESC
#cat/PERSIST
#cat/AZIZI-Sajjad
#tag/tcpdump


## tcpdump - specific host,
```
tcpdump ’host <ipaddress>’;
  #### Exemple : tcpdump ‘host 10.10.10.1’
```


## tcpdump - specific source host,
```
tcpdump ’src host <ipaddress>’;
  #### Exemple : tcpdump ‘src host 10.10.10.1’
```


## tcpdump - specific destination host,
```
tcpdump ’dst host <ipaddress>’;
  #### Exemple : tcpdump ‘dst host 10.10.10.1’
```


## tcpdump - specific network,
```
tcpdump ’net <network address>’;
  #### Exemple : tcpdump ‘net 10.10.10’
```


## tcpdump - specific source network,
```
tcpdump ’src net <network address>’;
  #### Exemple : tcpdump ‘src net 10.10.10’
```


## tcpdump - specific destination network,
```
tcpdump ’dst net <network address>’;
  #### Exemple : tcpdump ‘dst net 10.10.10’
```


## tcpdump - specific port,
```
tcpdump ’port <port-number>’;
  #### Exemple : tcpdump ‘port 21’
```


## tcpdump - specific source port,
```
tcpdump ’src port <port-number>’;
  #### Exemple : tcpdump ‘src port 21’
```


## tcpdump - specific destination port,
```
tcpdump ’dst port <port-number>’;
  #### Exemple : tcpdump ‘dst port 21’
```


## tcpdump - specific host for the particular port,
```
tcpdump ‘host <ipaddress> and port <port-number>’;
  #### Exemple : tcpdump ‘host 10.10.10.1 and port 21’
```


## tcpdump - the specific host for all the ports except SSH,
```
tcpdump ‘host <ipaddress> and port not <port-number>’;
  #### Exemple : tcpdump ‘host 10.10.10.1 and port not 22’
```


## tcpdump - specific protocol,
```
tcpdump ’proto ICMP’;
  #### Exemple : 
	tcpdump ’proto UDP’
	tcpdump ’proto TCP’
	tcpdump ‘arp’
```


## tcpdump - particular interface,
```
tcpdump interface <interface>;
  #### Exemple : tcpdump interface PortB
```


## tcpdump - specific port of a particular interface,
```
tcpdump interface <interface> ‘port <port-number>’;
  #### Exemple : tcpdump interface PortB ‘port 21’
```
