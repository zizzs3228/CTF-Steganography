# How to solve stega/forensics CTFs
## General
+ `file filename` - to check real extension 
+ `exiftool filename` - to check metadata
+ binwalk
  + `binwalk filename` - to check files inside file
  + `binwalk -e filename` - to extract files from file
  + `binwalk --dd='.*' filename` - to extract files even if they are not in this file
+ `strings filename | grep ` - to get all strings in file and grep from them
+ `steghide --extract -sf filename` - steg extraction (passphrase required)
+ `hexeditor filename.png` - to open hex of file and check if header is right and hight+width is also right
+ `stegcracker filename wordlist` - to bruteforce steghide tool
+ `stegseek` - same as stegcracker
+ `snowflake` - tool for decoding SPACES and TABS
+ `binascii python` - python library to work with hex-files
+ LSB can be in any file, so use `GBS` to make image from file and then use `stegsolve.jar`
+ https://www.asciitohex.com/ - tool to decode different formats
+ https://gchq.github.io/CyberChef/ - also same tool
+ https://hexed.it/ - tool to edit hex files EASIER!!!!!
## Images/GIFs
+ Check the image, flag can be hidden right in front of you
+ Check google image search and try to check it with Stegsolve.jar
+ `zsteg -a filename.png` - to extract all possible hidden strings from png/GIF file
+ `- java -jar stegsolve.jar` - the most powerfull instrument for images/GIFs
+ `jsteg` - same as stegsolve, but better for bigger pictures
+ `convert -h` - tool to cut and work with GIFs/images
+ https://onlinepngtools.com/ - many tools, which can be helpfull for stega
## Audio
+ Sound Visualizer (Windows)
+ Audacity (Windows)
+ QSSTV (Windows)
## PDF
+ `pdfcracker` - to crack PDFs
+ `pdf-parser -v filename.pdf` - to parse everything from pdf file
+ `pdfimages -png filename.pdf .` - to extract all images from pdf file
+ `pdftotext filename.pdf` - to extract text from pdf file -> `strings`
+ `pdfdetach -list filename.pdf` - to show embeded files
## PCAP
+ `wireshark filename.pcap` - almost the only way to solve CTF
  + File -> Export Objects 
+ `tcpflow -r filename.pcap` - to extract all pocket streams
+ `python scapy` - Python library to work with pcap/pcapng files
  + ICMP tasks
    + Decode Raw part
    + Decode id part
    + Decode lenght part
## Disk Images/Virtual machines/memory dumps
+ Autopsy - linux
+ tsk_recover
+ volatility py - python
+ Hetman Partition Recovery - disk recovery Windows
+ R-Studio - disk recovery Windows
+ EaseUs Data Recovery Wizard - disk recovery Windows
+ Disk Drill - disk recovery Windows
## Other resources about forensics and stega
+ https://github.com/shadawck/awesome-anti-forensic/blob/master/README.md
+ https://habr.com/ru/companies/hetmansoftware/articles/553866/
+ https://github.com/DominicBreuker/stego-toolkit/tree/master
