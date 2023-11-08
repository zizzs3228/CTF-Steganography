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
+ LSB can be in any file, so use `GBS` to make image from file and then use `stegsolve.jar`
+ https://www.asciitohex.com/ - tool to decode different formats
+ https://gchq.github.io/CyberChef/ - also same tool
## Images/GIFs
+ Check the image, flag can be hidden right in front of you
+ Check google image search and try to check it with Stegsolve.jar
+ `zsteg -a filename.png` - to extract all possible hidden strings from png/GIF file
+ `- java -jar stegsolve.jar` - the most powerfull instrument for images/GIFs
+ `convert -h` - tool to cut and work with GIFs/images
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
## Disk Image - .img
+ Autopsy
