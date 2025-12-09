# Excel Bikes Sales Dashboard

This project analyzes bike customer data using the six-step Google Data Analytics process: Ask, Prepare, Process, Analyze, Share, and Act. To identify key trends and uncover insights that help make smarter decisions based on customer preferences and sales behavior.

# Project Skills 

• Cleaning and preparing raw data. • Data transformation • Filtering, sorting, and Excel functions (VLOOKUP, IF, Find and Replace) • Pivot Tables and Pivot Charts • Data visualization and dashboard creation • Analyzing purchase trends

# Business Task

Build an interactive sales dashboard to showcase bike sales and analyze results to identify sales trends.

# 1. Ask

• Which age group buys the most bikes?

• Do men or women purchase more bikes?

• Which commute distance has the most bike buyers?

# 2. Prepare

Starting Dataset: [Excel Project Dataset.xlsx](https://github.com/user-attachments/files/24042478/Excel.Project.Dataset.xlsx) raw dataset containing detailed bike customer details.

In Excel, 1 sheet is included in the dataset: bike_buyers

<img width="950" height="428" alt="Screenshot 2025-12-08 at 5 35 00 PM" src="https://github.com/user-attachments/assets/e5c93d23-bbdf-41db-8560-a021aa7c9607" />

# 3. Process 

I began by creating three new sheets in Excel: Working Sheet, Pivot Table, and Dashboard.

Next, I copied the original bike_buyers dataset into the Working Sheet to keep the source data intact.

After that, I reviewed the dataset to understand the fields available and identify what could be analyzed.

# Checking For Duplicate Values

I began by checking the dataset for duplicate entries. To do this, I selected the entire sheet, went to the Data tab, and used the Remove Duplicates feature. I selected all columns to ensure a full check across the dataset, which resulted in 26 duplicate values being removed.

<img width="1004" height="663" alt="Screenshot 2025-12-08 at 6 41 09 PM" src="https://github.com/user-attachments/assets/6c60c03e-4622-417e-86cf-cf959ca4ad71" />

# Find and Replace

The Marital Status and Gender columns use single-letter codes, which aren’t necessarily wrong, but they may be unclear to someone viewing the final dashboard. For example, a user might not immediately understand what “M” or “S” represents for marital status. To make the data more user-friendly and improve dashboard readability, I decided to replace these one-letter values with the full words.

To make this change, I started by selecting the entire Marital Status column (Column B) and using the Ctrl + H shortcut to open the Find and Replace tool.

Since both Column B and Column C contain the letter “M,” it’s important to note that they represent different meanings. In the Marital Status column (B), “M” means “Married,” while in the Gender column (C), “M” means “Male.” This means each column needs to be updated separately to avoid replacing the wrong values. To ensure accuracy, I opened the Options menu in the Find and Replace window and selected Search by Column and Match Case so that only the correct “M” values were replaced. Then selected Replace All.

<img width="764" height="403" alt="Screenshot 2025-12-08 at 7 01 11 PM" src="https://github.com/user-attachments/assets/3123d08b-7b83-479b-8048-dabc76065fda" />


After updating the “M” values, I repeated the same process for the letter “S” in Column B, replacing it with “Single.”

I then moved over to Column C and updated the Gender values by replacing “F” with “Female” and “M” with “Male.”

<img width="954" height="343" alt="Screenshot 2025-12-08 at 7 06 04 PM" src="https://github.com/user-attachments/assets/ce33cdfe-b68d-4692-a4a2-1b54c5db4f04" />

# Age Brackets 

There are many different age values in the dataset, so grouping them will make the information easier to understand. To simplify the analysis, I created a new column to categorize each person into an age group, which will be used later in the dashboard for clearer insights.

To the right of the Age column, I created a new column named Age Bracket.
I used an IF statement to classify each age by checking whether it falls above or below specific ranges. This allowed me to automatically assign the correct age bracket to each person.

To create the first age group (under 31), I used the formula: =IF(L3<31,"Adolescent","Invalid")

This returned “Adolescent” for anyone younger than 31 and “Invalid” for everyone outside that range, which confirmed the formula was working correctly before building the remaining brackets. 

# Building a Nested IF statement 

I then added an additional IF statement in front of the original formula to include a “Middle Age” category for anyone aged 31 or older. This allowed me to begin building multiple age ranges within a single nested IF formula.

To create the second age group (31 or older), I used: =IF(L2>=31,"Middle Age", IF(L2<31,"Adolescent","Invalid"))

Next, I created a third and final age group, “Old,” for anyone older than 54. To do this, I expanded the nested IF statement again.

For the final age group (54 or older), I used: =IF(L2>54, "Old", IF(L2>=31,"Middle Age", IF(L2<31,"Adolescent","Invalid")))

<img width="907" height="506" alt="Screenshot 2025-12-08 at 7 45 46 PM" src="https://github.com/user-attachments/assets/7e8349da-744c-48de-a328-0d2f60bbee98" />


