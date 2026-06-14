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
├── .env                  # Private configurations (Excluded from Git)
├── .env.example          # Public environment template
├── .gitignore            # Git exclusion rules
├── scanner.py            # Main application source code
├── vulnerable.py         # Target file for testing/auditing
└── README.md             # Documentation
