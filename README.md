# imonitorg
Generic version: raspberry pi3B/3B+ images available at sourceforge link

For a general overview:  https://imonitorg.com/overview.pdf

Information about how to install/start this image:

A standard linux "gunzip/bunzip2/unxz" should unzip the .gz/.bz2/.xz file to a 32GB image.   It will come up running if you use ethernet connect to your router.  If you are wifi only, then connect up KVM, login default user and config wifi creds [can remove KVM after thi
s].  "Pihole" is included via a link on index page.  Setup gmail config on web page to enable daily email.  These images are standard raspberry pi3B/pi3B+ with default pi password.  All scripts run as pi or root.  Do n
ot disturb the scripts or the cron files. Reburn the image to restore.  You are free to use the pi normally in other ways.  Run "raspi-config" to set TZ other than US EST.

There is absolutely no connection to remote servers in this generic imonitorg software [other than those in the original pi3B[+] distributions].  Some of the scripts/names/crons have remnant names suggesting this due t
o its development across 26 users in different ISPs across the US. These are original jessie[stretch] distributions, updated at one or more times, and uses a noobs disk structure with a recovery partition.  Originally 
obtained from Vilros. There is also absolutely no use of "arp spoofing" to intercept any traffic from any other devices on your network.  
 
Run "/root/clean_piG_files_generic" as root to clean all history at any time in /root via "./clean_piG_files_generic"
/root/Top100WebSites.txt is primarily for US; you can modify this for other countries if you want -length must remain same!  
"Pihole" is available via a link on the main rpi web page.  Change DNS server on your LAN or individual gadgets to point to the rpi and it will record all your DNS queries.
1-20-2021: Run "raspi-config" to set TimeZone - it is set to US EST
6-26-2022: Setup gmail parameters to allow relay of daily email on rpi web page
6-11-2021:latest [32GB]pi0w image (buster): This contains an APN so you can find it on wifi[SSID "Browseto...";KEY is "password"], enter home SSID/KEY/gmail_info[opt]; vncserver enabled; email sent on bootup!;  NO NETW
ORK PERF monitoring sware --caution: it will boot into present state, so you must boot from/into APN/configure state [not from the "un-configured" -since there is no configuration!]
3-5-2022: MAKE SURE YOU WAIT a DAY to FLUSH OUT STATs, old config, a week to recycle host discovery.
8-14-2022: Image copy error may cause tcppings to not appear for 1st day of use.  /root/RTTimetcpping.txt may have a binary character until cleared overnite. Simple ping results start ON the hour.
11-11-2022: New 3B/3B+ jessie/stretch images. NOTE near realtime plot [5 min delay] of perf, linked on pi home page
 