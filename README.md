# [IPV6 Token](https://ipv6token.com)


```bash
    ________ _    _______    ______      __            
   /  _/ __ \ |  / / ___/   /_  __/___  / /_____  ____ 
   / // /_/ / | / / __ \     / / / __ \/ //_/ _ \/ __ \
 _/ // ____/| |/ / /_/ /    / / / /_/ / ,< /  __/ / / /
/___/_/     |___/\____/    /_/  \____/_/|_|\___/_/ /_/ 
                                                                               
```
# What is IPV6 Token Project?
IPV6 Token Project aims to bring blockchain and crypto to a lower level of the network stack as well
as being the first Enterprise-ready blockchain managed by IT and HR departments.

Corporations tend to manage their own infrastructure for security purposes and integrating their 
human resource-based transactions into existing blockchains is currently frowned upon.  IPV6 Token aims 
to issue corporate sidechains that are fully managed by IT and HR departments to alleviate any security
concerns.

Existing blockchain interaction lives on layer 7, which is typically blocked by corporate networks due to
the fact that they are prone to mitm (man in the middle) attacks.  Using IPV6 (Internet Protocol) brings
numerous advances to communication, most importantly, symmetric and asymmetric excryption via custom headers.
Two parties are able to use stegangraphy (the science of hiding messages) in these custom destination 
headers to secure transactions with the blockchain.

Instead of going from Browser -> DAPP/DEFI/WALLET (which is insecure), IPV6 token project aims to create 
standards of communication over the network from IPV6 Protocol -> DAPP/DEFI/WALLET using secure headers.

This means exisitng protocols such as LDAP can be integrated into the blockchain, mapping employees,
contractors, and vendors into their own managed sidechain.

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


# Blockchain Crypto Headers

The standard must be applicable in many programming languages, easy to read and write, and
be applicable to multiple blockchains (ie: Bitcoin, Ethereum, Polygon, Cardano, Binance, Doge, Solana etc).

The formatting of a custom IPV6 Crypto header is a stadard that anyone can easily implement and author.

```bash
For example, using Scapy (python library to forlumate IPV6 packet):

packet = IPv6(dst='2600::89f::db01::72b3:8cb2')
query = 'quote("ETH/USD", "ether")'
send(packet/IPv6ExtHdrDestOpt(options=PadN(optdata=query)))
```
In the example above, one would initiate an IPV6 connection as normal..
Then formulate a query and send using the padded `IPv6ExtHdrDestOpt` options method.

The receiver (ie: processing party) would process the request and respond with the data in the following format:

```bash
quote:3,291.47
```

# List of Standard Crypto methods for use in headers

## quote()

## address()

## approve()

## tx()

## gas()

## convert()

## token()

## supply()

## marketcap()

## holders()

## transfers()

## encrypt()

## decrypt()
