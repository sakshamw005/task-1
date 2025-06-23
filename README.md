**Nmap** : Originally referred as **Network Mapper** , helps us identify open-ports,running services etc. for the very basic purpose of **reconnaisance** . 

So , here's the steps I took to create the result .

Step 1 : Check for the availability of nmap on your OS , search
         nmap --version.If it shows it is available

Step 2 : I identified the IP Address of my system . 

Step 3 : I performed a basic scan with the command : 
         **nmap -sS -p- -A -O -oX nmap_scan.xml 192.168.18.240** 
         Let's understand the meaning :
         -sS : The -sS option performs a TCP SYN scan, which is one of the most popular and stealthy scanning techniques in Nmap. 
         -p- : It scans all the 65535 ports , if not placed nmap by default scan only top 1000 ports
         -A : It aggresively scans , it uses aggressive scripts to scan doesn't matter if any footprint is left
         -O : It is used for OS identification
         -oX : The -oX option tells Nmap to save the scan results in XML format.

Step 4 : I converted the scan result originally in .xml format to .html format using the tool xsltproc with the following command
         xsltproc scan_result.xml -o scan_result.html
