# doh-http2

This script is used to perform DNS Over HTTPs queries.

| Supported Platforms  |
| ---------------------|
| Linux |


| Supported Protocols  |
| ---------------------|
| IPv4 |
| IPv6 |

## Prerequisites

* Python3
* PIP 

## Installation

```

$ git clone git@github.com:chanchal127/doh-http2.git
$ cd doh-http2
$ pip install -r dependency
$ ./final_touch
Initial setup is done..!!
Now you can use doh-http2 script to perform DoH queries from you terminal..!!

```

## Usages

```

$ doh-http2 --help

usage: doh-query [-h] [--dns DNS] [--edns] [--padding] [--cert CERT] [--post] [--nocert] [--timeout TIMEOUT] domain [A,AAAA,CNAME,MX,TXT]

Perform DNS queries over HTTP with a default GET request.

positional arguments:
  domain               The Domain Name System to resolve.
  A,AAAA,CNAME,MX,TXT  Supported DNS Resourse Records

optional arguments:
  -h, --help           show this help message and exit
  --dns DNS            Enter the DoH Server IP or Hostname. If you are using ipv6 then use proper format []. For example - [ipv6]. Default server is dns.google
  --edns               If you need to enable EDNS
  --padding            Pad with EDNS(0)
  --cert CERT          Enter the absolute path of the certificate
  --post               For post request
  --nocert             No certificate varification request
  --timeout TIMEOUT    Maximum time in seconds that you allow the whole operation to take. Default is 60 secs.

Example:
doh-query test.com A --dns 10.10.10.10 --nocert --edns --padding
doh-query example.com A --dns [2403:8600:80cf:e10c:3920::36] --nocert --edns

```

## Sample Output

##### DoH query on IPv4 Server with the help of GET request with EDNS0 padding.

```

$ doh-http2 test.com A --dns 10.197.36.36 --nocert --edns --padding

###[ DNS ]###
  id        = 256
  qr        = 1
  opcode    = QUERY
  aa        = 0
  tc        = 0                                                                                                                                                                 rd        = 1                                                                                                                                                                 ra        = 1                                                                                                                                                                 z         = 0                                                                                                                                                                 ad        = 0                                                                                                                                                                 cd        = 0                                                                                                                                                                 rcode     = ok                                                                                                                                                                qdcount   = 1                                                                                                                                                                 ancount   = 1                                                                                                                                                                 nscount   = 0                                                                                                                                                                 arcount   = 1
  \qd        \
   |###[ DNS Question Record ]###
   |  qname     = 'test.com.'
   |  qtype     = A
   |  qclass    = IN
  \an        \
   |###[ DNS Resource Record ]###
   |  rrname    = 'test.com.'
   |  type      = A
   |  rclass    = IN
   |  ttl       = 1445
   |  rdlen     = None
   |  rdata     = 115.183.122.234
  ns        = None
  \ar        \
   |###[ DNS OPT Resource Record ]###
   |  rrname    = '.'
   |  type      = OPT
   |  rclass    = 1220
   |  extrcode  = 0
   |  version   = 0
   |  z         = 0
   |  rdlen     = None
   |  \rdata     \
   |   |###[ DNS EDNS0 TLV ]###
   |   |  optcode   = 12
   |   |  optlen    = 411
   |   |  optdata   = '\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00'

None

Response packet Length: 468 Bytes

Total Time Taken: 22.82 ms

```



##### DoH query on IPv4 Server with the help of POST request with EDNS0 padding.

```

$ doh-http2 test.com A --dns 10.197.36.36 --nocert --edns --padding --post

###[ DNS ]###
  id        = 256
  qr        = 1
  opcode    = QUERY
  aa        = 0
  tc        = 0                                                                                                                                                                 rd        = 1                                                                                                                                                                 ra        = 1                                                                                                                                                                 z         = 0                                                                                                                                                                 ad        = 0                                                                                                                                                                 cd        = 0                                                                                                                                                                 rcode     = ok                                                                                                                                                                qdcount   = 1                                                                                                                                                                 ancount   = 1                                                                                                                                                                 nscount   = 0                                                                                                                                                                 arcount   = 1
  \qd        \
   |###[ DNS Question Record ]###
   |  qname     = 'test.com.'
   |  qtype     = A
   |  qclass    = IN
  \an        \
   |###[ DNS Resource Record ]###
   |  rrname    = 'test.com.'
   |  type      = A
   |  rclass    = IN
   |  ttl       = 1345
   |  rdlen     = None
   |  rdata     = 115.183.122.234
  ns        = None
  \ar        \
   |###[ DNS OPT Resource Record ]###
   |  rrname    = '.'
   |  type      = OPT
   |  rclass    = 1220
   |  extrcode  = 0
   |  version   = 0
   |  z         = 0
   |  rdlen     = None
   |  \rdata     \
   |   |###[ DNS EDNS0 TLV ]###
   |   |  optcode   = 12
   |   |  optlen    = 411
   |   |  optdata   = '\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00'

None

Response packet Length: 468 Bytes

Total Time Taken: 25.69 ms

```

##### DoH query on IPv6 Server with the help of GET request without EDNS0.

```
$ doh-http2 test.com AAAA --dns [2403:8600:80cf:e10c:3920::36] --nocert

###[ DNS ]###
  id        = 256
  qr        = 1
  opcode    = QUERY
  aa        = 0
  tc        = 0
  rd        = 1
  ra        = 1
  z         = 0
  ad        = 0
  cd        = 0
  rcode     = ok
  qdcount   = 1
  ancount   = 1
  nscount   = 0
  arcount   = 0
  \qd        \
   |###[ DNS Question Record ]###
   |  qname     = 'test.com.'
   |  qtype     = AAAA
   |  qclass    = IN
  \an        \
   |###[ DNS Resource Record ]###
   |  rrname    = 'test.com.'
   |  type      = AAAA
   |  rclass    = IN
   |  ttl       = 3600
   |  rdlen     = None
   |  rdata     = 6fbb:7aea:70bb:7aea:71bb:7aea:72bb:7aea
  ns        = None
  ar        = None

None

Response packet Length: 54 Bytes

Total Time Taken: 299.09 ms

```



##### DoH query on IPv4 Server with a CA singned certificate and EDNS0.

```
$ doh-http2 test.com AAAA --dns 10.197.36.36 --cert /mnt/home/csutradhar/ca.pem --edns

###[ DNS ]###
  id        = 256
  qr        = 1
  opcode    = QUERY
  aa        = 0
  tc        = 0
  rd        = 1
  ra        = 1
  z         = 0
  ad        = 0
  cd        = 0
  rcode     = ok
  qdcount   = 1
  ancount   = 1
  nscount   = 0
  arcount   = 1
  \qd        \
   |###[ DNS Question Record ]###
   |  qname     = 'test.com.'
   |  qtype     = AAAA
   |  qclass    = IN
  \an        \
   |###[ DNS Resource Record ]###
   |  rrname    = 'test.com.'
   |  type      = AAAA
   |  rclass    = IN
   |  ttl       = 3540
   |  rdlen     = None
   |  rdata     = 6fbb:7aea:70bb:7aea:71bb:7aea:72bb:7aea
  ns        = None
  \ar        \
   |###[ DNS OPT Resource Record ]###
   |  rrname    = '.'
   |  type      = OPT
   |  rclass    = 1220
   |  extrcode  = 0
   |  version   = 0
   |  z         = 0
   |  rdlen     = None
   |  \rdata     \

None

Response packet Length: 65 Bytes

Total Time Taken: 17.91 ms

```

