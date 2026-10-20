# Case Study: Test Design (Pairwise Testing) for a Real Estate App

**Project:** Apartment Rental Application (Educational Project)
**Task:** Optimize test coverage using the Pairwise testing technique to reduce the number of test cases without losing coverage of critical parameter combinations.
**Tools Used:** Google Sheets / Microsoft Excel.

---

## 📝 Project Context & Overview
The goal was to test the apartment search functionality. The search form has the following filters:
*   **Rent Type:** All, Long-term, Daily (3 options)
*   **Floor:** 1 to 50 inclusive (but for testing, we define boundary/class values, e.g., 1, 25, 50)
*   **District:** Moldavanka, Primorskiy, Center, Arcadia (4 options)
*   **Pets:** Yes, No (2 options)

If we used exhaustive testing (test everything), we would need `3 * 3 * 4 * 2 = 72` test cases. 

## 🛠 My Approach
Instead of full combinatorial testing, I applied the **Pairwise Testing** technique. This method ensures that every pair of input parameters is tested at least once.

As a result, the number of test cases was reduced from 72 to **12**, significantly optimizing testing time while maintaining high coverage of interactions between parameters.

### Generated Test Suite (Pairwise)

| № | Rent Type | Floor | District | Pets |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **All** | 50 | Moldavanka | Yes |
| 2 | **Long-term** | 1 | Arcadia | No |
| 3 | **Daily** | 25 | Primorskiy | Yes |
| 4 | **Long-term** | 1 | Moldavanka | No |
| 5 | **Long-term** | 25 | Center | Yes |
| 6 | **Long-term** | 50 | Primorskiy | No |
| 7 | **Daily** | 1 | Arcadia | Yes |
| 8 | **Daily** | 25 | Moldavanka | Yes |
| 9 | **Daily** | 50 | Center | No |
| 10 | **All** | 1 | Primorskiy | Yes |
| 11 | **All** | 25 | Center | No |
| 12 | **All** | 50 | Arcadia | Yes |

## 💡 Conclusion
Applying the Pairwise technique reduced the test suite from 72 to 12 cases. This approach significantly decreased testing time and resources while ensuring that all critical interactions between the search parameters (Rent Type, Floor, District, Pets) were fully validated.
