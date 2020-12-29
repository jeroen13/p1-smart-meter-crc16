# p1-smart-meter-crc16
A CRC / CRC16 / CRC16-ARC / CRC16-IBM calculation for P1 Smart meter telegrams in JavaScript

This CRC is a CRC16 value calculated over the preceding characters in the data message (from “/” to “!” using the polynomial: x^16+x^15+x^2+1). 
CRC16 uses no XOR in, no XOR out and is computed with least significant bit first. 
The value is represented as 4 hexadecimal charaters (MSB first).

Tested with ESMR5.0 on a CTA5ZIV-METER using Node-Red JS 


# Usage: 

Include the `p1-smart-meter-crc16.js` file.


```
/*  ==========================================================================

                                Example usage code

    Example telegram: https://raw.githubusercontent.com/nlrb/nl.dsmr.p1/master/node_modules/node-dsmr-parser/example-telegram.txt

==========================================================================  */


var CRC_is_Valid = calcCRC16(`/ISk5\\2MT382-1000

1-3:0.2.8(40)
0-0:1.0.0(101209113020W)
0-0:96.1.1(4B384547303034303436333935353037)
1-0:1.8.1(123456.789*kWh)
1-0:1.8.2(123456.789*kWh)
1-0:2.8.1(123456.789*kWh)
1-0:2.8.2(123456.789*kWh)
0-0:96.14.0(0002)
1-0:1.7.0(01.193*kW)
1-0:2.7.0(00.000*kW)
0-0:17.0.0(016.1*kW)
0-0:96.3.10(1)
0-0:96.7.21(00004)
0-0:96.7.9(00002)
1-0:99:97.0(2)(0:96.7.19)(101208152415W)(0000000240*s)(101208151004W)(00000000301*s)
1-0:32.32.0(00002)
1-0:52.32.0(00001)
1-0:72:32.0(00000)
1-0:32.36.0(00000)
1-0:52.36.0(00003)
1-0:72.36.0(00000)
0-0:96.13.1(3031203631203831)
0-0:96.13.0(303132333435363738393A3B3C3D3E3F303132333435363738393A3B3C3D3E3F303132333435363738393A3B3C3D3E3F303132333435363738393A3B3C3D3E3F303132333435363738393A3B3C3D3E3F)
0-1:24.1.0(03)
0-1:96.1.0(3232323241424344313233343536373839)
0-1:24.2.1(101209110000W)(12785.123*m3)
0-1:24.4.0(1)
!F46A`, true)

// Output the true / false
console.log("CRC valid? " + CRC_is_Valid);
```



```
Output> CRC valid? true
```

##### tags
CRC16/IBM, CRC16-IBM, CRC16-ARC, CRC16 0xA001, CRC16 Javascript, CRC Javascript, P1 Smart meter checksum, P1 Smart meter CRC, Slimme meter CRC, Smart meter CRC, P1 CRC
