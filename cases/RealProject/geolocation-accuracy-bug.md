# Geolocation Accuracy Bug (Report & Retest) — Commercial Project (Anonymized)

> ⚠️ **NDA Notice:** Project name, URLs, city names and sensitive data are 
> anonymized. Testing approach and artifacts reflect my actual contribution.

## Project Info
- **Project type:** Map-based mobile & web application
- **My role:** Manual QA / Beta Tester (exploratory testing, part-time, parallel with education)
- **Period:** 04.10.2026 – 10.10.2026
- **Tools:** Testiny (Test Management), DevTools, screen recording

## Task / Context
Testing the **"Where am I"** (Geolocation) functionality. The app is supposed 
to center the map on the user's current location and place a static marker to 
show the exact position. 

I tested this feature across different environments (Desktop PC with Ethernet, 
Mobile via Wi-Fi). The goal was to verify geolocation accuracy, visual feedback, 
and stability.

## Test Cases & Results

### TC-01: Verifying the "Where am I" button and geolocation accuracy
| Field | Value |
|-------|-------|
| **Steps** | 1. Open the map. 2. Click the **"Where am I"** button. 3. Allow location access. 4. Wait for location determination. 5. Observe the map for 10-15 sec. |
| **Expected** | The map centers on the user's location and displays a clear, static marker at the exact coordinates. |
| **Actual** | **First run:** No marker appeared at all, the map just centered on the general area. **After retest (fix applied):** The marker appeared, but it was unstable — the map kept shifting slightly left/right and up/down around the point. |
| **Result** | ❌ **Failed** |
| **Comments** | 1. Initially, users couldn't pinpoint their location (no marker).
| **Attachments** | <video src="./video/geolocation-bug-003.gif" width="500" controls></video> |

## Summary of Results
| Test Case | Result |
|-----------|--------|
| TC-01 | ❌ Failed (Retest revealed a new issue) |

**Not passed:** 1 of 1 — due to the found defects BUG-003 and BUG-004.

## Defect Log

### BUG-003: No precise location marker on the map (Initial defect)
| Field | Value |
|-------|-------|
| **Severity** | Major |
| **Priority** | High |
| **Status** | Fixed (Marker added by developer) |
| **Environment** | 1. Desktop PC (Ethernet). 2. Mobile (Wi-Fi). |

**Steps to reproduce:**
1. Open the map.
2. Click the **"Where am I"** button and allow location access.
3. Wait for the map to center on your location.

**Expected:** A clear marker (pin or dot) is placed at the user's exact current coordinates.
**Actual:** The map centers on the general area, but there is no visual marker indicating the exact current position. 

**Comments:** The bug was verified on two different devices and network types (Ethernet and Wi-Fi), confirming it is a stable, cross-platform issue. The developer confirmed and fixed it by adding a location marker.

---

### BUG-004: Location marker is unstable / UI drift (Found during retest)
| Field | Value |
|-------|-------|
| **Severity** | Minor / Medium |
| **Priority** | Medium |
| **Status** | Open / Reported |
| **Environment** | 1. Desktop PC (Ethernet). 2. Mobile (Wi-Fi). |

**Steps to reproduce:**
1. Open the map.
2. Click the **"Where am I"** button and allow location access.
3. Wait for the marker to appear.
4. Observe the marker and the map behavior for 10-15 seconds.

**Expected:** The marker is strictly static. The map centers on the marker and remains completely still (unless the user physically moves).
**Actual:** The marker appears, but the map constantly shifts slightly back and forth (left/right, up/down) around the target coordinate. The user experiences visual jitter.

**Comments:** 
1. This issue was discovered during the **retest** of BUG-003. While the missing marker was fixed, the new implementation introduced a UI drift/jitter bug.
2. **Suggested UX improvement:** Implement a slight "snap" or debounce logic to stabilize the coordinates, preventing the map from micro-adjusting when the user is standing still.

**Attachments:** 
<video src="./video/retested-bug-004.gif" width="500" controls></video>

## Conclusion
This case was a fantastic lesson in **retesting and regression testing**. 

I initially discovered that the geolocation feature completely lacked a visual marker (BUG-003). I reported it, and the developer implemented a fix. However, instead of just closing the ticket, I performed a **retest** — and discovered a new defect (BUG-004): the newly added marker was unstable, causing the map to jitter back and forth. 

This perfectly illustrates why QA is an iterative process. A "fix" isn't truly successful until it's verified in a real-world scenario. By catching the UI drift, I ensured the feature went from "technically functional" to "actually usable" for the end user.
