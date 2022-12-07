# NetPractice

This project is about networking and subnetting.
What is requested by the exercises is connecting a series of TCP/IP addresses between them so that they can communicate with each other.
To do so, it is important to understand the concepts of subnetowrk and submask.

We can divide the last part of a TCP/IP address in subnetworks according to the binary conversion of the mask it has, and the CIDR notation.
For example, a mask 255.255.255.192 (\26 in the CIDR notation, because the first three bytes of the mask exclusively contain "1", e.g. "11111111.11111111.11111111", what makes twenty-four "1", and the fourth byte contains two "1" and six "0").

To find if an IP address is in the same subnetwork of another one, we have to compare the binary conversion of the mask with the binary conversion of the address with the bitwise operator "&", what will result in a series of "1" indicating what cyphers indicate the network followed by a series of "0" to define the cyphers of the host, giving us the modifiable range. The range will span from a series of "0", representing the network address, to a series of "1" preceded by a "0", representing the broadcast address.

Our available range will have to exclude those two addresses.

To calculate how many subnetworks a mask allows we have to subtract the decimal conversion of the last "1" of the mask to the previous "1", and add one to consider the network part.

A modulo "%" gives us the position our IP address occupies in a subnetwork. For example, with a mask of 255.255.255.192 and an IP address of 132.156.76.2, the range available for each subnetwork may be calculated with the following formula:

192 - 128 = 64

and 2 % 64 gives us 2, which represents the distance from zero of our IP address in the subnetwork range.

It's important to notice that:

* the internet needs the IP address range of the computer to which it has to send a packet.

* <https://github.com/lpaube/NetPractice>;
* <https://www.it-connect.fr/adresses-ipv4-et-le-calcul-des-masques-de-sous-reseaux>;
* <https://www.aelius.com/njh/subnet_sheet.html>.