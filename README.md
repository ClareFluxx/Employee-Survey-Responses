# Employee-Survey-Responses

![Introduction](Employee-survey-introduction.jpg)

## Objectives

This project analyses employee engagement survey data to uncover trends, department-wise engagement levels, and key factor affceting work place satisfaction. The goal is to provide data driven insights to help the organization improve employee engagement.

## Tools Used
- Power BI(For data visualization and dashboard creation)
- Power Query(For data cleaning and transformation)
- DAX

## Dataset Overview

#### Data Source
The Employee Survey Responses Dataset consists of:
- 14,725 Total Responses
- 21 Departments
- 11 Questions
- Overall Agreement Score of 2.96

#### Data Cleaning Process
Some of the key steps used to clean this data in power query includes:
- Removed null values
- Standardized column names
- Ensured correct data format

## Problem Statement

1. Which survey questions did respondents agree with or disagree with most?
2. Do you see any patterns or trends by department or role?
3. As an employer, what steps might you take to improve employee satisfaction based on the survey results?
4. What is the total agreement to disagreement percentage?

## DAX Used

The following DAX measures were used to calculate key metrics within the dataset:
- Agreement % = DIVIDE([Total Agreement],[Total Response],0)
- Agreement % Per Dept = DIVIDE([Total Agreement Per Dept],[Total Response Per Dept],0)
- Agreement Score Per Question = AVERAGE('HR Survey Reponses'[Response])
- Disagreement % = DIVIDE([Total Disagreement],[Total Response],0)
- Total Agreement = CALCULATE(COUNT('HR Survey Reponses'[Response ID]),'HR Survey Reponses'[Response Text] IN {"Agree","Strongly Agree"})
- Total Agreement Per Dept = CALCULATE(COUNTROWS('HR Survey Reponses'),'HR Survey Reponses'[Response Text] IN {"Agree","Strongly Agree"},ALLEXCEPT('HR Survey Reponses','HR Survey Reponses'[Department]))
- Total Disagreement = CALCULATE(COUNTROWS('HR Survey Reponses'),'HR Survey Reponses'[Response Text] IN {"Disagree","Strongly Disagree"})
- Total Response = COUNT('HR Survey Reponses'[Response ID])
- Total Response Per Dept = CALCULATE(COUNTROWS('HR Survey Reponses'),ALLEXCEPT('HR Survey Reponses','HR Survey Reponses'[Department]))

## Key Insights From Analysis

![Dashboard](Employee-survey-dashboard.PNG)

- #### Which survey questions did respondents agree with or disagree with most?
  
  ![Agreement-Disagreement-By-Question](Agreement-disagreement-by-question.PNG)

  - Top 4 Most Agreed Questions
  1. "I know what is expected of me at work" 91% agreement
  2. "My Supervisor or someone at work cares about me as a person" 85% agreement
  3. "My department encourages a positive work environment" 80% agreement
  4. "At work, i have the opportunity to do what i do best everyday" 79% agreement

  ![Top-4-most-and-least-agreed-questions](Top-4-most-and-least-agreed-questions.PNG)

  - Top 4 Least Agreed Questions
  1. "I have a best friend at work." 41% disagreement
  2. "In the last seven days, I have received recognition for good work." 34% disagreement
  3. "My supervisor provides me with regular feedback." 23% disagreement
  4. "Overall, I am satisfied with my job" 23% disagreement

- #### Do you see any patterns or trends by department or role?
  
  ![Department-Role-Agreement](department-role-agreement.PNG)

  - Department Wise
  1. Emergency management(86.32%), Human Resource(86.30%), Family Justice Center(85%), Communications Office(84.58%) and Economic Development(84.29%) has the highest engagement levels. Employees in this departmentss feel aligned with their work environment.
  2. Law enforcement and judicial roles like Sheriff's department (49.64%), district court (71.90%) report lower agreement responses, likely due to job stress and workload pressures.
  
  - Role Wise
  1. Leadership roles (Directors, Managers, Supervisors) have the lowest agreement responses.

- #### As an employer, what steps might you take to improve employee satisfaction based on the survey results?
  
  ![Employee-satisfaction-Percentage](Employee-satisfaction.PNG)

  As an employer, the following steps can be taken to address low agreement rates and improve overall employee satisfaction:
  1. Provide leadership training on employee engagement and communication
  2. Encourage regular check-ins and one-on-one meetings between managers and employees
  3. Ensure employees feel heard and valued by implementing feedback-driven changes
  4. Create employee recognition programs, offer performance based incentives, celebrate team successes in public forums or meetings to boost morale.

 - #### What is the total agreement to disagreement percentage
   
   ![Agreement-Disagreement-%](agreement-disagreement-%.PNG)

   Overall agreement percentage: 100%
   
   this suggests that a majority of employees are satisfied.
    
   Overall disagreement percentage: 29%
   
   This signals areas for improvement.

## Conclusion
The survey shows 100% agreement, but 29% disagreement on some questions highlights concerns. Job clarity(91%) and supervisor respect(85%) rank high, while the sheriff's department (49.64%) has the lowest satisfaction. Key issues include:
1. Lack of workplace friendships(41%)
2. Infrequent feedback(34%)

Strengthening team relationships, leadership, and feedback can drive improvement.
    
    


















