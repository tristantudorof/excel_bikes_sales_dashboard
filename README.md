# Excel Bikes Sales Dashboard

This project analyzes bike customer data using the six-step Google Data Analytics process: Ask, Prepare, Process, Analyze, Share, and Act. To identify key trends and uncover insights that help make smarter decisions based on customer preferences and sales behavior.


# The Finished Dashboard

<img width="882" height="623" alt="Screenshot 2025-12-08 at 11 29 13 PM" src="https://github.com/user-attachments/assets/86e0b379-d93a-4b0a-a064-3c643195a030" />

Download Finished Dashboard and Excel sheets: [Excel Bike Project Dataset Finished.xlsx](https://github.com/user-attachments/files/24046342/Excel.Bike.Project.Dataset.Finished.xlsx)



# Project Skills 

• Cleaning and preparing raw data. • Data transformation • Filtering, sorting, and Excel functions (IF, Find and Replace) • Pivot Tables and Pivot Charts • Data visualization and dashboard creation • Analyzing purchase trends

# Business Task

Build an interactive sales dashboard to showcase bike sales and analyze results to identify sales trends.

# 1. Ask

• Which age group buys the most bikes?

• Do men or women purchase more bikes?

• Which commute distance has the most bike buyers?

# 2. Prepare

Starting Raw Dataset: [Excel Project Dataset.xlsx](https://github.com/user-attachments/files/24042478/Excel.Project.Dataset.xlsx) raw dataset containing detailed bike customer details.

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

I now have three different age groups, which are much more useful for the finished dashboard and overall analysis.

I noticed that using Find and Replace to change the “M” and “S” values also altered the column header, so I went back and quickly corrected the column name.

<img width="206" height="75" alt="Screenshot 2025-12-08 at 7 51 12 PM" src="https://github.com/user-attachments/assets/22e9bb30-1d2f-475a-bce7-9f4fa9837f39" />

# 4. Analyze 

Pivot tables are essential for the analysis stage of this project because they allow me to quickly summarize and explore the dataset. Using pivot tables, I can condense large amounts of data into clear totals, counts, and averages, making trends and patterns much easier to identify. They also allow me to break the data down by different categories—such as age group, gender, region, or marital status—to compare how each group relates to bike purchases. In addition, pivot tables make it easy to filter, rearrange, and drill deeper into the data without altering the original dataset. These insights form the foundation for the visualizations and dashboard I build later in the process.

# Pivot Table

Inserting a Pivot Table

Insert → Pivot Table → Range: "Table1"  → OK

The first thing I wanted to analyze was the average income of customers who purchased a bike compared to those who did not. This helps reveal whether income level plays a role in bike buying behavior and provides an early insight into potential customer segments.

I pulled Income into the Values area and Gender into the Rows area of the pivot table. I then changed the Income calculation from Sum to Average so I could compare the average income for each group. After that, I added Purchased Bike to the Columns area to see how the average income differs between customers who bought a bike and those who did not.

<img width="380" height="132" alt="Screenshot 2025-12-08 at 8 35 22 PM" src="https://github.com/user-attachments/assets/b89d453c-4e66-4700-8c70-14b2fdd05a3e" />

From this pivot table, I can see that customers who did not buy a bike generally had lower incomes, while those who did purchase a bike had higher incomes overall. I also noticed that men had higher average incomes compared to women across both groups.

After building the pivot table, I inserted a 2D Column Chart (Insert → 2D Column Chart) to visualize the relationship between gender, income, and bike purchases. I then added clear chart titles to make the visualization easy to understand for the final dashboard. To improve readability, I also added a Data Table below the chart to display the exact values used in the visualization. After that, I formatted the income values to remove decimal places, helping the chart appear cleaner, more consistent, and more professional.

<img width="781" height="533" alt="Screenshot 2025-12-08 at 9 28 15 PM" src="https://github.com/user-attachments/assets/68fbbf89-79fd-4320-9a26-ec9e135c02cd" />

Next, I wanted to analyze the commute distance of customers. Understanding whether bike buyers live just a few miles from work or much farther away helps reveal whether commuting habits influence the likelihood of purchasing a bike.

I inserted an additional pivot table below the first one so I could analyze commute distance separately without affecting my earlier calculations.

To analyze how commute distance relates to bike purchases, I built a second pivot table. I dragged Commute Distance into the Rows area so each distance category appears as its own row. Then I placed Purchased Bike into the Columns area to split the results into “Yes” and “No” buyers. Finally, I added Purchased Bike again into the Values area, this time set as Count of Purchased Bike, so the pivot table counts how many people in each commute distance group purchased a bike versus not.

This setup lets me easily compare buying behavior across different commute distances.

<img width="331" height="157" alt="Screenshot 2025-12-08 at 9 40 02 PM" src="https://github.com/user-attachments/assets/6cf8e07c-e8dc-4f7c-96c6-bb967ec0735f" />

I noticed that “10+ miles” was appearing third in the pivot table instead of at the bottom, which would distort the order of my chart. Since filtering and sorting didn’t resolve it, I went back to the working sheet and used Find and Replace to rename “10+ miles” to “More than 10 miles.” This ensures Excel treats it as text that naturally appears at the end of the list, keeping both the pivot table and the chart in the correct logical order.

<img width="822" height="458" alt="Screenshot 2025-12-08 at 9 44 57 PM" src="https://github.com/user-attachments/assets/d314c7cb-8336-4459-b368-d2fe8a032abe" />

I then refreshed the pivot table, and the updated label successfully moved to the bottom of the list.

<img width="392" height="177" alt="Screenshot 2025-12-08 at 9 45 39 PM" src="https://github.com/user-attachments/assets/a3eb145c-21f1-4f1a-b2c7-5440281e5969" />

I then inserted a 2D Line Chart and added both axis titles and a clear chart title to make the visualization easy to interpret.

<img width="594" height="346" alt="Screenshot 2025-12-08 at 9 51 40 PM" src="https://github.com/user-attachments/assets/12ad388e-af3e-4c37-88f1-3a742a656847" />

I then moved on to my last pivot table. For this one, I wanted to analyze my Age Brackets, see who purchased the bike, and view the count of purchases. I selected Age Brackets and Purchased Bike from the field list, then placed Age Brackets in the Rows area so each bracket appears as its own category. I added Purchased Bike to the Columns area to separate results into “Yes” and “No,” and dragged Purchased Bike into the Values area to count how many people in each age bracket purchased a bike versus did not. This setup lets me clearly compare bike-buying behavior across different age groups.

<img width="334" height="121" alt="Screenshot 2025-12-08 at 9 55 22 PM" src="https://github.com/user-attachments/assets/473e73e6-d317-44e9-9092-6005e0424918" />

After setting up the pivot table, I inserted a 2D line chart with markers to visualize the purchasing trends across the age brackets. I then added a chart title and axis titles to clearly label what the chart represents, making the visualization easier to read and more professional.

<img width="394" height="236" alt="Screenshot 2025-12-08 at 10 00 05 PM" src="https://github.com/user-attachments/assets/98f8b6a3-4ce3-4363-9995-2a54143d4f01" />

I then went back to the working sheet to improve the clarity of the age bracket labels. Using Find and Replace, I updated the formula so it returned more descriptive groups: 0–30 (Adolescent), 31–54 (Middle Age), and 55+ (Old). These clearer labels make the pivot table and final charts easier to understand and provide more meaningful insights when analyzing purchasing behavior across different age groups. And refreshed the data on the Pivot Table page.

<img width="838" height="286" alt="Screenshot 2025-12-08 at 10 10 48 PM" src="https://github.com/user-attachments/assets/4bfb08fb-07fd-443a-927c-41e0862debde" />

However, updating the labels changed the alphabetical order of the age groups in my pivot table, which disrupted the order of my chart. Since this affected the readability of the visualization, I decided to undo the changes and keep the original age bracket labels to maintain the correct order.

With all three pivot tables and charts finalized and cleaned, I am now ready to begin building my dashboard.

# Dashboard

I then copied and pasted all three charts from the Pivot Table sheet into the Dashboard sheet. This allowed me to organize the visuals in one place and begin structuring the final layout of the dashboard.

<img width="1057" height="619" alt="Screenshot 2025-12-08 at 10 18 09 PM" src="https://github.com/user-attachments/assets/8e0145a9-f2e4-4a79-bf28-6057be653b21" />

I added a shape to the top of the Dashboard sheet and used it as a header section. I filled it with a background color and added the title “Bike Sales Dashboard.” After that, I aligned and positioned all three charts in a visually appealing layout to create a clear and organized dashboard.

Next, I wanted to make the dashboard interactive, so I added filters to the charts. To do this, I went to PivotChart Analyze and inserted Slicers, which allow users to filter the dashboard by specific categories with a single click.

<img width="965" height="477" alt="Screenshot 2025-12-08 at 10 38 21 PM" src="https://github.com/user-attachments/assets/cfb8ee61-60c3-4822-8176-73a759b2dbd2" />

To make the slicer work on all the charts, I selected the slicer and opened Report Connections, then checked all three pivot tables. This made every chart update together when I use the slicer.

<img width="1057" height="383" alt="Screenshot 2025-12-08 at 10 40 54 PM" src="https://github.com/user-attachments/assets/34d90167-edaf-4aa8-b0e2-b458b23783cf" />

I then added more slicers for Region and Education, and connected each one to all three pivot tables so the entire dashboard updates when any filter is used.

# 5. Share

# The Finished Dashboard

<img width="882" height="623" alt="Screenshot 2025-12-08 at 11 29 13 PM" src="https://github.com/user-attachments/assets/86e0b379-d93a-4b0a-a064-3c643195a030" />

Download Finished Dashboard and Excel sheets: [Excel Bike Project Dataset Finished.xlsx](https://github.com/user-attachments/files/24045883/Excel.Bike.Project.Dataset.Finished.xlsx)

# 6. Act

# 1. Age Group Purchases

Adolescent (0–30): Lowest number of bike purchases overall.
Middle Age (31–54): Highest number of purchases, making this the strongest buying group.
Old (55+): Moderate purchase activity but significantly lower than middle-aged customers.

Insight: The 31–54 age group drives the majority of bike sales, making them the primary target audience.

# 2. Gender Purchases

Female: Lower purchase counts compared to males.
Male: Higher purchase counts and higher average income, contributing more to overall bike sales.

Insight: Men purchase more bikes than women, indicating stronger engagement from male customers.

# 3. Commute Distance Purchases

0–1 Miles: Highest number of bike buyers.
1–2 Miles / 2–5 Miles: Moderate but declining purchase levels.
5–10 Miles: Higher non-buyer counts compared to buyers.
More than 10 Miles: Lowest purchase numbers.

Insight: Short-distance commuters (0–1 miles) are the most likely to buy bikes, suggesting convenience plays a major role in purchase decisions.

# Market Opportunity Breakdown

Overall, the market shows its strongest opportunity in middle-age buyers, high-income male customers, and short-distance commuters—three segments with clear purchase intent and strong alignment with practical, lifestyle-driven bike use.

# High-Performing Segment: Middle-Age Customers (31–54)

Middle-age customers represent the largest and most consistent group of bike buyers across the dashboard. They show strong engagement and the highest count of purchases.

Business Proposals:
• Develop targeted marketing campaigns focused on health, commuting convenience, and lifestyle benefits.
• Introduce mid-range and premium bike packages tailored to this demographic.
• Create retention strategies (warranty upgrades, service discounts) to strengthen long-term customer value.

# Growth Opportunity: Male Customers

Male customers demonstrate stronger purchasing activity and higher average incomes, especially among those who buy bikes. This indicates clear potential for expanding high-value sales.

Business Proposals:
• Promote performance and feature-driven models that appeal to higher-income male buyers.
• Offer premium add-ons (gear bundles, accessories, maintenance plans).
• Run targeted digital ads focusing on lifestyle improvement and convenience.

# Emerging Segment: Short-Distance Commuters (0–1 Mile)

Bike purchases are highest among customers with short commutes, suggesting strong practicality-driven demand. While this group is smaller than age or gender segments, it shows clear behavioral alignment with bike ownership.

Business Proposals:
• Position bikes as the ideal solution for quick, cost-effective daily travel.
• Create commuter-focused bundles (helmets, locks, lights, panniers).
• Partner with local employers or city programs to promote bike-to-work initiatives.

# Business Impact

The dashboard gives decision makers a clear understanding of who buys bikes, what motivates their purchases, and which customer segments deliver the strongest opportunities. These insights support more effective marketing, targeted product offerings, and focused retention strategies ultimately helping increase sales, strengthen customer loyalty, and guide smarter, data driven planning.

# Conclusion

The bike sales analysis highlights clear customer patterns—middle-age buyers, male customers, and short-distance commuters consistently drive the highest purchase activity. Understanding these trends allows the business to tailor marketing, product offerings, and engagement strategies to the segments most likely to convert, ultimately supporting stronger sales and more targeted growth.

# Thank You

Thank you for your interest and time. Feel free to give your valuable suggestions and connect with me on [LinkedIn](https://www.linkedin.com/in/tristan-tudorof/)




