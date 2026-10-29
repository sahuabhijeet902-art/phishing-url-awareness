# EWB Phishing URL Awareness Checker

A Python-based educational tool that checks URL text for selected phishing warning signs. The program performs text-only checks and does not open URLs or make network requests.

## Overview

This project was created as part of the EWB Cybersecurity Mini Project Workbook. It demonstrates how simple URL characteristics can be used to identify potential warning signs commonly associated with phishing links.

The checker is designed for awareness and education only. Finding no warning signs does not prove that a URL is safe.

## Features

The program checks for six selected warning signs:

1. @ symbol in the URL
2. Unusually long URLs over 100 characters
3. IP address used as the hostname
4. Five or more hostname segments/subdomains
5. Punycode marker (xn--)
6. HTTP instead of HTTPS

The program also:

- Accepts multiple URLs in one run
- Allows the user to quit by entering q, quit, or exit
- Handles malformed URL input without crashing
- Uses only Python standard-library modules
- Does not open or visit submitted URLs

## Requirements

- Python 3
- No additional Python packages are required.

The project uses Python's built-in re and urllib.parse modules.

## How to Run

Open a terminal in the project directory and run:

python phishing_checker.py

Enter a URL when prompted.

To stop the program, enter:

q

## Example

Example input:

https://www.example.com/login

Example output:

Result:
- No listed warning signs found. This does NOT prove safety.

For an IP-based URL:

http://192.0.2.10/account

The checker reports:

- Uses an IP address instead of a familiar domain.
- Uses HTTP. HTTPS alone does not prove trust.

## Testing

The project was tested using the five required sample URLs from the workbook.

Test 1: https://www.example.com/login
Warning Sign: No listed warning signs
Status: PASS

Test 2: http://192.0.2.10/account
Warning Sign: IP address + HTTP
Status: PASS

Test 3: http://example.com@sample.invalid/login
Warning Sign: @ symbol + HTTP
Status: PASS

Test 4: https://a.b.c.d.e.example.invalid/path
Warning Sign: Many hostname segments
Status: PASS

Test 5: https://xn--example.invalid/
Warning Sign: Punycode
Status: PASS

Detailed test results are available in tests/test_samples.md.

## Screenshots

The test evidence is available in the screenshots folder.

- sample_run.png — terminal output showing part of the required test results
- test_results.png — terminal output showing the remaining required test results

Together, the two screenshots show the results of all five required test URLs.

## Improvements

Two improvements were added after the basic version was working.

### Improvement 1 — Multiple URL Checks

The program can now inspect multiple URLs during a single run. The user does not need to restart the program after every URL.

The program can be stopped using:

q
quit
exit

### Improvement 2 — Malformed URL Handling

The program safely handles malformed URL input such as:

http://[bad

Instead of crashing, it reports that the text is not a valid URL format.

## Limitations

This tool only checks the six selected warning signs listed above.

It does not:

- Open or visit URLs
- Check website content
- Query reputation services
- Use VirusTotal or other external APIs
- Perform WHOIS lookups
- Guarantee that a URL is safe or malicious

A URL with no listed warning signs may still be dangerous.

## Ethical Use

This project is intended for cybersecurity education and URL awareness.

Only use the checker for legitimate educational, testing, and awareness purposes. Do not use it to access or investigate websites without appropriate authorization.

## Author

Abhijeet Sahu

BCA Student
BBD University, Lucknow
