Alter_J_assignment2
===================

Apache log analyzer (Assignment 2)

A small CLI tool that parses Apache Combined Log Format lines and reports:
- top active hosts (counts every request per host)
- top downloaded resources (counts only GET requests)

The analyzer filters log lines by inclusive calendar date (MM/DD/YYYY) using only the date portion of the CLF timestamp.

Usage
-----
From the project folder run:

```powershell
# basic: log file in same directory
python Alter_J_assignment2.py apache_logs_small

# with start date
python Alter_J_assignment2.py apache_logs_small 05/18/2015

# with start + end
python Alter_J_assignment2.py apache_logs_small 05/17/2015 05/17/2015
```

Notes
-----
- Dates must be MM/DD/YYYY.
- The assignment text uses textual defaults `01/01/0000` and `12/30/9999` — Python's datetime does not accept year 0000, so the program prints the original textual defaults but maps them internally to safe bounds (datetime.date.min and datetime.date.max) for filtering.
- The host is taken as the first token of each line; the request is taken from the first `"..."` pair after the date. Malformed lines are skipped.
- The top lists include ties at the cutoff (so you may see >30 results).
- Do not commit large log files (for example `apache_logs`); add them to `.gitignore`.

Running on the department machine (linprog)
-----------------------------------------
Steps (on linprog shell):

```bash
# download sample if needed
wget -O apache_logs_small 'https://www.cs.fsu.edu/~xyuan/cop4521/apache_logs_small'

# run
python3 Alter_J_assignment2.py apache_logs_small
```

License / Author
----------------
Author: Judah Alter
Repository: https://github.com/JudahA72/Python-Parallelism

