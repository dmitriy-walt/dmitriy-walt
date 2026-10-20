# Study-case: Requirements Review for a Pet-Adoption App

**Project:** Pet-Adoption & Donation Web Application (Pet-project)
**Task:** Conduct static testing (requirements review) to identify logical flaws, ambiguities, and inconsistencies before the development phase begins.
**Tools Used:** Google Docs / Confluence (for documentation).

---

## 📝 Project Context & Overview
The goal was to analyze the initial technical requirements for an application designed to help kittens through donations. Early detection of these issues prevents costly rework during the development and QA phases.

The main functionality includes:
*   **Account Section:** Users can create and manipulate virtual bank cards.
*   **Card Limits:** A user can create a maximum of 5 cards. The maximum deposit amount on one card is 100,000.
*   **Donate Section:** Users can transfer money to the shelter using their added cards.
*   **Data Validation:** First and Last names must be 2–20 English characters.

## 🔍 My Findings (Defect Log)

During the review, I identified **12 major issues** categorized by defect type (Incompleteness, Ambiguity, Inconsistency). Here is an excerpt of the most critical findings:

| No | Requirement | Defect Type | Issue Description | Recommendation |
| :--- | :--- | :--- | :--- | :--- |
| **1** | User can create 5 cards | Incompleteness | It is not specified whether a user can create a new card after deleting an existing one. | Clarify the logic for card limits and deletion. |
| **2** | Deposit money up to 100,000 | Ambiguity | What is the minimum deposit? Is it a limit for the account balance or only for transfers? Can a user deposit with a negative balance? What payment methods are allowed (cash, card, crypto)? | Add detailed specifications for payment methods and limits. |
| **3** | Donate any sum to kittens | Inconsistency | The requirements state "donate any sum" (Slide 2), but later introduce a maximum limit of 50,000 (Slide 9). | Resolve the contradiction and define clear min/max limits. |
| **4** | Button "Create a virtual card" disabled | Incompleteness | No information on how to activate this button after registration. | Describe the user flow for activating the button. |
| **5** | Button "Delete" | Incompleteness | No details on what exactly is deleted (all cards or just one?). Also, no accessibility considerations (e.g., screen readers for blind users). | Specify deletion logic and add accessibility requirements. |
| **6** | Field length: 2-20 chars vs <2 / >20 | Inconsistency | Conflict of constraints in the text. | Unify the requirement to mean the same thing. |
| **7** | Expiry date: random month in 2025 | Inconsistency | Hardcoding a specific year for card expiration is illogical. | Define a dynamic expiration period (e.g., 5 years from the card creation date). |

*(The full defect log included 12 issues, covering missing validations, undefined button states, and unclear user flows).*

## 🛠 Additional Findings: Grammar & Usability
Along with logical flaws, I identified critical text and UX issues:
*   **Typos:** "Filed" instead of "Field".
*   **Missing predicates:** Sentences missing action words (e.g., "he will_card section").
*   **UI Text:** "Add moneys" (incorrect pluralization) -> should be "Add Money" or "Add Funds".
*   **UX/Accessibility:** Identified the need to add screen reader support for visually impaired users when interacting with the "Delete" button.

## 💡 Conclusion
Static testing at this stage helped prevent severe bugs (such as duplicate card creation or contradictory donation limits) from reaching production. Documenting these findings in a structured report allowed the business analysts to fix the specification before coding started.
