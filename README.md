# SENG 637 - Software Testing, Reliability, and Quality

### Lab. Report \#1 – Introduction to Testing and Defect Tracking

| Group Number      |
|-----------------|
| Zohara Kamal            |   
| Thanoshan Vijayanandan          |   
| Shuvam Agarwala               |   
| Minh Le              |   


**Table of Contents**

(When you finish writing, update the following list using right click, then
“Update Field”)

[1 Introduction	1](#_Toc439194677)



[2 High-level description of the exploratory testing plan	1](#_Toc439194678)


[3 Comparison of exploratory and manual functional testing	1](#_Toc439194679)

[4 Notes and discussion of the peer reviews of defect reports	1](#_Toc439194680)

[5 How the pair testing was managed and team work/effort was
divided	1](#_Toc439194681)

[6 Difficulties encountered, challenges overcome, and lessons
learned	1](#_Toc439194682)

[7 Comments/feedback on the lab and lab document itself	1](#_Toc439194683)

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

Exploratory testing helped our team find many more bugs than scripted testing. This is because each team member used the program in their own creative and different ways. These different actions helped us discover problems that were not covered in the 40 scripted test cases. The biggest advantage of exploratory testing is freedom, we are not limited to fixed steps. It works especially well when scripted tests are not complete. In our case, the 40 manual test cases were not enough to find most of the bugs.

However, exploratory testing also has downsides. It was hard to track our testing progress because nothing was planned in advance. Some bugs may have been missed. Sometimes we found a bug but could not reproduce it later because we did not record the exact steps.

Scripted testing is better for tracking progress and documenting bugs. The test steps are written clearly, so anyone can follow them and check if the program meets basic quality standards. Once scripted tests are created, they do not depend on the tester’s creativity since everyone follows the same instructions.

The disadvantage of scripted testing is that it depends on the imagination of the person who wrote the tests. If a test case is forgotten or not included, that problem might never be tested in future testing rounds.

## Bug report

The bug report generated by export of Jira backlog issues:
   
# Notes and discussion of the peer reviews of defect reports

Our group’s peer review involved two pairs checking each other’s results from both exploratory testing and scripted testing. One interesting thing we noticed is that everyone has a different way of using the ATM program. This was very clear during exploratory testing, where each person found different bugs with very little overlap. It showed that each of us has a slightly unique testing style.

We divided the peer review into two main parts: exploratory testing and scripted testing. For each part, one pair first looked at the other pair’s bug list and tried to reproduce the issues in the program. After that, we all met online as a group to talk about our feedback, especially the bugs that could not be reproduced. These discussions gave us useful insights, such as differences in display settings between team members.

For example, some members could not reproduce the issue where the word “transaction” was cut off on the screen. After discussing it together, we realized the problem was caused by different screen resolutions and display scaling. Some members used higher or lower resolutions, which explained why the bug only appeared for certain people.

# How the pair testing was managed and team work/effort was divided 

The testing work was shared among the team using a collaborative approach.

**Exploratory Testing:**
First, we started by exploring the system to understand how it works. Based on that, we created a high-level test plan. Then, two pairs from our team tested the system separately and took notes. Finally, each pair reviewed the issues they found and reported them in Jira.

**Manual Scripted Testing:**
We completed this task as a team. Each team member executed 10 test cases, while the other members tracked the completed tests and reported any defects. Shuvam Agarwala executed test cases 1–10, followed by Zohara Kamal (11–20), Minh Le (21–30), and Thanoshan Vijayanandan (31–40).

**Regression Testing:**
We completed this task as a group. Each team member who reported defects in the previous two phases retested the same test cases on version 1.1 and updated the defect status, while the other members reviewed.

# Difficulties encountered, challenges overcome, and lessons learned

Since we conducted exploratory testing individually from remote locations, each team member reported a similar set of defects. Although we checked for existing defects before creating new ones to reduce duplication, some duplicate reports were still created. Removing these duplicates was challenging because the same issues were described using different titles and descriptions. To resolve this, we met in person at the university, discussed the reported defects, and removed the duplicates.

Some reported defects were also not reproducible, so we retested them together and removed the invalid reports.

Another challenge was reporting defects in a clear and consistent way. To address this, we created a bug template in Jira. This allowed us to follow the same format whenever a new bug was reported, ensuring consistency across all defect reports.

This experience showed us how important teamwork is. Everyone must be aligned on what needs to be done and understand how their efforts fit into the group's work.

# Comments/feedback on the lab and lab document itself

1. The detailed and comprehensive assignment document (seng637-a1.md) helped us clearly understand and complete the required tasks.
2. Through this assignment, we gained hands-on experience in key testing activities used in the software industry. Further, the selected system was appropriate because it allowed us to perform all three types of testing in sequence.

