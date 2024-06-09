Using LOKI
Overview

As a security analyst, you'll need to research various threat intelligence sources to gather IOCs (hashes, IP addresses, domain names, etc.) and create rules to detect threats. If you encounter something unknown that your security tools can't detect, you can use tools like LOKI to add your own rules based on your findings.
LOKI Basics

LOKI comes with a set of Yara rules you can use immediately to scan for threats on endpoints.
Steps to Use LOKI

    Navigate to the tools directory:

    sh

cmnatic@thm-yara:~/tools$ ls
Loki  yarGen

Run LOKI Help Command:

sh

cmnatic@thm-yara:~/tools/Loki$ python loki.py -h

Update LOKI (if running on your own system):

sh

python loki.py --update

This command adds the signature-base directory, which LOKI uses to scan for known threats.

Inspect the signature-base directory:

sh

cmnatic@thm-yara:~/tools/Loki/signature-base$ ls
iocs  misc  yara

Navigate to the Yara directory and inspect Yara files:

sh

    cd yara

Running LOKI

To scan a suspicious file, use the following command from within the file directory:

sh

cmnatic@thm-yara:~/suspicious-files/file1$ python ../../tools/Loki/loki.py -p .

This command instructs LOKI to scan the current directory for any suspicious files using the pre-configured Yara rules.
Conclusion

LOKI is a powerful tool for incorporating custom threat intelligence and enhancing your security operations. It allows you to leverage existing Yara rules while adding your own based on ongoing threat intelligence and incident response findings.
