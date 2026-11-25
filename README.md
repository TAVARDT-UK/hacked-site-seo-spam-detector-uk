# Hacked Site and SEO Spam Detector

[![SEO Spam Detector](https://img.shields.io/badge/TAVARDT-Antispam%20SEO-5b3cf5.svg)](https://tools.tavardt.com/uk/seo-spam-detector/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Application security audit tool detecting user-agent cloaking, hidden backlink farms, conditional mobile redirects, and web compromise indicators.

***

## Forensic Audit and SEO Compromise Capabilities

* **Search Engine Cloaking Detection**: Differential HTML inspection contrasting standard user-agent responses with Googlebot crawler requests.
* **Hidden Link and Keyword Injections**: Pinpointing zero-opacity text blocks, negative-margin containers, and illicit off-screen iframe tags.
* **Conditional Malicious Redirects**: Automated tracking of evasive redirection rules tailored to search referrers or mobile screen resolutions.
* **Forensic Integrity Benchmark**: Reproducible 0 to 100 scoring with prioritised mitigation and site cleanup procedures.

***

## Installation and Execution

Requires Python 3.8 or higher with zero external packages.

```bash
git clone https://github.com/TAVARDT-UK/hacked-site-seo-spam-detector-uk.git
cd hacked-site-seo-spam-detector-uk
python seo_spam_detector.py example.co.uk
```

To output structured JSON:

```bash
python seo_spam_detector.py example.co.uk -json
```

***

## Digital Forensics and Malware Remediation Advisory

For emergency incident response, manual code decontamination, and hardening aligned with NCSC Cyber Essentials and Web Integrity Standards, contact the security practice at **TAVARDT**.

***

## Useful Links

* **Corporate Portal:** https://ag.tavardt.com/uk/
* **Diagnostic Suite:** https://tools.tavardt.com/uk/
* **Technical Contact:** https://ag.tavardt.com/uk/contact/

***

***

### License
Released under the MIT License.

***

© 2026 TAVARDT. All rights reserved.
