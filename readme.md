# WordPress Plugin The True Ranker 2.2.2 - Arbitrary File Read

Python proof-of-concept for **CVE-2021-39312**, affecting **The True Ranker (seo-local-rank)** WordPress plugin versions **≤ 2.2.2**.

## Vulnerability Details

* **CVE:** CVE-2021-39312
* **Type:** Arbitrary File Read
* **Affected Plugin:** The True Ranker
* **Affected Versions:** ≤ 2.2.2
* **Vendor Homepage:** https://wordpress.org/plugins/seo-local-rank/
* **Plugin Source:** https://plugins.svn.wordpress.org/seo-local-rank/tags/2.2.2/

## Description

The vulnerability allows an attacker to read arbitrary files from the target server via a path traversal issue in:

```text
wp-content/plugins/seo-local-rank/admin/vendor/datatables/examples/resources/examples.php
```

The exploit attempts to retrieve:

```text
wp-config.php
```

and saves the response locally.

## Requirements

Install dependencies:

```bash
pip install requests
```

## Usage

```bash
python exploit.py -u http://127.0.0.1
```

## Arguments

| Argument      | Description |
| ------------- | ----------- |
| `-u`, `--url` | Target URL  |

## Tested On

* Linux

## References

* CVE-2021-39312
* https://wordpress.org/plugins/seo-local-rank/
* https://plugins.svn.wordpress.org/seo-local-rank/tags/2.2.2/

## Disclaimer

This project is provided for educational purposes and authorized security testing only. The author is not responsible for misuse or damage caused by this code.
