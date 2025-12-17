# Remote Repository – Setup & Reproducibility

This document explains how to clone and run this project on a new machine.

---

## 1. Clone the repository

This step downloads the project from GitHub onto a new computer.

```bash
git clone https://github.com/baderknufinke/Sales_Analysis_Project.git
cd Sales_Analysis_Project

---

## 2. Python usage (optional)
This project is primarily SQL-based.

Python is only used if and when we:
- run statistical analysis
- work in notebooks
- build small automation or application components

If Python is required, set it up like this:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

---

## 3. Secrets and configuration

Project credentials are stored in a local `.env` file.

This file:
- is created locally
- is never committed to Git
- is ignored via `.gitignore`

Typical variables include:
- DB_HOST
- DB_PORT
- DB_NAME
- DB_USER
- DB_PASSWORD

---

## 4. PostgreSQL

This project uses PostgreSQL as the main execution engine.

Use a local PostgreSQL installation and connect using:
- psql (command line), or
- DBeaver (GUI)

The working database for this project is typically:
- sales_analytics
