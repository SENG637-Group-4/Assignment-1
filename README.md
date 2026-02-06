# SENG 637 - Software Testing, Reliability, and Quality

### Lab. Report \#1 – Introduction to Testing and Defect Tracking

| Group 4      |
|-----------------|
| Zohara Kamal            |   
| Thanoshan Vijayanandan          |   
| Shuvam Agarwala               |   
| Minh Le              |   


## Table of Contents
1. [Introduction](#introduction)
2. [High-level description of the exploratory testing plan](#high-level-description-of-the-exploratory-testing-plan)
3. [Comparison of exploratory and manual functional testing](#comparison-of-exploratory-and-manual-functional-testing)
   - [Bug report](#bug-report)
4. [Notes and discussion of the peer reviews of defect reports](#notes-and-discussion-of-the-peer-reviews-of-defect-reports)
5. [How the pair testing was managed and team work/effort was divided](#how-the-pair-testing-was-managed-and-team-workeffort-was-divided)
6. [Difficulties encountered, challenges overcome, and lessons learned](#difficulties-encountered-challenges-overcome-and-lessons-learned)
7. [Comments/feedback on the lab and lab document itself](#commentsfeedback-on-the-lab-and-lab-document-itself)

# Introduction

This lab focuses on gaining practical experience in software testing and defect tracking using an ATM simulation system as the System Under Test (SUT). The main objective of the lab is to understand and apply different testing approaches, including exploratory testing, manual scripted (functional) testing, and regression testing. The ATM simulation system provides common banking operations such as deposits, withdrawals, transfers, and balance inquiries, which allows testers to evaluate both functional correctness and usability.

In this lab, we conduct exploratory and scripted tests on ATM System version 1.0, which is provided in the archive `/assignment1-artifacts.zip` under the file name `ATM System - Lab 1 Version 1.0.jar`. Any defects discovered during these testing phases are recorded in the Jira backlog.

After documenting the identified defects, regression testing is performed on the updated release of the application, ATM System version 1.1, also included in `/assignment1-artifacts.zip` as `ATM System - Lab 1 Version 1.1.jar`. The status of previously reported issues is then reviewed and updated in the Jira backlog based on whether the defects have been resolved or remain present.


# High-level description of the exploratory testing plan

Our exploratory testing plan focused on understanding the core functionalities of the ATM simulation system and identifying defects through unscripted interaction with the interface. The primary functions targeted during this phase were:

- Authentication (card number and PIN)
- Deposit
- Withdrawal
- Transfer between accounts
- Balance inquiry
- Transaction receipts/ logs
- Session termination and card ejection
- System on/off behavior
  
Our approach was broad-first then deep. We initially tested all major functions lightly to gain familiarity with the system. After that, we selected a few high-risk or complex functions (such as transfer and withdrawal) and tested them more extensively.
Test case ideas were derived from:

- Test typical user activities like successful login, regular deposits, withdrawals, transfers, and balance inquiries
- Explore what the user can potentially do when he visits the ATM, like pressing incorrect buttons or navigating menus in unusual orders
- After each transaction, verify account balances and system logs to ensure the operation was recorded accurately
- Review the generated receipt to confirm that all transaction details are correct and complete
- Evaluate boundary conditions (depositing $0, very large amounts ...)
- Exceptional paths (wrong PIN, negative numbers, cancel operations ...)
- Usability behaviors (pressing unexpected buttons, repeated inputs ...)

We also varied: Account types (Checking, Savings, Money Market)

The goal of this phase was not to cover every scenario, but to uncover unexpected behaviors, crashes, or inconsistencies without relying on predefined scripts.

# Comparison of exploratory and manual functional testing

Exploratory testing helped our team find many more bugs than scripted testing. This is because each team member used the program in their own creative and different ways. These different actions helped us discover problems that were not covered in the 40 scripted test cases. The biggest advantage of exploratory testing is freedom, we are not limited to fixed steps. It works especially well when scripted tests are not complete. In our case, the 40 provided scripted manual test cases were not enough to find most of the bugs.

However, exploratory testing also has downsides. It was hard to track our testing progress because nothing was planned in advance. Some bugs may have been missed. Sometimes we found a bug but could not reproduce it later because we did not record the exact steps.

Scripted testing is better for tracking progress and documenting bugs. The test steps are written clearly, so anyone can follow them and check if the program meets basic quality standards. Once scripted tests are created, they do not depend on the tester’s creativity since everyone follows the same instructions.

The disadvantage of scripted testing is that it depends on the imagination of the person who wrote the tests. If a test case is forgotten or not included, that problem might never be tested in future testing rounds.

To summarize:

| Aspect | Exploratory Testing | Scripted Testing |
|--------|---------------------|--------------------------------------|
| **Benefits** | • Encourages creativity and critical thinking<br>• Effective at finding unexpected defects<br>• Helps testers quickly learn the system | • Structured and repeatable<br>• Ensures requirement coverage<br>• Easier to verify expected behavior |
| **Trade-offs** | • Harder to reproduce issues consistently<br>• Coverage is less measurable<br>• Depends heavily on tester skill | • Limited creativity<br>• May miss unusual or hidden defects<br>• Time-consuming if the test suite is large |
| **Effectiveness** | High for discovering usability issues and edge-case bugs | High for confirming known requirements |
| **Efficiency** | Fast for initial defect discovery but less systematic | Good for verification but weaker at discovering new issues |


## Bug report from Jira Backlog

The bug report generated by export of Jira backlog issues: 

### Note 
After the regression tesing, we also found new bugs in system ATM 1.1 which are `CRM-49` and `CRM-50`. In adition, some of the defects that were detected in non-scripted and scripted testings are fixed but several of them are still in-progress (not fix yet)
   
# Notes and discussion of the peer reviews of defect reports
One interesting thing we noticed is that everyone has a different way of using the ATM program. This was very clear during exploratory testing, where each person found different bugs with very little overlap. For example, Thanoshan and Minh discovered that entering a negative deposit amount caused an incorrect message, while Zohara and Shuvam found that repeatedly pressing the cancel button sometimes froze the screen. It showed that each of us has a slightly unique testing style. 

Overall, we divided the peer review into two main parts: exploratory testing and scripted testing. For each part, one pair first looked at the other pair’s bug list and tried to reproduce the issues in the program. After that, we combined our findings and removed duplicate defects. We all met online as a group to discuss our feedback, especially the bugs that could not be reproduced. Communication was maintained through shared notes in Notion and backlog in Jira, and this division of work improved efficiency while allowing multiple perspectives when identifying defects.

We have multiple discussions and reviews. The review focused on:
- Whether reproduction steps were detailed and precise
- If expected vs. actual outcomes were clearly distinguished
- Proper classification of severity and priority
- Correct identification of SUT version
- Consistency in formatting and terminology in Jira backlog

We have some recommended improvement for the next assignment:
- Adding screenshots for all defects 
- Clarifying ambiguous reproduction steps
- Ensuring consistent naming of functions and accounts in Jira backlog

# How the pair testing was managed and team work/effort was divided 

The testing work was shared among the team using a collaborative approach.

**Exploratory Testing:**
First, we started by exploring the system to understand how it works. Based on that, we created a high-level test plan. Then, two pairs from our team tested the system separately and took notes. 

Within each pair, roles were rotated to ensure equal participation:
- Driver: Operated the ATM system and executed transactions.
- Observer: Documented test steps, outcomes, and logged defects.

Finally, each pair reviewed the issues they found and reported them in Jira and removed duplicates.

**Manual Scripted Testing:**
We completed this task in pairs, similar to the previous step. Shuvam Agarwala and Zohara Kamal executed test cases 1–20, while Minh Le and Thanoshan Vijayanandan performed test cases 21–40. After finishing the execution phase, each pair then focused on defect documentation and verification for the other pair’s results.

This approach ensured that all test cases were fully covered and also provided a second layer of review for accuracy. By cross-checking each other’s work, we reduced the chances of missing defects and confirmed that the system behavior matched the expected outcomes. It also helped maintain consistency in how defects were recorded and improved the overall reliability of our testing process.

**Regression Testing:**
Each team member who reported defects in the previous two phases retested the same test cases on version 1.1 and updated the defect status, while the other members reviewed.

As mentioned earlier, communication was maintained through shared Notion notes and Jira backlog. This division of work improved efficiency and allowed multiple perspectives when identifying defects.

# Difficulties encountered, challenges overcome, and lessons learned

Since we conducted exploratory testing individually from remote locations, each team member reported a similar set of defects. Although we checked for existing defects before creating new ones to reduce duplication, some duplicate reports were still created. Removing these duplicates was challenging because the same issues were described using different titles and descriptions. To resolve this, we met in person at the university, discussed the reported defects, and removed the duplicates. In addition, some issues appeared intermittently, making them hard to reproduce consistently during testing.

Some reported defects were also not reproducible, so we retested them together and removed the invalid reports.

Another challenge was reporting defects in a clear and consistent way. To address this, we created a bug template in Jira. This allowed us to follow the same format whenever a new bug was reported, ensuring consistency across all defect reports.

Moreover, understanding certain user interface behaviors was challenged due to the lack of detailed documentation, which made it harder to determine whether some behaviors were intended or defects.

This experience showed us how important teamwork is. Everyone must be aligned on what needs to be done and understand how their efforts fit into the group's work.

# Comments/feedback on the lab and lab document itself
1. The detailed and comprehensive assignment document (seng637-a1.md) helped us clearly understand and complete the required tasks.
2. Through this assignment (The SUT chosen for this assignmen), we gained hands-on experience in key testing activities used in the software industry. Further, the selected system was appropriate because it allowed us to perform all three types of testing in sequence. It effectively demonstrated the differences between exploratory, scripted, and regression testing. It was simple enough to be understood by anyone, yet it had plenty of bugs to be discovered.
4. Backlog was used as a tool for reporting and managing bugs. In our opinion, it was perfect for this assignment. Now we are familiar with these issue tracking tools.

Overall, the lab was practical and valuable for learning defect tracking and teamwork in software testing. Adding more example bug reports or a short demo video could further improve clarity for future students.



