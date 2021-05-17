The big Question ("describe what happens when you type www.google.com in to your browser")
Yay interview questions!

Ok. DNS. You type this in. And besides the keystrokes connecting electrical circuitry that feeds in to a processor and hits some kind of timing cycle input, whatever..

Your browser first goes to the Resolver.
The resolver looks first for the information in two places, the host machine's cache and /hosts/file (in Linux)
Then if the information is not there it sends a recursive request to the local DNS server.
This is a request that demands that server find a definite answer, it is responsible for getting it now and first checks it's own cache.
The local DNS server is at the level of the ISP provider or thereabouts.
It then makes an iterative request to a series of servers, which means that in any of them a definite answer is not required.
First it queries the Root Server, which is responsible for knowing top level domains. If it doesn't know, it sends back a reference to a .com server ("www.google.com")
The local DNS server may cache this information in it's local cache from every iterative request.
Then it requests the info from the referenced Domain Server. If it doesn't have the information it can givfe a reference to where to find the .google. information.
Following this process the Local DNS server then goes to a DNS server that has the www.google.com information, which sends back the IP address.

WEB APP process knowledge.
Now that the browser knows the server's IP address, it can ask it for the web page using an HTTP GET request. This is a HTTP verb, and the server
responds with web content. This can include JavaScript, images and CSS files. Smart users will disable macros and admins will set Group Policies on a
secure baseline image they flash to every new host, disabling employee's ability to perhaps accidentally load these as they may contain malware.
This is an excellent place to infiltrate the system with a virus or worm, which will load perhaps even without the employee knowing.

SEC+ questions woven in.
As the attacker or security tester, if the server will take a web page request then either port 443 is open (https) or port 80 where insecure HTTP is run. 
One can use burp suite to enumerate by capturing the traffic sent back and forth between server and host using a proxy in a Man In The Middle Attack.
Injection vulnerability such as SQL injection is a leading weakness in modern web apps, and a pen tester will recommend <technical name of hardening> it.
Moving deeper in to server analysis, a previous attacker may have placed a RAT or remote access trojan, to ensure persistent access that they can return to later. 
This is similar to the backdoors non-security trained programmers will often leave to bypass the hassle of authentication during development, weaponized and made invisible.
Another move a malicious actor may make is to place a Dropper in the system. This is a tiny piece of shell code that will download the rest of the malware, using a Downloader 
which will connect to the internet and download more tools. Another form of injection attack for instance, would be DLL injection in which the dropper would force DLL to load with malicious code in parallel. Alternately, the malware could use Masquerading, replacing a legitimate .exe file with a malicious .exe file..

Mobile App Security
If a company provides phones to employees they have the right to control access, and even in a BYOD situation they can mandate MDM software (Mobile Device Management) be used.
This will push through updates to ensure vulnerabilities are patched in a timely manner, for instance, and Group Policies can be implemented across all devices.
If a patch exists, this means there is an exploit already out there taking advantage of the vulnerability.
Another good move is to offer CYOD - Choose Your Own Device, provided by the company, rather than BYOD. Bluetooth can be disabled, preventing BlueJacking and BlueSnarfing,
and if location access is denied to all except the GPS app, the effectiveness of some OSINT techniques such as geolocating employees and establishing patterns, diminished.

