# What are checksums and what are they useful for?
 
## What are checksums
Checksum is a method to validate the fulfillment and correctness of a piece data that may be corrupted during data tranmission. It could be an integer/character or a bit, that is sent with the data piece and the receiver must know the package format in order to extract and validate the checksum.
 
## What are they use for
Checksums can be useful for validating packet data content or size. I think giving examples would be the best way to explain the usage of it.
 
A good example is Wiegand protocol which is a card reader protocol, which only uses 1 last bit of the data to check if the packet length is correct or not
 
Another example is OSDP (another reader protocol) has checksum as an 8-bit integer. On the controller side, we analyze the checksum using an algorithm provided by OSDP maker so that we could request a resend if the checksum is not what we expect.
 
UART and I2C also has checksum as well but it is usually digested by the MCU
