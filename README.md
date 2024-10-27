#### Manufacturing-Efficiency-Assessment-Downtime-Insights



![Line Downtime](https://github.com/user-attachments/assets/6ac81dc9-cd97-47b2-9855-0d3a0f12d2fe)


### Project Overview

As an aspiring production manager at Wolf Cola, a soft drink manufacturing company operating in India, I analyzed the productivity and downtime data collected by Frank, the former manager, to identify opportunities for improving the efficiency of the bottling production line. The project aimed to assess line efficiency, identify key downtime
factors, and explore operator-specific downtime patterns to enhance overall performance.

This project demonstrates my ability to use data-driven techniques to identify bottlenecks, provide actionable recommendations, and improve manufacturing operations. All visuals and charts created during this analysis are included as part of my portfolio. Please note that this is dummy data sourced online for practice purposes.

## Objective 1: Calculate Line Efficiency

The first objective was to calculate the efficiency of the production line, broken down by operator, and visualize the results.

# Steps Taken

 - Created a "Batch Time" column:
I calculated the time (in minutes) between the start and end of each batch using the following formula:
=(F2 - E2) * 24 * 60

-  Created a "Min Batch Time" column:
Used the XLOOKUP function to pull the minimum batch time for each product from the "Products" sheet:
=XLOOKUP(B2, Products!$A$2:$A$7, Products!$D$2:$D$7)

- Calculated Operator Efficiency:
I used a PivotTable to determine the efficiency of each operator based on batch time and minimum batch time.

- Visualized Efficiency Data:
I created a clustered bar chart to display operator efficiency.

##  Recommendation

Focus on improving Mac's efficiency (61%) through targeted training or a performance review, as it is the lowest among all operators.
Leverage Charlie’s best practices (67%) to enhance the performance of other operators.


![Line Productivity](https://github.com/user-attachments/assets/ebc1af86-f275-4822-a62b-77ead2641477)


## Objective 2: Identify Main Downtime Factors

The second objective was to use a Pareto chart to highlight the main factors contributing to downtime.

# Steps Taken\

- Created a "Downtime" Column:
I summed the downtime for each factor using the INDEX and MATCH functions:
=SUM(INDEX('Line downtime'!$C$3:$N$40,,MATCH(A2,'Line downtime'!$C$2:$N$2,0)))

- Sorted Factors by Downtime:
Applied filters to sort factors in descending order by total downtime.

- Calculated Running Total of Downtime:
I used the following formula to calculate the percentage running total of downtime:
=SUM($D$2:D2) / SUM($D$2:$D$13)

- I formatted the column to display percentages.

- Created a Pareto Chart:
Visualized downtime factors to identify high-impact issues.

![Downtime Factors](https://github.com/user-attachments/assets/70c2fc16-7562-40df-8d67-e20a0d984b96)


##  Recommendations

- Prioritize Key Downtime Factors: Focus on machine adjustments and failures by implementing regular maintenance schedules and predictive maintenance strategies.

- Optimize Inventory Management: Introduce better stock forecasting methods and set minimum stock levels to prevent shortages.
  
- Streamline Batch Processes: Automate batch changes and standardize coding procedures to minimize setup time.
  
- Address Quick Wins: Provide troubleshooting guides and operator training to reduce calibration, labeling, and conveyor-related issues.
  
- Conduct Root Cause Analysis (RCA): Utilize tools like the 5 Whys to uncover underlying issues.
  
- Implement Real-Time Monitoring: Set up tracking and alerts for quick response to emerging issues.
  
- Enhance Operator Training: Train operators to proactively handle minor issues and avoid unnecessary emergency stops.
  
- Monitor KPIs Regularly: Track downtime trends to drive continuous improvement.

  
## Conclusion

- Addressing high-impact downtime factors (e.g., machine adjustments, failures, and inventory shortages) will significantly improve operational efficiency.
  
- Implementing predictive maintenance, optimizing batch changes, and investing in operator training are essential steps toward long-term performance gains.



## Objective 3: Calculate Downtime by Operator & Factor

The third objective was to analyze downtime by operator and downtime factor using a matrix.

# Steps Taken:

- Created a Matrix with Operators and Factors:
I used the operators as rows and the main downtime factors as columns on the dashboard.
Added an "Operator" Column to the "Line Downtime" Sheet

- I used XLOOKUP to retrieve the operator for each batch:
=XLOOKUP(A3, 'Line productivity'!$C$2:$C$39, 'Line productivity'!$D$2:$D$39)

- Calculated Downtime by Operator and Factor:
I used a combination of SUMIFS and INDEX/MATCH to calculate total downtime:
=SUMIFS(INDEX('Line downtime'!$C$3:$N$40, , IFERROR(MATCH(Dashboard!B$17, 'Line downtime'!$C$2:$N$2, 0), 1)), 'Line downtime'!$B$3:$B$40, Dashboard!$A20)

- Applied Conditional Formatting:

I applied conditional formatting to highlight the highest, middle, and lowest downtime.
- Dark Blue for highest downtime
- Orange for middle downtime
- White for lowest downtime

 ![Downtime Dashboard](https://github.com/user-attachments/assets/fa8ff9ed-641e-4e0d-92c2-9a0ce758883d) 

## Recommendation
- Mac's high downtime from batch changes (130 minutes) and inventory shortages (80 minutes) suggests a need for better process optimization and inventory planning.
  
- Dennis and Charlie experienced significant downtime from machine adjustments and failures, indicating the need for preventive maintenance.
  
- Dee requires support with inventory management to reduce downtime associated with stock issues.

  
## Final Remarks

This analysis highlights key areas for improvement, including targeted operator training, preventive maintenance, and streamlined processes. 

The matrix and Pareto chart provide actionable insights into where downtime is concentrated, enabling the team to address high-priority issues first.

## Disclaimer

This project used dummy data sourced online to strengthen my data analysis skills. Visual representations of the work, including charts and dashboards, are included in my portfolio.
