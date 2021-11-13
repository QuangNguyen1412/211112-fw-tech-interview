# How would you go about locating the cause of a stack overflow or watchdog timer reset?

## Detect a stack overflow
I think Stack overflow is a not a simple problem to detect at runtime. Though it could be actually prevented much easier at compiling time, any warning could be a wrong usage of an array being overflow or we can also use code analysis tool for that.
 
Otherwise at run time, we can also detect when it has already happened by analysing the coredump or directly use JTAG and GDB on the device when reproducing it to see the last line of code that was called.
 
## watchdog timer reset
Usually the system should log the watchdog reset causes at boot time if any. I think a good designed system should have stored the watchdog reset causes in persistent memory before WDT reset the board and clear all the causes/flags after everything were logged.
 
Or we can also debug it with JTAG and GDB while reproducing it so that we can observe the watch dog register of the device for better understanding of reset causes.
