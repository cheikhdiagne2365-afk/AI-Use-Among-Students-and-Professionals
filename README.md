# AI-Use-Among-Students-and-Professionals
Data Analysis and Visualization project to determine the use, impact and effectiveness of AI among a population of students and working professionals.

Original Database: https://www.kaggle.com/datasets/eishatuzzuhra/ai-usage-and-impact-on-students-and-professionals

## Columns
- User_ID
- Age
- Gender
- Country
- User_Type
- Education_Level
- Profession
- Monthly_Income
- AI_Tool
- AI_Purpose
- AI_Usage_Hours_Per_Day
- Tasks_Performed
- Monthly_AI_Cost
- Productivity_Score
- Accuracy_Rating
- Satisfaction_Score
- Time_Saved_Hours_Per_Week
- Work_or_Study_Hours_Per_Day
- Would_Recommend

## Database Cleaning Process
Before conducting our analysis, we need to undergo a cleaning process to the original database. This will allow us to maximize the accuracy of the data analysis and visualization process. The cleaning of the data will be done using PowerQuery on Microsoft Excel.

### Steps
1. Change the column type of the "Age" column from Text to Number
2. Change the column type of the "Monthly_Income" from Text to Currency
3. Capitalize each word in the columns: Country, Gender and AI_Tool
4. In the "Gender" column, use find and replace to substitute every occurence of "F" with "Female" and "M" with "Male"
5. In the "Country" column, replace every occurence of "U.K." with "United Kingdom" and "United States of America" with "United States"
6. In the "Education_Level" column, remove every occurence of "'s"
7. Remove any row that contains an error or a null tag
8. Remove any duplicate rows
9. Remove any row that contain an empty cell
   ```
   Table.SelectRows(#"[Name_of_Previous_Step]", each not List.AnyTrue(List.Transform(Record.FieldValues(_), each _ = null or _ = "")))
   ```
10. In the "AI_Tool" column, replace every occurence of "Ai" with "AI", "Chatgpt" with "ChatGPT" and "Chat gpt" with "ChatGPT"
11. In the "Education_Level" column, perform these listed replacements:
    - BA/BSc —> Bachelor
    - MA/MSc —> Master
    - Ph.D. —> PhD
    - Masters —> Master
    - master degree —> Master
    - undergrad —> Undergraduate
    - Bachelors —> Bachelor
    - Diploma —> Other
12. For the "AI_Usage_Hours_Per_Day", "Time_Saved_Hours_Per_Week" and "Work_or_Study_Hours_Per_Week" columns, remove every occurence of "hrs"
13. For the same columns as step 11, change the column type from Text to Decimal
14. For the "Tasks_Performed" column, translate any cell content that isn't written in English
