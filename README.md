# SENG 637 - Software Testing, Reliability, and Quality

### Lab. Report \#1 – Introduction to Testing and Defect Tracking

| Group 4      |
|-----------------|
| Zohara Kamal            |   
| Thanoshan Vijayanandan          |   
| Minh Le                |   
| Shuvam Agarwala              |   


## Table of Contents
1. [Introduction](#introduction)
2. [High-level description of the exploratory testing plan](#high-level-description-of-the-exploratory-testing-plan)
3. [Comparison of exploratory and manual functional testing](#comparison-of-exploratory-and-manual-functional-testing)
4. [Bug report from Jira Backlog](#bug-report-from-jira-backlog)
5. [Notes and discussion of the peer reviews of defect reports](#notes-and-discussion-of-the-peer-reviews-of-defect-reports)
6. [How the pair testing was managed and team work/effort was divided](#how-the-pair-testing-was-managed-and-team-workeffort-was-divided)
7. [Difficulties encountered, challenges overcome, and lessons learned](#difficulties-encountered-challenges-overcome-and-lessons-learned)
8. [Comments/feedback on the lab and lab document itself](#commentsfeedback-on-the-lab-and-lab-document-itself)

# Introduction

This lab focuses on gaining practical experience in software testing and defect tracking using an ATM simulation system as the System Under Test (SUT). The main objective of the lab is to understand and apply different testing approaches, including exploratory testing, manual scripted (functional) testing, and regression testing. The ATM simulation system provides common banking operations such as deposits, withdrawals, transfers, and balance inquiries, which allows testers to evaluate both functional correctness and usability.

In this lab, we conduct exploratory and scripted tests on ATM System version 1.0, which is provided in the archive `/Assignment 1 - artifacts.zip` under the file name `ATM System - Lab 1 Version 1.0.jar`. Any defects discovered during these testing phases are recorded in the Jira backlog.

After documenting the identified defects, regression testing is performed on the updated release of the application, ATM System version 1.1, also included in `/Assignment 1 - artifacts.zip` as `ATM System - Lab 1 Version 1.1.jar`. The status of previously reported issues is then reviewed and updated in the Jira backlog based on whether the defects have been resolved or remain present.


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

Exploratory testing enabled our team to identify significantly more defects than scripted testing. This was largely because each team member interacted with the application in unique and creative ways, exploring workflows and edge cases that were not covered by the 40 scripted test cases. A key strength of exploratory testing is its flexibility: testers are not constrained by predefined steps, which makes it especially effective when scripted coverage is incomplete. In our case, the provided scripted manual test cases were insufficient to uncover many of the issues we ultimately found.

However, exploratory testing also has limitations. Because sessions are not fully planned in advance, it can be difficult to track overall progress and confirm coverage across features. This approach also increases the risk of missing defects, and some issues can be challenging to reproduce if exact steps, inputs, and environment conditions are not documented at the time of discovery.

In contrast, scripted testing is well suited for monitoring progress, ensuring consistent coverage, and supporting repeatability. Clearly defined steps make it easy for any tester to execute the same tests and verify that the application meets baseline quality expectations. Once established, scripted tests are less dependent on individual tester creativity because execution follows a standardized process.

The main drawback of scripted testing is that its effectiveness depends on the completeness and foresight of the test design. If important scenarios are overlooked or not included in the test suite, those areas may remain untested in future cycles, allowing defects to persist undetected.


To summarize:

| Aspect | Exploratory Testing | Scripted Testing |
|--------|---------------------|--------------------------------------|
| **Benefits** | • Encourages creativity and critical thinking<br>• Effective at finding unexpected defects<br>• Helps testers quickly learn the system | • Structured and repeatable<br>• Ensures requirement coverage<br>• Easier to verify expected behavior |
| **Trade-offs** | • Harder to reproduce issues consistently<br>• Coverage is less measurable<br>• Depends heavily on tester skill | • Limited creativity<br>• May miss unusual or hidden defects<br>• Time-consuming if the test suite is large |
| **Effectiveness** | High for discovering usability issues and edge-case bugs | High for confirming known requirements |
| **Efficiency** | Fast for initial defect discovery but less systematic | Good for verification but weaker at discovering new issues |


# Bug report from Jira Backlog

The bug report generated by export of Jira backlog issues: [`./Defect_report_backlog.csv`](https://github.com/SENG637-Group-4/Assignment-1/blob/main/Defect_report_backlog.xlsx)

### Note 
After exploratory and scripted tesing, we found 32 bugs in the system ATM 1.0.

After the regression tesing, we also found new  2 bugs in the system ATM 1.1 which are `CRM-49` and `CRM-50`. In adition, some of the defects that were detected in non-scripted and scripted testings are fixed but several of them are still in-progress (not fix yet)

Overall, we have 34 defects in the Jira backlog.

<img width="1241" height="700" alt="image" src="https://github.com/user-attachments/assets/dff78c6b-d69a-44c4-a8ac-2441209d179c" />

<img width="1241" height="700" alt="image" src="https://github.com/user-attachments/assets/18af28fa-86b2-4844-811f-caa631b55c2b" />


   
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
We completed this task in two pairs, similar to the previous step.

Within each pair, roles were rotated to ensure equal participation:
- Driver: Operated the ATM system and executed system under test.
- Observer: Documented test steps, outcomes, and logged defects.

Shuvam Agarwala and Zohara Kamal executed test cases 1–20, while Minh Le and Thanoshan Vijayanandan performed test cases 21–40. After finishing the execution phase, each pair then focused on defect documentation and verification for the other pair’s results.

This approach ensured that all test cases were fully covered and also provided a second layer of review for accuracy. By cross-checking each other’s work, we reduced the chances of missing defects and confirmed that the system behavior matched the expected outcomes. It also helped maintain consistency in how defects were recorded and improved the overall reliability of our testing process.

**Regression Testing:**
Each team member who reported defects in the previous two phases retested the same test cases on version 1.1 and updated the defect status, while the other members reviewed.

As mentioned earlier, communication was maintained through shared Notion notes and Jira backlog. This division of work improved efficiency and allowed multiple perspectives when identifying defects.

# Difficulties encountered, challenges overcome, and lessons learned

Since we conducted exploratory testing individually from remote locations, multiple team members identified many of the same defects. Although we reviewed existing tickets before logging new ones to minimize duplication, some duplicate reports were still created because similar issues were documented with different titles and descriptions. To address this, we met in person at the university to review the defect list, consolidate overlapping tickets, and remove duplicates.

We also encountered intermittent issues that were difficult to reproduce reliably. In addition, some reported defects were not reproducible, so we retested them as a group and closed the invalid reports.

Another challenge was ensuring defect reports were clear and consistent. To improve quality and standardize reporting, we created a Jira bug template and used it for all new tickets. This helped ensure every report followed the same structure and included the required details.

Finally, limited documentation made it harder to interpret certain user interface behaviors and determine whether they were expected features or true defects.

Overall, this experience reinforced the importance of collaboration and alignment within the team, both for maintaining a clean defect backlog and for ensuring everyone’s efforts contribute effectively to shared project goals.


# Comments/feedback on the lab and lab document itself
1. The detailed and comprehensive assignment document (seng637-a1.md) helped us clearly understand and complete the required tasks.
2. Through this assignment (The SUT chosen for this assignmen), we gained hands-on experience in key testing activities used in the software industry. Further, the selected system was appropriate because it allowed us to perform all three types of testing in sequence. It effectively demonstrated the differences between exploratory, scripted, and regression testing. It was simple enough to be understood by anyone, yet it had plenty of bugs to be discovered.
4. Backlog was used as a tool for reporting and managing bugs. In our opinion, it was perfect for this assignment. Now we are familiar with these issue tracking tools. And we also know about the logs of tracking system.

Overall, the lab was practical and valuable for learning defect tracking and teamwork in software testing. Adding more example bug reports or a short demo video could further improve clarity for future students.



