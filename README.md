<p align="center">
  <a href="https://ag.tavardt.com/uk/">
    <img src="https://ag.tavardt.com/img/tavardt-banner.png" alt="TAVARDT" width="1024" />
  </a>
</p>

# Hacked Site and SEO Spam Detector

[![SEO Spam Detector](https://img.shields.io/badge/TAVARDT-Antispam%20SEO-5b3cf5.svg)](https://tools.tavardt.com/uk/seo-spam-detector/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

The **TAVARDT Hacked Site and SEO Spam Detector** provides forensic inspection for web applications across the United Kingdom, identifying search engine cloaking, concealed pharma and gambling links, hidden iframes, and obfuscated code.

***

## Detection Architecture and Forensic Vector Matrix

Search bot cloaking and stealth text injections mislead search engine crawlers while hiding malicious content from regular users. This compromise triggers immediate algorithmic penalties, domain blacklisting, and brand reputational damage.

This lightweight auditing engine compares response sizes between differing User-Agents, inspects obscured CSS styling blocks, and isolates stealth tracking elements without third-party dependencies.

The diagnostic engine evaluates DOM structure, differential response byte volumes, and suspicious script patterns starting from a 100-point baseline:

<table>
  <thead>
    <tr>
      <th>Compromise Vector</th><th>Detection Logic</th><th>Deduction</th><th>Integrity Impact</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Differential Cloaking</strong></td><td>Compares standard browser User-Agent against Googlebot. Flagged when byte divergence ratio > 0.40 and absolute delta > 1000 bytes.</td><td>-30 pts</td><td>High risk of search engine de-indexing and critical ranking loss.</td>
    </tr>
    <tr>
      <td><strong>Spam Keyword Injection</strong></td><td>Scans containers styled with <code>display:none</code>, <code>opacity:0</code>, or off-screen negative margins for pharmaceutical/gambling terms.</td><td>-35 pts</td><td>Critical compromise indicator confirming database or template tampering.</td>
    </tr>
    <tr>
      <td><strong>Concealed iframes</strong></td><td>Identifies zero-dimension (width/height=0) or hidden iframes not matching legitimate security vendor whitelists.</td><td>-20 pts</td><td>Potential drive-by download, credential harvesting, or unauthorized redirection.</td>
    </tr>
    <tr>
      <td><strong>Obfuscated Execution</strong></td><td>Identifies repeated dynamic execution patterns including <code>eval()</code>, <code>unescape()</code>, and <code>base64_decode</code> (>2 instances).</td><td>-15 pts</td><td>Suspicious payload delivery indicative of persistent backdoor scripts.</td>
    </tr>
    <tr>
      <td><strong>Connection Failure</strong></td><td>Network timeout or failure during SSL/TLS negotiation or HTTP handshake.</td><td>-20 pts</td><td>Host unreachability preventing thorough forensic verification.</td>
    </tr>
  </tbody>
</table>

### Integrity Health Scale

The utility calculates a consolidated integrity health score categorizing target status:

* <strong>85 to 100 (CLEAN)</strong>: No compromise indicators detected; standard response consistency observed across user-agents.
* <strong>60 to 84 (SUSPICIOUS)</strong>: Anomalies detected in layout styling, iframes, or payload variance requiring immediate manual inspection.
* <strong>0 to 59 (COMPROMISED)</strong>: Confirmed presence of cloaking, spam injection, or obfuscated payloads demanding immediate containment.

***

## Installation and Execution

Built with pure Python standard library modules with zero third-party dependencies.

```bash
git clone https://github.com/TAVARDT-UK/hacked-site-seo-spam-detector-uk.git
cd hacked-site-seo-spam-detector-uk
```

### Standard CLI Execution

```bash
python seo_spam_detector.py example.co.uk
```

### Automated CI/CD Pipeline JSON Output

```bash
python seo_spam_detector.py example.co.uk -j
```

### Custom Timeout Configuration

```bash
python seo_spam_detector.py example.co.uk -j -t 15
```

***

## NCSC Alignment and Cyber Essentials Plus

This diagnostic tool supports the **National Cyber Security Centre (NCSC)** guidance and Cyber Essentials Plus controls. Early detection of unauthorized modifications prevents supply chain exploitation and preserves consumer trust.

UK businesses should embed automated DOM cloaking and hidden link audits within deployment workflows to ensure application resilience and regulatory compliance.

***

## Technical Frequently Asked Questions

### How does the differential cloaking detection algorithm operate?

The engine dispatches two sequential HTTP requests to the target domain, first utilizing a standard modern browser User-Agent and subsequently identifying as Googlebot. If the proportional divergence in byte length exceeds 0.40 and the absolute byte variance exceeds 1000 bytes, the tool reports a cloaking violation with a 30-point deduction.

### What criteria distinguish suspicious hidden iframes from legitimate ones?

The scanner identifies iframes configured with zero width, zero height, or <code>display:none</code> inline styling. Elements containing whitelisted vendor strings such as Cloudflare, Google reCAPTCHA, Google Tag Manager, or hCaptcha are recognized as safe, whereas unrecognized hidden iframes incur a 20-point deduction.

### Which specific spam terms are targeted in obscured CSS containers?

The pattern analyzer inspects containers hidden through <code>visibility:hidden</code>, <code>display:none</code>, <code>opacity:0</code>, or negative pixel offsets for terms including viagra, cialis, casino, payday loan, replica watch, poker, roulette, baccarat, vape, and ketamine. Detection results in a 35-point penalty.

### Why are repeated eval and unescape code patterns penalized?

Legitimate modern production code rarely relies on inline <code>eval()</code> or <code>unescape()</code> calls. Encountering more than two instances of these patterns signals potential obfuscated script injection or dropper code, resulting in a 15-point penalty.

### How can automated pipelines consume the diagnostic results?

Executing the scanner with the <code>-j</code> flag instructs the utility to emit structured JSON output to stdout. This output provides machine-readable score metrics, finding details, and remediation recommendations for direct integration into monitoring dashboards.

***

## NCSC Aligned Incident Response and Remediation

For emergency web decontamination and technical resilience under NCSC Guidelines and Web Application Security, consult **TAVARDT**.

***

## Useful Links

* **Corporate Portal:** https://ag.tavardt.com/uk/
* **Diagnostic Suite:** https://tools.tavardt.com/uk/
* **Technical Contact:** https://ag.tavardt.com/uk/contact/

***

### License
Released under the MIT License.

***

© 2026 TAVARDT. All rights reserved.
