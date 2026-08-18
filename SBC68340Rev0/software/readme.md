# software for SBC68340 rev0

- 340Bug monitor v0.3, still under construction to remove redundant functions

- Tutor v1.3 for Easy68K ← the original Tutor modified to use Easy68K's Trap15 services. type “go 44000” in 340Bug to invoke Tutor

- CP/M demo. This flash programming file contains 4 components; 340Bug monitor, CPM15000, BIOS340, and a small flash disk. Start CP/M68K with 'bo' command in 340bug monitor. There are two drives: drive A is flash drive with 3 files, init, pip, and stat; drive B is 64K RAM drive.

- Source files for above CP/M demo

- Gkermit for drive B. Load this s-record before issuing 'bo' command. Gkermit.68K will show up in drive B. ←note, gkermit won't work at 115200 baud. The serial clock should be 614400hz to enable 38.4K baud serial communication to run gkermit file transfer.
