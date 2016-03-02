# openvpn-installer
Installation script for running openvpn server and generating certificate for clients

## Firewall configurations
> Faced some issue in pinging client <-> client and server -> (some) clients. Here are some iptable configurations that helped

```shell
iptables -t filter -F
iptables -t nat -F
iptables -A FORWARD -m state --state RELATED,ESTABLISHED -j ACCEPT
iptables -A FORWARD -s "10.8.0.0/24" -j ACCEPT
iptables -A FORWARD -j REJECT
iptables -t nat -A POSTROUTING -s "10.8.0.0/24" -j MASQUERADE
```


> Note:
Adapted from github.com/Nyr
The MIT License (MIT)
Copyright (c) 2013 Nyr
Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:
The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
\THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


Copyright (c) 2016 Mohit Sharma
