# netpractice

A 42 school system administration exercise

## Practical knowledge

### Cheat sheet

| Subnet Mask   | CIDR Notation | Binary Value          |
|---------------|---------------|-----------------------|
| 0.0.0.0       | /0            | 00000000.00000000.00000000.00000000 |
| 128.0.0.0     | /1            | 10000000.00000000.00000000.00000000 |
| 192.0.0.0     | /2            | 11000000.00000000.00000000.00000000 |
| 224.0.0.0     | /3            | 11100000.00000000.00000000.00000000 |
| 240.0.0.0     | /4            | 11110000.00000000.00000000.00000000 |
| 248.0.0.0     | /5            | 11111000.00000000.00000000.00000000 |
| 252.0.0.0     | /6            | 11111100.00000000.00000000.00000000 |
| 254.0.0.0     | /7            | 11111110.00000000.00000000.00000000 |
| 255.0.0.0     | /8            | 11111111.00000000.00000000.00000000 |
| 255.128.0.0   | /9            | 11111111.10000000.00000000.00000000 |
| 255.192.0.0   | /10           | 11111111.11000000.00000000.00000000 |
| 255.224.0.0   | /11           | 11111111.11100000.00000000.00000000 |
| 255.240.0.0   | /12           | 11111111.11110000.00000000.00000000 |
| 255.248.0.0   | /13           | 11111111.11111000.00000000.00000000 |
| 255.252.0.0   | /14           | 11111111.11111100.00000000.00000000 |
| 255.254.0.0   | /15           | 11111111.11111110.00000000.00000000 |
| 255.255.0.0   | /16           | 11111111.11111111.00000000.00000000 |
| 255.255.128.0 | /17           | 11111111.11111111.10000000.00000000 |
| 255.255.192.0 | /18           | 11111111.11111111.11000000.00000000 |
| 255.255.224.0 | /19           | 11111111.11111111.11100000.00000000 |
| 255.255.240.0 | /20           | 11111111.11111111.11110000.00000000 |
| 255.255.248.0 | /21           | 11111111.11111111.11111000.00000000 |
| 255.255.252.0 | /22           | 11111111.11111111.11111100.00000000 |
| 255.255.254.0 | /23           | 11111111.11111111.11111110.00000000 |
| 255.255.255.0 | /24           | 11111111.11111111.11111111.00000000 |
| 255.255.255.128 | /25         | 11111111.11111111.11111111.10000000 |
| 255.255.255.192 | /26         | 11111111.11111111.11111111.11000000 |
| 255.255.255.224 | /27         | 11111111.11111111.11111111.11100000 |
| 255.255.255.240 | /28         | 11111111.11111111.11111111.11110000 |
| 255.255.255.248 | /29         | 11111111.11111111.11111111.11111000 |
| 255.255.255.252 | /30         | 11111111.11111111.11111111.11111100 |
| 255.255.255.254 | /31         | 11111111.11111111.11111111.11111110 |
| 255.255.255.255 | /32         | 11111111.11111111.11111111.11111111 |

| Bit Position | 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 |
|--------------|---|---|---|---|---|---|---|---|
| Decimal Value| 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| Binary Value | 10000000 | 01000000 | 00100000 | 00010000 | 00001000 | 00000100 | 00000010 | 00000001 |

### IP Address Range

To identify the IP address range within a network:

1. **Network Address & Subnet Mask**: Identify these two elements. For instance, a network address could be 192.168.1.0 and a subnet mask 255.255.255.0.

2. **Binary Conversion**: Convert the network address and subnet mask to binary for easier calculations.

3. **Network & Host Portions**: Identify these portions in the IP address. They correspond to the 1s (network) and 0s (host) in the subnet mask.

4. **IP Address Range**: Determine the range using the host portion of the IP address. The first IP address is the network address (all host bits set to 0), and the last is the broadcast address (all host bits set to 1).

5. **Usable IP Address Range**: This is the set of addresses between the network and broadcast addresses. These can be assigned to devices on the network.

### Finding Subnet mask

Ip Address 1 = 192.168.25.222 IP Address 2 = 192.168.25.192  

- find common prefix: 192.168.25
- write out in binary
- Address 1: 11000000.10101000.00011001.11011110  
- Address 2: 11000000.10101000.00011001.11000000
- set same bits to 1 and after that all to 0
- Convert binary mask back to decimal: 11111111.11111111.11111111.11000000 translates to 255.255.255.192.

### Finding Network Address

Example:  
Ip Address 1: 192.168.19.222  
Subnet Mask: 255.255.255.224

- write out in binary:  
192.168.19.222 = 11000000.10100000.00010011.11011110  
255.255.255.224 = 11111111.11111111.11111111.11100000  
- Result of bitwise AND operation: 11000000.10100000.00010011.11000000
- Network Address: 192.168.19.192
- perform bitwise and operation
- Result = Network Address



### Finding Subnet mask

Given two IP addresses, you can find a common subnet mask by following these steps:

1. Identify the common prefix. For example, given IP Address 1 = 192.168.25.222 and IP Address 2 = 192.168.25.192, the common prefix is 192.168.25.

2. The subnet mask is determined by the number of bits in the common prefix. For a common prefix of 192.168.25, the subnet mask would be 255.255.255.0 in decimal notation.

### Finding Network Address

Given an IP address and a subnet mask, you can find the network address by following these steps:

1. Write out the IP address and the subnet mask in binary.

2. Perform a bitwise AND operation between the IP address and the subnet mask. This means comparing each bit of the IP address with the corresponding bit of the subnet mask. If both bits are 1, the result is 1. Otherwise, the result is 0.

3. The result of the bitwise AND operation is the network address in binary.

4. Convert the binary network address back to decimal.

For example, given the IP Address 1: 192.168.19.222 and Subnet Mask: 255.255.255.224, the network address can be found by performing the bitwise AND operation and converting the result back to decimal.

