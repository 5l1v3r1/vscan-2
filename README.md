# vscan

vulnerability scanner tool is using nmap and nse scripts to find vulnerabilities

This tool puts an additional value into vulnerability scanning with nmap. 
It uses NSE scripts which can add flexibility in terms of vulnerability detection and exploitation.
Below there are some of the features that NSE scripts provide  

- Network discovery
- More sophisticated version detection
- Vulnerability detection
- Backdoor detection
- Vulnerability exploitation

This tool uses the path ```/usr/share/nmap/scripts/``` where the nse scripts are located in kali linux 

The tool performs the following 

- check the communication to the target hosts by cheking icmp requests
- takes as input a protocol name such as http and executes all nse scripts related to that protocol
- if any vulnerability triggers it saves the output into a log file
- it may perform all of the above actions for a range of IP addresses

If the tool finds a vulnerabilty in a certain protocol it keeps the output into a log file which is saved in the following location ```/home/vulnerabilities_enumeration/http_vulnerabilities/http_vulnerabilities/http_vulnerabilities.txt``` 
In this example the folders have been created using the protocol prefix which in the current occasion is the http protocol. 

##Usage: 

```[Usage:] ./vscan.sh <ipadress_range> <protocol> <port>```

##examples:

1)
```./vscan.sh 192.168.162.90 http 80``` 

2)
```./vscan.sh 192.168.162.10-90 http 80```

##References :
- https://nmap.org/book/nse.html
- https://nmap.org/nsedoc/

##Screenshots:

###Example: SMB scanning 
![vuln_scan](https://cloud.githubusercontent.com/assets/12726776/12111385/820089b6-b39d-11e5-9664-ab8f4c0ae417.PNG)


###Example: Slowloris vulnerability detection 


![slowloris](https://cloud.githubusercontent.com/assets/12726776/12113240/28be284c-b3aa-11e5-99f6-faa19a9ba00f.PNG)

##Example: multiple IP scanning SSH weak keys

![range](https://cloud.githubusercontent.com/assets/12726776/12118359/b1619c32-b3ce-11e5-862c-cc5a85b667d1.PNG)
