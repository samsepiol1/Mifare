<center><h2>Mifare Classic Cards Vulnerabilities</h2></center>
<p align="center"><a href="" target="_blank"><img src="https://www.mifare.net/wp-content/themes/p371-mifare-theme/img/mifare_logo_rgb.png" width="400" alt="Mifare Logo"></a></p>

## About Mifare Classic Card
MIFARE Classic is a contactless smart card technology used for a wide range of applications, such as public transport, access control, and payment systems. It is developed by NXP Semiconductors and is one of the most widely used smart card technologies in the world.

MIFARE Classic cards are based on RFID technology and operate at a frequency of 13.56 MHz. The cards are typically embedded with an antenna and a microchip that stores data, and communicate with a reader using radio waves. The data on the card is encrypted using the Crypto-1 algorithm, which provides basic security features such as authentication and encryption.

MIFARE Classic cards come in various sizes and memory capacities, ranging from 1KB to 4KB. The card's memory is organized into sectors, each of which can be locked and accessed using keys. Each card has two sets of keys, referred to as Key A and Key B, which are used for authentication and data encryption.

One of the main advantages of MIFARE Classic cards is their compatibility with a wide range of readers and applications. They are widely used in public transportation systems, such as subways and buses, as well as in access control systems for buildings, parking garages, and other secure areas. They are also used in payment systems, such as electronic toll collection and prepaid debit cards.

However, MIFARE Classic cards have been subject to several security vulnerabilities and attacks, which have raised concerns about their security. For example, the Crypto-1 encryption algorithm used by MIFARE Classic cards was found to be vulnerable to a number of attacks, including key recovery and eavesdropping. As a result, there have been calls to phase out MIFARE Classic cards in favor of more secure alternatives.

## Mifare Basic Structure

```c
typedef struct{
    unsigned char uid[4]; // Indentify Card - UUID
    unsigned char manufacturer[8];  // Card Manufacturer
    unsigned char data[1024]; // Data Card
    unsigned char sector_trailer[16]; // Sector Trailer
    unsigned char sector_trailer_access_bits[3]; // Access Bits
    unsigned char sector_trailer_keyA[6]; // Sector A Key
    unsigned char sector_trailer_keyB[6]; //Sector B Key
    unsigned char sector_trailer_nonce[4]; // Random number to access key in card


} mifare_classic_t;

```
