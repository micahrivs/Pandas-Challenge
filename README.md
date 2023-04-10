# Pandas-Challenge
 ## "While data can reveal valuable insights, having the right tool, such as the Pandas library, can help you effectively analyze and interpret that data."
## Background
This repository presents a Python Pandas solution for analyzing school district data in the education sector of a city. The goal of this project is to aid the school board and mayor in making informed decisions about future school budgets and priorities. To accomplish this, two datasets in CSV format were utilized: schools_complete.csv and students_complete.csv. The former contains information such as Student ID, school name, type, size, and budget, while the latter includes columns for Student ID, student name, gender, grade, school name, reading score, and math score. These datasets were imported, merged, and analyzed using Python Pandas dataframes to display the aggregate data. The project was conducted in a Jupyter notebook, and a link to the analysis report is provided through the Jupyter Notebook Viewer.
 # Observable Trends
* The dataset used in this analysis includes data from 15 schools, with a total of 39,170 students. The average reading score for all students is 81.87, which is higher than the average math score of 78.98. In terms of passing rates, the percentage of students who passed the reading test (85.80%) is higher than the percentage who passed the math test (74.98%). The overall passing rate, which considers both subjects, is 65.17%. These results suggest that students tend to perform better in reading than in math.
* Based on the school summary findings, it was determined that out of the 15 schools included in the dataset, 7 of them are district schools while the remaining 8 are charter schools. The number of students at each school ranges from 427 students at Holden High School to 4976 students at Bailey High School. Furthermore, the data shows that district schools tend to have more students than charter schools. It is reasonable to conclude that the reason for this difference is due to the fact that district schools have a wider geographical coverage compared to charter schools.
* In the school summary, the total budget field provides information about the amount of money allocated to each school. Bailey High School has the highest budget at $3,124,928.00, while Holden High School has the lowest budget at $248,087.00. Interestingly, Bailey High School is not one of the top-performing schools, indicating that the school's budget allocators should focus on improving the quality of education provided with the available resources. Additionally, the budget per student varies across schools, with Huang High School having the highest budget per student at $655.00, while Wilson High School has the lowest at $578.00. Huang High School and Bailey High School are both among the bottom-performing schools, suggesting that improving the quality of education with the allocated budget should be a priority for these schools.
It is worth noting that the total budget allocated to district schools is higher than that of charter schools ($17,347,923.00 vs. $7,301,505.00). However, the allocation of budget per student is higher for charter schools ($4,796.00) than district schools ($4,505.00). This could be due to the fact that charter schools have fewer students compared to district schools.

* The data analysis revealed that, in all metrics (average, percent, and overall) of reading and math scores, charter schools performed better than district schools. Pena High School had the highest average math score (83.84), the highest percent of students passing math (94.59%), and the highest average reading score (84.04). This indicates that Pena High School is highly reputed for its quality of teaching in both math and reading.
On the other hand, Huang High School had a lower average math score (76.84) and a lower percent of students passing math (65.68%). With regards to the percent of students passing the reading class, Thomas High School had the highest percentage value (97.30%). In contrast, Rodriguez High School had a lower average reading score (80.74), and Ford High School had a lower percent of students passing reading.
In terms of overall percentage passing, Cabrera High School had the highest passing percentage rate (91.33%), while Rodriguez High School had the lowest passing percentage (52.98%). These findings suggest that there are significant differences in the quality of education provided by different schools, and further action may be required to improve the quality of education in some of the schools with lower performance metrics.

* According to the data analysis, it was found that grade 11 students at Holden High School had the highest average math score (85) compared to all schools and grades. This indicates that Holden High School has a strong math program for its grade 11 students.
Additionally, it was observed that Holden High School's grade 12 students had a higher average reading score (84.698795) compared to all schools and grades. This suggests that the school has a good quality reading program for its grade 12 students.
Overall, these findings show that Holden High School has a good reputation for providing quality education in both math and reading to its students, particularly in grade 11 for math and grade 12 for reading.

* One of the irregular findings in the analysis is that when the budget per student increases, the average math score, average reading score, percent of passing math, percent of passing reading, and the overall passing rate decrease. This is a surprising result as it goes against the common belief that higher budgets lead to better academic achievement.
This finding suggests that there might be other factors that contribute to academic success besides the budget allocated per student. It could be that the schools with higher budgets are not using the resources effectively or efficiently, or that other external factors such as student motivation, parental involvement, and teacher quality play a more significant role in academic success.
These findings raise important questions about the relationship between budget allocation and academic achievement, and call for further research to investigate the underlying factors that affect student performance.
* According to the data analysis, there is a negative correlation between the size of schools and student achievement. Specifically, as the number of students in a school increases, the average math and reading scores, passing rates for math and reading, and overall passing rates decrease. This suggests that schools, districts, and charters should consider reducing student size in order to improve academic achievement.
