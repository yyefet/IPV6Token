# [IPV6 Token](https://ipv6token.com)


```bash
    ________ _    _______    ______      __            
   /  _/ __ \ |  / / ___/   /_  __/___  / /_____  ____ 
   / // /_/ / | / / __ \     / / / __ \/ //_/ _ \/ __ \
 _/ // ____/| |/ / /_/ /    / / / /_/ / ,< /  __/ / / /
/___/_/     |___/\____/    /_/  \____/_/|_|\___/_/ /_/ 
                                                                               
```
# What is IPV6 Token Project?
IPV6 Token Project aims to bring blockchain and crypto to a lower level of the network stack.
Currently, blockchain interaction lives on layer 7, which is typically blocked by corporate networks,
and also is easier to attack with mitm (man in the middle).  Using IPV6 (Internet Protocol) brings
numerous advances to communication, most importantly, encrypted custom headers.
Two parties are also able to use stegangraphy (the science of hiding messages) in custom destination 
headers to secure interactions.

Instead of going from Browser -> DAPP/DEFI/WALLET (which is unsecure)...
Or project aims to create standards of communication from IPV6 Protocol -> DAPP/DEFI/WALLET using secure headers.

# How Standard IPV6 Crypto Headers work

IPV6 uses a concept of "Extension" headers..  These are used to get packet from point A to point B.
As well as flags/options that can be used by the destination.

1) Hop-by-Hop Option Header: which is used by routers and removed once the router processed the packet
2) Destination headers: which is only processed by the destination.

The IPV6 Blockchain/Crypto specific headers our project developed are embedded in the Destination Extension header.

```bash
Example IPV6 Headers:

###[ IPv6 ]### 
  version   = 6
  tc        = 0
  fl        = 0
  plen      = 8
  nh        = Hop-by-Hop Option Header
  hlim      = 64
  src       = ::1
  dst       = ::1
###[ IPv6 Extension Header - Hop-by-Hop Options Header ]### 
     nh        = No Next Header
     len       = 0
     autopad   = On
     \options   \
      |###[ PadN ]### 
      |  otype     = PadN [00: skip, 0: Don't change en-route]
      |  optlen    = 4
      |  optdata   = '\x00\x00\x00\x00'
...<redacted for brevity>...
```

In fact, symmetric encryption can be implemented by two parties, for example, if you run your own GETH node
where both parties one party explicity knows how to encrypt and the second party knows how to ecrypt.
Furthermore, this type of transaction can also be split into multiple IPV6 packets, and sent over a variable 
timeframe (to reduce risk).


