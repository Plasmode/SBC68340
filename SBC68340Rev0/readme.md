# SBC68340 Rev0
The prototype design was converted to pc board using WinDraft to capture schematic and WinBoard to lay out pc board.
![rev0pcb](SBC68340_rev0_topview.jpg)

### Features
- MC68340 Integrated Processor
  - 2 serial ports MC68681 compatible
  - 2 counter/timers
  - system integration module
  - 145-pin PGA
- 24MHz system clock
- 256KB 16-bit wide RAM
- 64KB 8-bit boot flash
- Support CP/M68K
- RC2014-like I/O expansion bus
- 100mm X 100mm PC board with prototype area

### Design Files
- [Schematic](sbc68340_rev0_scm.pdf)
- [Gerber photoplots](sbc68340_rev0_gerber.zip)
- Bills of materials

### [Software](software) 
- 340Bug monitor v0.3, still under construction to remove redundant functions
- Tutor v1.3 for Easy68K ← the original Tutor modified to use Easy68K's Trap15 services. type “go 44000” in 340Bug to invoke Tutor
- CP/M demo. This flash programming file contains 4 components; 340Bug monitor, CPM15000, BIOS340, and a small flash disk. Start CP/M68K with 'bo' command in 340bug monitor. There are two drives: drive A is flash drive with 3 files, init, pip, and stat; drive B is 64K RAM drive.

- Source files for above CP/M demo

- Gkermit for drive B. Load this s-record before issuing 'bo' command. Gkermit.68K will show up in drive B. ←note, gkermit won't work at 115200 baud. The serial clock should be 614400hz to enable 38.4K baud serial communication to run gkermit file transfer.

- [340Bug monitor v0.3](software/SBC68340R0_software_340bug_v03.zip), still under construction to remove redundant functions

- [Tutor v1.3](software/SBC68340R0_software_tutor_v1_3.zip) for SBC68340 ← the original Tutor modified to use Easy68K's Trap15 services. type “go 44000” in 340Bug to invoke Tutor

- CP/M demo. This [flash programming file](software/SBC68340_software_340bug_cpm15000_bios340_flash_drive.zip) contains 4 components; 340Bug monitor, CPM15000, BIOS340, and a small flash disk. Start CP/M68K with 'bo' command in 340bug monitor. There are two drives: drive A is flash drive with 3 files, init, pip, and stat; drive B is 64K RAM drive.

- [Source files](software/SBC68340R0_software_source_340bug_bios340_drivea_32k_cpm1500.zip) for above CP/M demo

- [Gkermit for drive B](software/SBC68340_software_gkermit_for_driveb.zip). Load this s-record before issuing 'bo' command. Gkermit.68K will show up in drive B. ←note, gkermit won't work at 115200 baud. The serial clock should be 614400hz to enable 38.4K baud serial communication to run gkermit file transfer.


## SBC68340 Engineering Changes
Enable RC2014 expansion bus
The P6 connector was originally designed as test connector for logic analyzer. Its pin assignments are similar to 40-pin RC2014 expansion bus, but there are significant differences that prevent interface with standard RC2014 expansion boards. Here are lists of engineering changes to enable RC2014 boards.

- Data bus changed to D[15..8]
- nM1 pulled up to 4.7K
- nMREQ cut from nAS, then pulled up to 4.7K
- nRD cut from nDSACK0, then connected to nRD


