# 🏸 SmashPoint — Badminton Mixer Engine

SmashPoint is a lightweight, zero-dependency web application designed to manage rotating doubles badminton tournaments on a single court. 

When you have a group of players (like 6, 7, 8, or 9) and only one court, it can be mathematically frustrating to figure out who plays with who, who sits out, and how to make sure everyone gets equal playtime. SmashPoint handles the scheduling, scorekeeping, and tie-breakers automatically.

## ✨ Features

* **Dynamic Matchmaking:** Auto-generates a balanced schedule ensuring fair playtime, rotations, and bench rests.
* **Live Leaderboard:** Automatically updates standings based on standard BWF tie-breaker rules (Wins → Point Differential → Total Points Scored).
* **Local Storage Save/Resume:** Accidentally closed the tab? No problem. The tournament state is saved directly in your browser.
* **CSV Export:** Download the final scorecard and points table as a `.csv` file to view in Excel or Google Sheets.
* **Zero Dependencies:** The entire app runs from a single `index.html` file. No databases, no frameworks, no backend required.

## 🧠 How the Math Works

SmashPoint uses a **Constraint-Optimization Round-Robin** algorithm. For odd-numbered groups (like 7 or 9 players), standard tournament brackets fail. SmashPoint solves this by:
1. Identifying the 4 players who have sat on the bench the longest.
2. Testing the 3 possible pair combinations for those 4 players.
3. Selecting the matchup that features teammates and opponents who have faced each other the least.
