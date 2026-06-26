# PacSat SPI to I2C Converter Sysconfig

This repository holds the sysconfig configuration of the PacSat SPI to
I2C converter processor, also known as the Antenna Control Processor.

This does not hold the actual software.  Instead, it holds the
sysconfig that is used to program the NONMAIN (NONCONFIG) FLASH memory
in the processor.  The software to run on this is in the PacSatPII2C
repository.

You *MUST* program this first before programming the actual software.

## Programming The Config

You program this normally with TI Code Composer Studio, but you must
change a setting.  CCS will not program the NONMAIN memory by default,
you will get an error about not erasing the NONCONFIG memory.

In TI CCS you must to go to Project->Executable Actions->Manage then
go to the Debug section, choose "MSPM0 Flash Settings," then choose
"Erase MAIN and NONMAIN necessary sectors only".  Then reset the
M0L1228 with the reset button on the launchpad XDS110 and it program
it.

## The Sysconfig Itself

The sysconfig in this repository is an accurate representation of the
configuration of the processor.  This was used to figure out what pins
to use for what.  Refer to this for details.

