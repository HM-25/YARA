# YARA

Study notes on **YARA**, the pattern matching tool used to identify and classify malware.

> "The pattern matching swiss knife for malware researchers (and everyone else)" (VirusTotal)

## Contents

| Note | Topic |
|------|-------|
| [What is YARA?](What%20is%20Yara%3F.md) | What YARA is and how it matches files by strings and conditions |
| [YARA Rules](Yara%20Rules.md) | Rule structure: meta, strings, conditions and modules |
| [YARA Tools](Yara%20Tools.md) | Tools and projects built around YARA |
| [LOKI](LOKI.md) | LOKI, a free IOC and YARA scanner |
| [VALHALLA](WALHALLA.md) | Nextron's VALHALLA feed of ready-made YARA rules |

## Quick example

```yara
rule example_rule
{
    meta:
        description = "Matches files containing a test string"
    strings:
        $s1 = "Hello World!"
    condition:
        $s1
}
```

## About

Personal notes written while studying threat detection and malware analysis. Official docs: [yara.readthedocs.io](https://yara.readthedocs.io/)
