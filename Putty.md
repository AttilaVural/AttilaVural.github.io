Putty cannot ssh to an IPv6 server. Tried using square brackets, using port 222 but nothing worked.

Filezilla is said to have inbuilt IPv6 support

```mermaid
  flowchart
    1[Create your public key and private key using putty]
    1--->2[Give public key to server host]
    2--->3[Convert your private key to putty file (.ppk) format using puttygen]
    3--->4[Load the .ppk file into putty (Category > Connection > SSH > Auth)
    4--->5[Connect using the IPv4 address on port 22]
```
