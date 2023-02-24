<center><h2>Nintendo PRUDP</h2></center>
<p align="center"><a href="https://nintendo.com" target="_blank"><img src="https://logodownload.org/wp-content/uploads/2017/04/nintendo-logo-1-1.png" width="400" alt="Nintendo Logo"></a></p>

## About PRUDP Protocol

PRUDP is a transport layer protocol on top of UDP whose aim is to reliably and securely send UDP packets. There are two versions of this protocol (V0 and V1), but these are pretty similar. The primary difference lies in the encoding of the packets. All values are encoded in little endian byte order.

On the Nintendo Switch, NEX uses a WebSocket connection instead of UDP and the 'Lite'-encoding is used.

## PRUDP Session
