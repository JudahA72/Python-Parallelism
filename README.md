Python Projects 1 & 2
=====================

This repository holds two small Python projects (Assignment 1 and Assignment 2). The files are in the project root and are ready to run.

Summary
-------
- Project 1 (Python Project 1) — an iterative Prisoner's Dilemma tournament / strategy runner. File: `Alter_J_assignment1.py`.
	- Implements several strategies (always cooperate/defect, probing, adaptive strategies) and a small CLI that asks how many rounds and how many strategies to include in the tournament.
	- Interactive: it prompts for number of rounds and how many strategies to use, then runs pairwise matches and prints total scores per strategy.

- Project 2 (Python Project 2) — Apache log analyzer. File: `Alter_J_assignment2.py`.
	- CLI tool that parses Apache Combined Log Format lines and reports:
		- top active hosts (counts all methods)
		- top downloaded resources (counts only GET requests)
	- Filters by inclusive calendar date (MM/DD/YYYY) using only the date part of the CLF timestamp.
	- Includes tie-handling for the top-N lists (will include all items tied at the cutoff).

Quick usage
-----------
From the project folder (PowerShell on Windows):

```powershell
cd 'C:\Users\Judah\Desktop\CS-School\ParaPython\CodeProjects'

# Run Project 1 (interactive)
python Alter_J_assignment1.py

# Run Project 2 (analyzer) against a local small sample
python Alter_J_assignment2.py apache_logs_small

# Run Project 2 with date filters (MM/DD/YYYY)
python Alter_J_assignment2.py apache_logs_small 05/18/2015
python Alter_J_assignment2.py apache_logs_small 05/17/2015 05/17/2015
```

Running on linprog (remote)
----------------------------
If you copied files to linprog or will fetch the sample log there, use these commands on linprog:

```bash
# download sample if needed
wget -O apache_logs_small 'https://www.cs.fsu.edu/~xyuan/cop4521/apache_logs_small'

# run the analyzer
python3 Alter_J_assignment2.py apache_logs_small

# run interactive project 1
python3 Alter_J_assignment1.py
```

Details & notes
---------------
- Project 1 is interactive and prints scores for each strategy after running pairwise matches.
- Project 2 prints two top lists and a summary line of kept/total lines. Dates must be `MM/DD/YYYY`.
- The assignment text uses textual defaults `01/01/0000` and `12/30/9999`. The analyzer preserves those strings for display but maps them internally to safe Python date bounds (to avoid errors with year 0000).
- Do not commit large log files (e.g., `apache_logs`); add them to `.gitignore`.

How to push this README update
-----------------------------
Run these commands from your project folder to commit and push the updated README:

```powershell
cd 'C:\Users\Judah\Desktop\CS-School\ParaPython\CodeProjects'
git add README.md
git commit -m "Add comprehensive README for Projects 1 & 2"
git push origin main
```

If the remote is not set, add it first:

```powershell
git remote add origin https://github.com/JudahA72/Python-Parallelism.git
git push -u origin main
```

Author
------
Judah Alter

