# Abuse Case: Point Farming Vulnerability — Commercial Project (Anonymized)

> ⚠️ **NDA Notice:** Project name, URLs, city names and sensitive data are 
> anonymized. Testing approach and artifacts reflect my actual contribution.

## Project Info
- **Project type:** Map-based mobile & web application with store markers (pins) and a user points/ranking system
- **My role:** Manual QA / Beta Tester (exploratory testing, part-time, parallel with education)
- **Period:** 12.09.2026
- **Tools:** DevTools, screen recording, Testiny

## Task / Context
Testing the **user points and ranking system**. Users earn points for adding 
markers to the map. To prevent spam, points are supposed to be deducted if a 
marker is deleted. 

My task was to verify the synchronization between marker creation/deletion and 
the user's point balance, specifically checking for potential system abuse (farming).

## Test Cases & Results

### TC-01: Point deduction upon marker deletion
| Field | Value |
|-------|-------|
| **Steps** | 1. Create a marker in the green zone. 2. Check the points counter (+1 point). 3. Delete the marker. 4. Check the points counter again. |
| **Expected** | The point earned for the marker is deducted (-1 point). The user's score returns to the original value. |
| **Actual** | After deleting the marker, the point is **not deducted**. The user retains the point for a non-existent marker. |
| **Result** | ❌ **Failed** — defect found (see BUG-003) |
| **Comments** | This breaks the integrity of the ranking system. Users can inflate their points by creating and deleting markers. |
| **Attachments** | <img src="./videos/points-bug.gif" width="500" alt="Points not deducted"> |

### TC-02: Abuse Case — Point Farming Loop
| Field | Value |
|-------|-------|
| **Steps** | 1. Create a marker and immediately delete it. 2. Repeat this cycle 10 times in a row. 3. Check the user's rank and point balance. |
| **Expected** | The system prevents abuse. The point balance remains the same. Rapid create/delete actions should be blocked or reverted. |
| **Actual** | The user gains +1 point for every cycle. After 10 cycles, the user has 10 extra points without any actual contribution. The rank increases. |
| **Result** | ❌ **Failed** — defect found (see BUG-003) |
| **Comments** | **Critical Abuse Case (Farming).** The system allows users to artificially inflate their points, making the entire leaderboard/ranking system meaningless. |
| **Attachments** | <img src="./videos/points-farming.gif" width="500" alt="Point farming abuse"> |

## Summary of Results
| Test Case | Result |
|-----------|--------|
| TC-01 | ❌ Failed (bug found) |
| TC-02 | ❌ Failed (bug found) |

**Not passed:** 2 of 2 — due to the found defect BUG-003.

## Defect Log

### BUG-003: Points are not deducted upon marker deletion (Point Farming vulnerability)
| Field | Value |
|-------|-------|
| **Severity** | Critical |
| **Priority** | Highest |
| **Status** | Open / Reported |
| **Environment** | Web & Mobile |

**Steps to reproduce:**
1. Open the map and create a marker (note the +1 point added).
2. Immediately delete the marker.
3. Observe the point balance.
4. Repeat steps 1-2 rapidly.

**Expected:** The point balance decreases when a marker is deleted. Rapid add/delete actions are rate-limited.
**Actual:** The points are not deducted. Users can repeatedly create and delete markers to infinitely farm points, breaking the ranking system.

**Comments:** 
1. This is a critical business logic flaw that allows users to cheat the system. 
2. **Suggested fix:** Implement a transaction rollback for points upon marker deletion, and add a cooldown for rapid add/delete actions.

**Attachments:** 
<img src="./videos/points-bug.gif" width="500" alt="Points not deducted">
<img src="./videos/points-farming.gif" width="500" alt="Farming abuse">

## Conclusion
This case was a deep dive into **Abuse Case Testing** and **Business Logic vulnerabilities**. 

I initially discovered a simple synchronization bug (points not deducted on deletion). However, by taking it a step further and testing how a malicious user could exploit this, I identified a **Point Farming vulnerability**. By creating and deleting markers in a loop, users could artificially inflate their rank.

This taught me that a good QA should think like an attacker (abuser). Finding a bug is good, but understanding how it affects the entire product ecosystem and identifying potential exploits is what brings real value to the team.
