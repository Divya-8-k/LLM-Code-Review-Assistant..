# Develop the First Working LLM Code-Review Assistant

## 📌 Project Overview

This project demonstrates the development of a working **LLM Code-Review Assistant** that combines static-analysis tools and a Large Language Model (LLM) to automatically review source code, identify issues, explain their impact, and recommend fixes.

The assistant analyzes Python programs using industry-standard tools such as Flake8, Pylint, and Bandit. The generated reports are then processed and provided to an LLM, which acts as an expert code reviewer.

The goal is to improve code quality, maintainability, and security while reducing manual review effort.

---

## 🎯 Objectives

The main objectives of this project are:

* Develop a working LLM-powered code-review assistant.
* Perform automated static code analysis.
* Detect code-quality issues and security vulnerabilities.
* Generate Flake8, Pylint, and Bandit reports.
* Combine multiple analysis reports.
* Use an LLM to explain detected issues.
* Recommend improvements and fixes.
* Generate a developer-friendly review report.
* Validate corrected code using static-analysis tools.

---

## 🛠️ Technologies Used

| Technology   | Purpose                               |
| ------------ | ------------------------------------- |
| Python       | Source code development               |
| Flake8       | Style and lint analysis               |
| Pylint       | Code quality analysis                 |
| Bandit       | Security vulnerability detection      |
| LLM          | Issue explanation and recommendations |
| Google Colab | Development and execution environment |
| GitHub       | Project hosting and version control   |

---

## 📂 Project Structure

```text
LLM-Code-Review-Assistant/
│
├── LLM_Code_Review_Assistant.ipynb
├── README.md
│
├── sample.py
├── sample_fixed.py
│
├── flake8_report.txt
├── pylint_report.txt
├── bandit_report.txt
│
└── review_report.txt
```

---

## 🔍 Sample Source Code

The project analyzes the following Python program:

```python
import os

password = "12345"

def divide(a,b):
    return a/b

print(divide(10,0))
```

The code intentionally contains style, quality, and security issues for demonstration purposes.

---

## 🔎 Static Analysis

The notebook installs the required tools:

```bash
pip install flake8 pylint bandit
```

The following commands are executed:

```bash
flake8 sample.py > flake8_report.txt

pylint sample.py > pylint_report.txt

bandit -r sample.py > bandit_report.txt
```

Each tool generates a report highlighting different types of issues.

---

## 🤖 LLM Code Review

After static analysis, the generated reports are combined and passed to a Large Language Model.

The LLM performs the following tasks:

1. Explains each identified issue.
2. Describes why the issue is important.
3. Suggests possible fixes.
4. Recommends coding best practices.
5. Produces a human-readable review report.

---

## 📋 Example Issues Identified

### Issue 1: Hardcoded Password

#### Explanation

The password is directly stored in the source code.

```python
password = "12345"
```

#### Why It Matters

Hardcoded credentials can be exposed when code is shared publicly and may lead to security risks.

#### Suggested Fix

Use environment variables or secure secret-management systems.

---

### Issue 2: Unused Import

#### Explanation

The `os` module is imported but never used.

#### Suggested Fix

Remove the unused import statement.

---

### Issue 3: PEP 8 Formatting Violation

#### Explanation

The function definition does not contain whitespace after commas.

```python
def divide(a,b):
```

#### Suggested Fix

```python
def divide(a, b):
```

---

### Issue 4: Division by Zero

#### Explanation

The program attempts to divide by zero.

```python
print(divide(10,0))
```

#### Why It Matters

This causes a runtime exception and program failure.

#### Suggested Fix

Validate the divisor before performing division.

---

## ✅ Corrected Code

The assistant generates an improved version:

```python
"""Sample calculator module."""

def divide(a, b):
    """Divide two numbers safely."""
    if b == 0:
        return "Cannot divide by zero"
    return a / b

print(divide(10, 2))
```

---

## 🔄 Validation

The corrected code is analyzed again using:

```bash
flake8 sample_fixed.py
```

```bash
pylint sample_fixed.py
```

```bash
bandit -r sample_fixed.py
```

This ensures that the identified issues have been resolved successfully.

---

## 🔄 Workflow

```text
        Python Source Code
                ↓
        ┌─────────────────┐
        │    Flake8       │
        ├─────────────────┤
        │    Pylint       │
        ├─────────────────┤
        │    Bandit       │
        └─────────────────┘
                ↓
        Analysis Reports
                ↓
         Combined Report
                ↓
            LLM Prompt
                ↓
        LLM Code Review
                ↓
      Issue Explanations
                ↓
      Suggested Fixes
                ↓
       Corrected Code
                ↓
      Re-run Validation
```

---

## 📚 Learning Outcomes

This project demonstrates:

* Static code analysis techniques
* Secure coding practices
* Automated code-review workflows
* LLM-assisted software engineering
* Security vulnerability detection
* Code-quality improvement
* Report generation and interpretation
* Validation of corrected source code

---

## 🚀 How to Run

### Step 1: Open the Notebook

Open:

```text
LLM_Code_Review_Assistant.ipynb
```

using Google Colab or Jupyter Notebook.

### Step 2: Install Required Packages

```bash
pip install flake8 pylint bandit
```

### Step 3: Run the Notebook

Execute all cells in sequence.

The notebook will:

1. Create sample source code.
2. Run Flake8 analysis.
3. Run Pylint analysis.
4. Run Bandit analysis.
5. Combine generated reports.
6. Generate an LLM review prompt.
7. Explain issues and recommendations.
8. Create corrected source code.
9. Validate improvements through re-analysis.

---

## 👩‍💻 Author

**Divya K**

---

## 📌 Project Type

**LLM-Assisted Static Code Analysis and Automated Code Review System**
