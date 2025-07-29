# Project
Web Application Vulnurability Scanner
Web Application Vulnerability Scanner
Overview
A Python-based web application vulnerability scanner designed to detect common security flaws including XSS (Cross-site Scripting), SQL Injection (SQLi), and CSRF (Cross-Site Request Forgery). It crawls web applications, injects test payloads, analyzes responses to detect vulnerabilities, and presents results via a simple Flask-based web interface.

Features
Recursive crawling of input fields and URLs

Injection of crafted payloads for common vulnerabilities

Response analysis using regex and pattern matching

Detection of XSS, SQLi, and CSRF vulnerabilities

Flask UI for managing scans and viewing detailed reports

Logs vulnerabilities with evidence and severity level

Modular code structure for easy extension

Technology Stack
Python

requests (HTTP requests)

BeautifulSoup (HTML parsing)

re (Regex for detection)

Flask (Web UI)

OWASP Top 10 guidelines for testing coverage

Installation
bash
git clone https://github.com/your-username/web-vuln-scanner.git
cd web-vuln-scanner
pip install -r requirements.txt
Usage
Run the Flask application:

bash
python main.py
Open your browser and navigate to http://localhost:5000.

Enter the target website URL you want to scan.

Start the scan and view results on the web interface.

Project Structure
text
web-vuln-scanner/
│
├── main.py               # Flask server with routes  
├── scanner/              # Scanner modules  
│   ├── crawler.py        # Crawling logic  
│   ├── payloads.py       # Payload definitions  
│   ├── analyzer.py       # Vulnerability detection logic  
│   └── logger.py         # Logging and report generation  
├── templates/            # HTML templates for the web UI  
│   ├── index.html        # Home page  
│   ├── results.html      # Results display  
├── static/               # Static assets (CSS)  
│   └── styles.css        # UI styling  
└── reports/              # Saved scan reports  
Example Report Entry
json
{
  "url": "http://example.com/login",
  "vulnerability": "SQL Injection",
  "parameter": "username",
  "payload": "' OR '1'='1",
  "severity": "High",
  "evidence": "SQL syntax error: unrecognized token ''OR''"
}
Limitations
May produce false positives or false negatives.

Limited support for JavaScript-heavy (SPA) applications.

CSRF detection assumes predictable token mechanisms.

Intended only for authorized penetration testing and educational use.

Future Enhancements
Support for authentication (cookies, sessions).

Persistent database logging (SQLite).

Export reports in PDF/Excel format.

Broaden vulnerability coverage beyond OWASP Top 10 basics.

Async crawling and scanning for improved performance.

Disclaimer
Use this tool only on websites you own or have explicit permission to test. Unauthorized scanning may be illegal.
