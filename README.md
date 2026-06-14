# AI-Powered Security Scanner 🛡️

A lightweight, automated static analysis tool that leverages the Gemini API to scan source code files for security vulnerabilities, misconfigurations, and potential exploits. The scanner outputs real-time analysis directly to your terminal with color-coded severity levels.

## Features

* **AI-Driven Static Analysis:** Utilizes the `gemini-2.5-flash` model to analyze code chunks for potential weaknesses.
* **Structured Risk Assessment:** Categorizes issues into standardized severity levels (`CRITICAL`, `HIGH`, `MEDIUM`, `LOW`).
* **Colorized Terminal Output:** Employs `colorama` to visually highlight high-risk findings for rapid auditing.
* **Secure Credential Handling:** Separates configuration from code using environment variables (`python-dotenv`) to prevent API key exposure.

---

## Project Structure

```text
security-scanner/
│
├── venv/                 # Python Virtual Environment (Ignored by Git)
├── .env                  # Private configurations (Excluded from Git)
├── .env.example          # Public environment template
├── .gitignore            # Git exclusion rules
├── scanner.py            # Main application source code
├── vulnerable.py         # Target file for testing/auditing
└── README.md             # Documentation
```

Installation & Setup
1. Clone the Repository
```
git clone [https://github.com/Hayder-Ben-Abdelhamid/Security-scanner.git](https://github.com/Hayder-Ben-Abdelhamid/Security-scanner.git)
cd Security-scanner
```

2. Set Up a Virtual Environment
```
python -m venv venv
# On Windows:
venv\Scripts\activate
# On Linux/macOS:
source venv/bin/activate
```

3. Install Dependencies
```
pip install python-dotenv google-genai colorama
```

4. Configure Environment Variables
Duplicate the example template and create your localized .env configuration file:

```
copy .env.example .env
```

Open the newly created .env file and insert your API credentials:

```
SECRET_API_KEY=your_actual_gemini_api_key_here
```

Usage
To execute a static analysis check against a target source file, pass the file path as an argument to the main script:

```
python scanner.py vulnerable.py
```

Example Output Format
---
SEVERITY: CRITICAL
TYPE: SQL Injection
DESCRIPTION: User input from the URL parameters is directly concatenated into a raw database query.
IMPACT: Remote attackers can manipulate database structures, bypass authentication checks, or extract raw records.
FIX: Use parameterized inputs / prepared statements instead of string formatting.
---

Security Notice
This repository implements secure design patterns by excluding local operational environments and dynamic access tokens (.env) from global code versioning histories using comprehensive .gitignore filtering. Never check raw secrets directly into code tracking streams.
