Yara Tools
Introduction

Creating custom Yara rules is useful, but many pre-existing resources can help you leverage Yara for hunting operations or incident response engagements.
LOKI

LOKI is a free, open-source IOC (Indicator of Compromise) scanner created by Florian Roth. It uses four main detection methods:

    File Name IOC Check
    Yara Rule Check
    Hash Check
    C2 Back Connect Check

Usage Example:

sh

python3 loki.py -h

THOR Lite

THOR Lite is Florian Roth's multi-platform IOC and YARA scanner. It is available for Windows, Linux, and macOS, and features scan throttling to limit CPU resource usage.

Usage Example:

sh

./thor-lite-linux-64 -h

FENRIR

FENRIR is a bash script that runs on any system capable of running bash. It was created to address issues with the requirements of previous tools.

Usage Example:

sh

./fenrir.sh

YAYA (Yet Another Yara Automaton)

YAYA, created by the Electronic Frontier Foundation (EFF), helps researchers manage multiple YARA rule repositories. It allows importing, adding, disabling rulesets, and running scans of files. Note that YAYA runs only on Linux systems.
Additional Notes

    These tools are not required for use in the current context but can significantly aid in various security operations.
    For detailed usage and download instructions, refer to the respective GitHub pages or official documentation.
