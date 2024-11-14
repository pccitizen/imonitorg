GENERAL:
See https://imonitorg.com for general information There is a link to iotsnoop.html for more detailed iotsnoop info.
A standard linux "gunzip/bunzip2/unxz" will unzip the .gz/.bz2/.xz file to a 32GB image.  You will need zip tools on windows [7-zip].....  
Burn it with any image creation tool [incl "dd"]. Win32DiskImager or rpiimager or balenaEtcher will work.
using linux: "gunzip|bunzip2 -c 32GBjdloop-pi3B[plus]X-Y-2024.img.[gz|bz2] | dd of=/dev/sd[c,d,drive e.g.-your usb carrier with microSD] bs=8MB status=progress"  e.g. to write to microSD card 

There is absolutely no connection to cloud servers in this generic imonitorg software [the original pi3B[+] trial used my linode server for development], and I had connection.   
Some of the scripts/names/crons have remnant names suggesting this due to its development across 26 users in different ISPs across the US. 
These are original jessie/stretch/buster distributions, updated at one or more times.  pi3B/3B+/pi4B use a noobs disk structure with a recovery partition.  Originally obtained from Vilros. 
There is also absolutely no use of "arp spoofing" to intercept any traffic from any other devices on your network.  
You are free to use the pi normally in other ways, but it is not recommended.  Some updates are turned off.  You may compromise the scripts. 

PI3B/pi3B+:
There is no initialization needed.  It will come up running if you use ethernet connect to your router.
If you are wifi only, then connect up KVM, login default user and config wifi creds [can remove KVM after this].
"Pihole" is included via a link on index page.  Point your DNS server to the pi and monitor your DNS queries.
Setup gmail config on web page to enable daily email.  Uses your gmail account as a relay.
These images are standard raspberry pi3B/pi3B+ with default pi password. All scripts run as pi or root.  Do not disturb the scripts or the cron files. Reburn the image to restore.  
Run "/root/clean_piG_files_generic" as root to clean all history at any time in /root via "./clean_piG_files_generic"
Run "raspi-config" to set TZ other than US EST.
/root/Top100WebSites.txt is primarily for US; you can modify this for other countries if you want -length must remain same!
You can set gmail parameters for daily email manually as root [on web ifce as well, but this is simpler!]
echo <gmail email@address> DEFgmailUSER.txt
echo YES > DEFgmailENABLE.txt
echo <key> > DEFgmailAUTH.txt  [this must be special obtained from gmail.  See https://imonitorg.com/gmailRelayInstructions.html 
echo <email address to send to> > DEFgmailULTIMATE.txt

pi4B/iotsnoop:  USE https://imonitorg.com/iotsnoop.html to track any changes/edits to existing version
IN GENERAL: using pi4 iotsnoop in APN mode is less capable than routers for wifi strength and power.  Can use an extender for range extension and only IOT [no streaming devices]
UPDATE 11-1-2024: version 4.5 corrections, IOT device count plot, DHCP lease archive, lease changed to 1 hr.
UPDATE 10-15-2024: Version 4.4 several corrections, detect loss of tmt power, dhcp changed to 1 day lease, APN defaults to 2.4 GHz [changable to 5GHz]
UPDATE 9-9-2024: Version 4.3 several corrections, some bogus data displayed at start, will clear. APN is running 5GHz, NOT 2.4 as stated.  Options for 5/2.4 next version
UPDATE 8-15-2024: Version 4.2 plot corrections, access to full IOT pcap for last hour!
UPDATE 8-11-2024: plot counts for hostpairs, udp, dns not accurate.  4.2 to come soon
UPDATE 8-6-2024 Version 4.1 BOGUS DATA displayed- will clear eventually [having trouble with "clean" script]
UPDATE 8-4-2024: Version 4.0 -PULLED- https://iotsnoop.com/iotsnoop.html tracks changes, improvements
UPDATE 8-4-2024: Version 3.1 is assigning gateway as DNS for IOT. This is correct, but GUI is misleading -DNS assignment is for iotsnoop pi4!  corrected version 4
UPDATE 8-4-2024: Version 4 is coming.  Wait for it.  Selected IOT packet statistics/port/DNS available!! on-net<->on-net traffic, non-dhcp users stats
UPDATE 6-18-2024: version 3.1 is posted.  I have added a mapping feature which maps IOT contacts[DNS queries] from a selected IOT. Other bugfixes.  
UPDATE 5-12-2024: version 1.31 posted I used "bunzip2 -c SDcard64GB-jdloop-iotsnoop5-12-2024.img.bz2 | dd of=/dev/sde bs=8MB status=progress [caution: use Your /dev/"sd?"]  
NOTE: NO data will appear until an hour is crossed and analysis performed.  It will accumulate thereafter.  As root "./clean_iotsnoop_files" to reinitialize.  Remember this is long term msmts!  
This is a beta version, using 64GB SDcard. 32bit pi4. Write intensive! Feedback Needed!  USB boot enabled.  Do rpi-clone sd[a|b] to create ssd on usd.  
Must be connected to ethernet interface on router or downstream switch.  Wifi wlan0 is dedicated APN.  
To use for imonitorg only function [like 3B, 3B+ images above], as root "echo NO > DEFfindiothosts.txt" -NO IOT functions performed. Wifi APN is still functional. 
For iotsnoop, use is traffic sensitive.  4GB pi4 is recommended for 20+ IOT devices; 1GB pi4 can probably function for <10, esp with no streaming [TVs, etc]
Do NOT put streaming devices, like smart TVs, Dish/DirecTV [these use Internet for streaming] on wifi. Packet capture is capped at 2GB/hr. Reset/restart each hour.
Traffic capability is 2GB packet collection/hr, about 6 Mb/s average total [rcv+tmt]. 4K streaming will saturate at ~30 minutes. 
Wifi is constrained to 802.11g -50Mb/s [why would you want your IOT stealing your bandwidth!!]
iotsnoop pi4B image turns the wifi into an APN so you can accept IOT logins, and monitor them. Default SSID/KEY is iotsnoopg/iotsnoop
Web interface shows IOT plots/statistics.  See webpage below for more info.
NOTE: The display manager is disabled for performance reasons.  Enable it via "systemctl start lightdm" as user pi, followed by "startx" -beware perf problems. 
Iotsnoop performs LONGER term measurements. You must wait hours/days to see plots/stats/info. 
You can set iotsnoop APN passwd/key manually as root by editting the /etc/hostapd/hostapd.conf file [or use default]
You can set iotsnoop gmail parameters on iotsnoop web interface.  Receive daily email.
See https://iotsnoop.com for initial information, representative plots/stats/info

Oracle VirtualBox ova images:
Oracle VirtualBox "ova" image uses Ubuntu OS 22.04 generic base. Tested on rocky8 linux, centos8 and win10 Oracle VirtualBox hypervisor.
See instructions above for gmail relay config for daily email

pi0w images:
6-11-2021: pi0w does NOT have perf monitoring or iotsnoop scripts.  Simply boots wifi as an APN so you can find the pi0w without a KVM -solves the "no ethernet" problem
6-11-2021:[32GB]pi0w image (buster): This contains an APN so you can find it on wifi[SSID "Browseto...";KEY is "password"], enter home SSID/KEY/gmail_info[opt]; 
vncserver is enabled; email sent on bootup -if configured!;  NO NETWORK PERF monitoring sware --caution: it will boot into present state, 
so you must boot from/into APN/configure state [not from the "un-configured" -since there is no configuration!]

CHANGES/Special Notes:
1-20-2021: Optional: download "CustPingSites.newtxt" and place in /home/pi/tests/customerpings/ and you will start deep ICMP pings for the NEXT DAY ONLY[2AM-1AM]; 
you can add your own IPs to this list, or create the file yourself.  Make a cron to load it every day if you want it permanent

12-6-2021: You can order a 32GB microSD from me if you prefer.  See order form at https://imonitorg.com
2-24-2023: Script is included to detect off-network unsolicited TCP SYNs.  If you expect these, as root: "echo OFF > DEFunsolicitedSYN.txt" to disable.
5-9-2023: Hook for CGNAT detect.  as root: "echo [NO|YES] > DEFcgnat.txt"  Defaults to NO. Internet IP changes will not be alerted if YES.  
1-30-2024: New pi3B (jessie), pi3B+ (stretch) and "ova" images.  Some cleanup, better plots.  Uses bing "burst" or 4-6 pkts every min instead of just 1.  
5-19-2023: If your ISP is CGNAT, as root: "echo YES > DEFcgnat.txt" to avoid IP change alerts
MAKE SURE YOU WAIT a DAY to FLUSH OUT STATs, OLD PLOTS, old config, a week to recycle host discovery.  The emphasis is on "long-term" statistics, not minute to minute.
3-20-2024: pi4B/iotsnoop images --see https://iotsnoop.com


















