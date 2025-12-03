
INTRODUCTION: 

This report contains results of code all relating to an instance of monitoring traffic. 
The pipeline collects a diag port .pcap, network port .pcap, and a power.csv

Note on usage: Related code not yet provided for usage. Preliminary results are shown only.

USAGE:

Must be run when logged in as root. To begin, in a root shell, run:

./diag.sh [FILE_NAME]

This will then open 3 other windows. These windows will include:
	- An instance of ./download.sh, generating a .pcap relating to the network interface rmnet_mhi0.1 (used by the 5G HAT)
		-- A window showing the status of wget on a test file of size x
	- An instance of python3 ucrINA.py, a modified version of the INA219.py program provided by waveshare
		-- The program dynamically adds the current power consumption at a time. Must be closed with ^C, but will be saved.

The following ouput will be:

Diag/   --
	[FILE_NAME]/ 
	     |
	     diag[FILE_NAME].pcap : contains the diag port log
	     diagTime[FILE_NAME].txt: contains the start time to be used for mapping  
Download/-- 
	[FILE_NAME]/
	    |
	    download[FILE_NAME].pcap : Contains tshark captured traffic from the network interface
	    downloadTime[FILE_NAME].pcap : Contaitns start time 
Power/--
	[FILE_NAME]/
	    |
		[FILE_NAME].csv : contains rows with Time, Voltage, Amps, and Watts (Power)

		^^ all can be resolved by either reboot, or reseating the ribbon cable.
		The alias is simply 'check'
