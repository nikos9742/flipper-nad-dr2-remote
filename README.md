# flipper-nad-dr2-remote
Remote replacement and emulation for NAD DR2 remote and NAD 3020 and 7050 Amplifier 

NAD audio equipement such as the NAD 3020 and 7050 use the NEC Extended Protocol
More informaion here : https://www.sbprojects.net/knowledge/ir/nec.php

By fuzzing the device with the 256 commands possible allow me to find direct command for all the specific input of the D3020.


Extended NEC protocol

The NEC protocol is so widely used that soon all possible addresses were used up. By sacrificing the address redundancy the address range was extended from 256 possible values to approximately 65000 different values. This way the address range was extended from 8 bits to 16 bits without changing any other property of the protocol.
By extending the address range this way the total message time is no longer constant. It now depends on the total number of 1's and 0's in the message. If you want to keep the total message time constant you'll have to make sure the number 1's in the address field is 8 (it automatically means that the number of 0's is also 8). This will reduce the maximum number of different addresses to just about 13000.

The command redundancy is still preserved. Therefore each address can still handle 256 different commands.

Extended NEC protocol

Keep in mind that 256 address values of the extended protocol are invalid because they are in fact normal NEC protocol addresses. Whenever the low byte is the exact inverse of the high byte it is not a valid extended address. 