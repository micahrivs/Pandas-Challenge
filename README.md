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

## Table of Contents
* [Import Dependencies and Setup](https://github.com/micahrivs/Pandas-Challenge/blob/main/PyCitySchools/PyCitySchools.ipynb)
* [Load, Read and Merge the Data](https://github.com/micahrivs/Pandas-Challenge/blob/main/PyCitySchools/PyCitySchools.ipynb)
* [District Summary](https://github.com/micahrivs/Pandas-Challenge/blob/main/PyCitySchools/PyCitySchools.ipynb)
* [School Summary](https://github.com/micahrivs/Pandas-Challenge/blob/main/PyCitySchools/PyCitySchools.ipynb)
* [Top Performing Schools (By % Overall Passing)](https://github.com/micahrivs/Pandas-Challenge/blob/main/PyCitySchools/PyCitySchools.ipynb)
* [Math Scores by Grade](https://github.com/micahrivs/Pandas-Challenge/blob/main/PyCitySchools/PyCitySchools.ipynb)
* [Reading Scores by Grade](https://github.com/micahrivs/Pandas-Challenge/blob/main/PyCitySchools/PyCitySchools.ipynb)
* [Scores by School Spending](https://github.com/micahrivs/Pandas-Challenge/blob/main/PyCitySchools/PyCitySchools.ipynb)
* [Scores by School Type](https://github.com/micahrivs/Pandas-Challenge/blob/main/PyCitySchools/PyCitySchools.ipynb)

### Import Dependencies and Setup

```python
# Dependencies and Setup
import pandas as pd
```
### Load, Read and Merge the Data
```python
# File to Load (Remember to Change These)
school_data_to_load = Path("Resources/schools_complete.csv")
student_data_to_load = Path("Resources/students_complete.csv")

# Read School and Student Data File and store into Pandas DataFrames
school_data = pd.read_csv(school_data_to_load)
student_data = pd.read_csv(student_data_to_load)

# Combine the data into a single dataset.  
school_data_complete = pd.merge(student_data, school_data, how="left", on=["school_name", "school_name"])
school_data_complete.head()
```
### District Summary

* A detailed examination of the districts formed based on the metrics mentioned below at a higher level.
  * Total Schools
  * Total Students
  * Total Budget
  * Average Math Score
  * Average Reading Score
  * % Passing Math (The percentage of students that passed math.)
  * % Passing Reading (The percentage of students that passed reading.)
  * % Overall Passing (The percentage of students that passed math **and** reading.)
  
  The table outlining the summary of districts appears in the following manner: 
<table id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691" > 
<thead>    <tr> 
        <th class="blank level0" ></th> 
        <th class="col_heading level0 col0" >Total Schools</th> 
        <th class="col_heading level0 col1" >Total Students</th> 
        <th class="col_heading level0 col2" >Total Budget</th> 
        <th class="col_heading level0 col3" >Average Math Score</th> 
        <th class="col_heading level0 col4" >Average Reading Score</th> 
        <th class="col_heading level0 col5" >% Passing Math</th> 
        <th class="col_heading level0 col6" >% Passing Reading</th> 
        <th class="col_heading level0 col7" >% Overall Passing</th> 
    </tr></thead> 
<tbody>    <tr> 
        <th id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691" class="row_heading level0 row0" >0</th> 
        <td id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691row0_col0" class="data row0 col0" >15</td> 
        <td id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691row0_col1" class="data row0 col1" >39,170</td> 
        <td id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691row0_col2" class="data row0 col2" >$24,649,428.00</td> 
        <td id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691row0_col3" class="data row0 col3" >78.985371</td> 
        <td id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691row0_col4" class="data row0 col4" >81.87784</td> 
        <td id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691row0_col5" class="data row0 col5" >74.980853	</td> 
        <td id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691row0_col6" class="data row0 col6" >85.805463</td> 
        <td id="T_1a0abed2_9a44_11e7_bb3a_0c4de9c48691row0_col7" class="data row0 col7" >65.172326</td> 
    </tr></tbody> 
</table> 

### School Summary

* A table providing a summary of essential metrics for each school was generated based on the following criteria.
  * School Name
  * School Type
  * Total Students
  * Total School Budget
  * Per Student Budget
  * Average Math Score
  * Average Reading Score
  * % Passing Math (The percentage of students that passed math.)
  * % Passing Reading (The percentage of students that passed reading.)
  * % Overall Passing (The percentage of students that passed math and reading.)
 
The table outlining the summary of schools appears in the following manner:

<table id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9"><thead>    <tr>        <th class="blank level0"></th>        <th class="col_heading level0 col0">School Type</th>        <th class="col_heading level0 col1">Total Students</th>        <th class="col_heading level0 col2">Total School Budget</th>        <th class="col_heading level0 col3">Per Student Budget</th>        <th class="col_heading level0 col4">Average Math Score</th>        <th class="col_heading level0 col5">Average Reading Score</th>        <th class="col_heading level0 col6">% Passing Math</th>        <th class="col_heading level0 col7">% Passing Reading</th>        <th class="col_heading level0 col8">% Overall Passing</th>    </tr></thead><tbody>
                <tr>
                        <th id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9level0_row0" class="row_heading level0 row0">Bailey High School</th>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row0_col0" class="data row0 col0">District</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row0_col1" class="data row0 col1">4976</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row0_col2" class="data row0 col2">$3,124,928.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row0_col3" class="data row0 col3">$628.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row0_col4" class="data row0 col4">77.048432</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row0_col5" class="data row0 col5">81.033963</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row0_col6" class="data row0 col6">66.680064</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row0_col7" class="data row0 col7">81.933280</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row0_col8" class="data row0 col8">54.642283</td>
            </tr>
            <tr>
                        <th id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9level0_row1" class="row_heading level0 row1">Cabrera High School</th>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row1_col0" class="data row1 col0">Charter</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row1_col1" class="data row1 col1">1858</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row1_col2" class="data row1 col2">$1,081,356.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row1_col3" class="data row1 col3">$582.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row1_col4" class="data row1 col4">83.061895</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row1_col5" class="data row1 col5">83.975780</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row1_col6" class="data row1 col6">94.133477</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row1_col7" class="data row1 col7">97.039828</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row1_col8" class="data row1 col8">91.334769</td>
            </tr>
            <tr>
                        <th id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9level0_row2" class="row_heading level0 row2">Figueroa High School</th>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row2_col0" class="data row2 col0">District</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row2_col1" class="data row2 col1">2949</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row2_col2" class="data row2 col2">$1,884,411.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row2_col3" class="data row2 col3">$639.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row2_col4" class="data row2 col4">76.711767</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row2_col5" class="data row2 col5">81.158020</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row2_col6" class="data row2 col6">65.988471</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row2_col7" class="data row2 col7">80.739234</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row2_col8" class="data row2 col8">53.204476</td>
            </tr>
            <tr>
                        <th id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9level0_row3" class="row_heading level0 row3">Ford High School</th>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row3_col0" class="data row3 col0">District</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row3_col1" class="data row3 col1">2739</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row3_col2" class="data row3 col2">$1,763,916.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row3_col3" class="data row3 col3">$644.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row3_col4" class="data row3 col4">77.102592</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row3_col5" class="data row3 col5">80.746258</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row3_col6" class="data row3 col6">68.309602</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row3_col7" class="data row3 col7">79.299014</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row3_col8" class="data row3 col8">54.289887</td>
            </tr>
            <tr>
                        <th id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9level0_row4" class="row_heading level0 row4">Griffin High School</th>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row4_col0" class="data row4 col0">Charter</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row4_col1" class="data row4 col1">1468</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row4_col2" class="data row4 col2">$917,500.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row4_col3" class="data row4 col3">$625.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row4_col4" class="data row4 col4">83.351499</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row4_col5" class="data row4 col5">83.816757</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row4_col6" class="data row4 col6">93.392371</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row4_col7" class="data row4 col7">97.138965</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row4_col8" class="data row4 col8">90.599455</td>
            </tr>
            <tr>
                        <th id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9level0_row5" class="row_heading level0 row5">Hernandez High School</th>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row5_col0" class="data row5 col0">District</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row5_col1" class="data row5 col1">4635</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row5_col2" class="data row5 col2">$3,022,020.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row5_col3" class="data row5 col3">$652.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row5_col4" class="data row5 col4">77.289752</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row5_col5" class="data row5 col5">80.934412</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row5_col6" class="data row5 col6">66.752967</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row5_col7" class="data row5 col7">80.862999</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row5_col8" class="data row5 col8">53.527508</td>
            </tr>
            <tr>
                        <th id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9level0_row6" class="row_heading level0 row6">Holden High School</th>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row6_col0" class="data row6 col0">Charter</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row6_col1" class="data row6 col1">427</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row6_col2" class="data row6 col2">$248,087.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row6_col3" class="data row6 col3">$581.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row6_col4" class="data row6 col4">83.803279</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row6_col5" class="data row6 col5">83.814988</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row6_col6" class="data row6 col6">92.505855</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row6_col7" class="data row6 col7">96.252927</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row6_col8" class="data row6 col8">89.227166</td>
            </tr>
            <tr>
                        <th id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9level0_row7" class="row_heading level0 row7">Huang High School</th>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row7_col0" class="data row7 col0">District</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row7_col1" class="data row7 col1">2917</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row7_col2" class="data row7 col2">$1,910,635.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row7_col3" class="data row7 col3">$655.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row7_col4" class="data row7 col4">76.629414</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row7_col5" class="data row7 col5">81.182722</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row7_col6" class="data row7 col6">65.683922</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row7_col7" class="data row7 col7">81.316421</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row7_col8" class="data row7 col8">53.513884</td>
            </tr>
            <tr>
                        <th id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9level0_row8" class="row_heading level0 row8">Johnson High School</th>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row8_col0" class="data row8 col0">District</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row8_col1" class="data row8 col1">4761</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row8_col2" class="data row8 col2">$3,094,650.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row8_col3" class="data row8 col3">$650.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row8_col4" class="data row8 col4">77.072464</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row8_col5" class="data row8 col5">80.966394</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row8_col6" class="data row8 col6">66.057551</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row8_col7" class="data row8 col7">81.222432</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row8_col8" class="data row8 col8">53.539172</td>
            </tr>
            <tr>
                        <th id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9level0_row9" class="row_heading level0 row9">Pena High School</th>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row9_col0" class="data row9 col0">Charter</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row9_col1" class="data row9 col1">962</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row9_col2" class="data row9 col2">$585,858.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row9_col3" class="data row9 col3">$609.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row9_col4" class="data row9 col4">83.839917</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row9_col5" class="data row9 col5">84.044699</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row9_col6" class="data row9 col6">94.594595</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row9_col7" class="data row9 col7">95.945946</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row9_col8" class="data row9 col8">90.540541</td>
            </tr>
            <tr>
                        <th id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9level0_row10" class="row_heading level0 row10">Rodriguez High School</th>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row10_col0" class="data row10 col0">District</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row10_col1" class="data row10 col1">3999</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row10_col2" class="data row10 col2">$2,547,363.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row10_col3" class="data row10 col3">$637.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row10_col4" class="data row10 col4">76.842711</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row10_col5" class="data row10 col5">80.744686</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row10_col6" class="data row10 col6">66.366592</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row10_col7" class="data row10 col7">80.220055</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row10_col8" class="data row10 col8">52.988247</td>
            </tr>
            <tr>
                        <th id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9level0_row11" class="row_heading level0 row11">Shelton High School</th>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row11_col0" class="data row11 col0">Charter</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row11_col1" class="data row11 col1">1761</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row11_col2" class="data row11 col2">$1,056,600.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row11_col3" class="data row11 col3">$600.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row11_col4" class="data row11 col4">83.359455</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row11_col5" class="data row11 col5">83.725724</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row11_col6" class="data row11 col6">93.867121</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row11_col7" class="data row11 col7">95.854628</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row11_col8" class="data row11 col8">89.892107</td>
            </tr>
            <tr>
                        <th id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9level0_row12" class="row_heading level0 row12">Thomas High School</th>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row12_col0" class="data row12 col0">Charter</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row12_col1" class="data row12 col1">1635</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row12_col2" class="data row12 col2">$1,043,130.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row12_col3" class="data row12 col3">$638.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row12_col4" class="data row12 col4">83.418349</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row12_col5" class="data row12 col5">83.848930</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row12_col6" class="data row12 col6">93.272171</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row12_col7" class="data row12 col7">97.308869</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row12_col8" class="data row12 col8">90.948012</td>
            </tr>
            <tr>
                        <th id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9level0_row13" class="row_heading level0 row13">Wilson High School</th>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row13_col0" class="data row13 col0">Charter</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row13_col1" class="data row13 col1">2283</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row13_col2" class="data row13 col2">$1,319,574.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row13_col3" class="data row13 col3">$578.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row13_col4" class="data row13 col4">83.274201</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row13_col5" class="data row13 col5">83.989488</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row13_col6" class="data row13 col6">93.867718</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row13_col7" class="data row13 col7">96.539641</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row13_col8" class="data row13 col8">90.582567</td>
            </tr>
            <tr>
                        <th id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9level0_row14" class="row_heading level0 row14">Wright High School</th>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row14_col0" class="data row14 col0">Charter</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row14_col1" class="data row14 col1">1800</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row14_col2" class="data row14 col2">$1,049,400.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row14_col3" class="data row14 col3">$583.00</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row14_col4" class="data row14 col4">83.682222</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row14_col5" class="data row14 col5">83.955000</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row14_col6" class="data row14 col6">93.333333</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row14_col7" class="data row14 col7">96.611111</td>
                        <td id="T_8d9d78d2_a90d_11ea_b01d_8863df8cd0c9row14_col8" class="data row14 col8">90.333333</td>
            </tr>
    </tbody></table>
 

### Top Performing Schools (By % Overall Passing)

* A table featuring the top 5 schools with the highest % Overall Passing rate was generated, and it includes the following metrics.
  * School Name
  * School Type
  * Total Students
  * Total School Budget
  * Per Student Budget
  * Average Math Score
  * Average Reading Score
  * % Passing Math (The percentage of students that passed math.)
  * % Passing Reading (The percentage of students that passed reading.)
  * % Overall Passing (The percentage of students that passed math and reading.)
  
The table showcasing the Top Performing Schools (By % Overall Passing) appears in the following manner:

<table id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9"><thead>    <tr>        <th class="blank level0"></th>        <th class="col_heading level0 col0">School Type</th>        <th class="col_heading level0 col1">Total Students</th>        <th class="col_heading level0 col2">Total School Budget</th>        <th class="col_heading level0 col3">Per Student Budget</th>        <th class="col_heading level0 col4">Average Math Score</th>        <th class="col_heading level0 col5">Average Reading Score</th>        <th class="col_heading level0 col6">% Passing Math</th>        <th class="col_heading level0 col7">% Passing Reading</th>        <th class="col_heading level0 col8">% Overall Passing</th>    </tr></thead><tbody>
                <tr>
                        <th id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9level0_row0" class="row_heading level0 row0">Cabrera High School</th>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row0_col0" class="data row0 col0">Charter</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row0_col1" class="data row0 col1">1858</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row0_col2" class="data row0 col2">$1,081,356.00</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row0_col3" class="data row0 col3">$582.00</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row0_col4" class="data row0 col4">83.061895</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row0_col5" class="data row0 col5">83.975780</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row0_col6" class="data row0 col6">94.133477</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row0_col7" class="data row0 col7">97.039828</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row0_col8" class="data row0 col8">91.334769</td>
            </tr>
            <tr>
                        <th id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9level0_row1" class="row_heading level0 row1">Thomas High School</th>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row1_col0" class="data row1 col0">Charter</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row1_col1" class="data row1 col1">1635</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row1_col2" class="data row1 col2">$1,043,130.00</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row1_col3" class="data row1 col3">$638.00</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row1_col4" class="data row1 col4">83.418349</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row1_col5" class="data row1 col5">83.848930</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row1_col6" class="data row1 col6">93.272171</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row1_col7" class="data row1 col7">97.308869</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row1_col8" class="data row1 col8">90.948012</td>
            </tr>
            <tr>
                        <th id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9level0_row2" class="row_heading level0 row2">Griffin High School</th>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row2_col0" class="data row2 col0">Charter</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row2_col1" class="data row2 col1">1468</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row2_col2" class="data row2 col2">$917,500.00</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row2_col3" class="data row2 col3">$625.00</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row2_col4" class="data row2 col4">83.351499</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row2_col5" class="data row2 col5">83.816757</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row2_col6" class="data row2 col6">93.392371</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row2_col7" class="data row2 col7">97.138965</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row2_col8" class="data row2 col8">90.599455</td>
            </tr>
            <tr>
                        <th id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9level0_row3" class="row_heading level0 row3">Wilson High School</th>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row3_col0" class="data row3 col0">Charter</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row3_col1" class="data row3 col1">2283</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row3_col2" class="data row3 col2">$1,319,574.00</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row3_col3" class="data row3 col3">$578.00</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row3_col4" class="data row3 col4">83.274201</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row3_col5" class="data row3 col5">83.989488</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row3_col6" class="data row3 col6">93.867718</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row3_col7" class="data row3 col7">96.539641</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row3_col8" class="data row3 col8">90.582567</td>
            </tr>
            <tr>
                        <th id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9level0_row4" class="row_heading level0 row4">Pena High School</th>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row4_col0" class="data row4 col0">Charter</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row4_col1" class="data row4 col1">962</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row4_col2" class="data row4 col2">$585,858.00</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row4_col3" class="data row4 col3">$609.00</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row4_col4" class="data row4 col4">83.839917</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row4_col5" class="data row4 col5">84.044699</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row4_col6" class="data row4 col6">94.594595</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row4_col7" class="data row4 col7">95.945946</td>
                        <td id="T_8d9ff59e_a90d_11ea_b01d_8863df8cd0c9row4_col8" class="data row4 col8">90.540541</td>
            </tr>
    </tbody></table> 


### Bottom Performing Schools (By % Overall Passing)

* A table featuring the bottom 5 schools with the lowest % Overall Passing rate was generated, including all of the same metrics as above.

The table showcasing the Bottom Performing Schools (By % Overall Passing) appears in the following manner:

<table id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9"><thead>    <tr>        <th class="blank level0"></th>        <th class="col_heading level0 col0">School Type</th>        <th class="col_heading level0 col1">Total Students</th>        <th class="col_heading level0 col2">Total School Budget</th>        <th class="col_heading level0 col3">Per Student Budget</th>        <th class="col_heading level0 col4">Average Math Score</th>        <th class="col_heading level0 col5">Average Reading Score</th>        <th class="col_heading level0 col6">% Passing Math</th>        <th class="col_heading level0 col7">% Passing Reading</th>        <th class="col_heading level0 col8">% Overall Passing</th>    </tr></thead><tbody>
                <tr>
                        <th id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9level0_row0" class="row_heading level0 row0">Rodriguez High School</th>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row0_col0" class="data row0 col0">District</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row0_col1" class="data row0 col1"> 3999</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row0_col2" class="data row0 col2">$2,547,363.00</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row0_col3" class="data row0 col3">$637.00</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row0_col4" class="data row0 col4">76.842711</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row0_col5" class="data row0 col5">80.744686</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row0_col6" class="data row0 col6">66.366592</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row0_col7" class="data row0 col7">80.220055</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row0_col8" class="data row0 col8">52.988247</td>
            </tr>
            <tr>
                        <th id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9level0_row1" class="row_heading level0 row1">Figueroa High School</th>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row1_col0" class="data row1 col0">District</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row1_col1" class="data row1 col1"> 2949</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row1_col2" class="data row1 col2">$1,884,411.00</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row1_col3" class="data row1 col3">$639.00</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row1_col4" class="data row1 col4">76.711767</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row1_col5" class="data row1 col5">81.158020</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row1_col6" class="data row1 col6">65.988471</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row1_col7" class="data row1 col7">80.739234</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row1_col8" class="data row1 col8">53.204476</td>
            </tr>
            <tr>
                        <th id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9level0_row2" class="row_heading level0 row2">Huang High School</th>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row2_col0" class="data row2 col0">District</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row2_col1" class="data row2 col1"> 2917</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row2_col2" class="data row2 col2">$1,910,635.00</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row2_col3" class="data row2 col3">$655.00</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row2_col4" class="data row2 col4">76.629414</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row2_col5" class="data row2 col5">81.182722</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row2_col6" class="data row2 col6">65.683922</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row2_col7" class="data row2 col7">81.316421</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row2_col8" class="data row2 col8">53.513884</td>
            </tr>
            <tr>
                        <th id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9level0_row3" class="row_heading level0 row3">Hernandez High School</th>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row3_col0" class="data row3 col0">District</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row3_col1" class="data row3 col1"> 4635</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row3_col2" class="data row3 col2">$3,022,020.00</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row3_col3" class="data row3 col3">$652.00</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row3_col4" class="data row3 col4">77.289752</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row3_col5" class="data row3 col5">80.934412</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row3_col6" class="data row3 col6">66.752967</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row3_col7" class="data row3 col7">80.862999</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row3_col8" class="data row3 col8">53.527508</td>
            </tr>
            <tr>
                        <th id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9level0_row4" class="row_heading level0 row4">Johnson High School</th>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row4_col0" class="data row4 col0">District</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row4_col1" class="data row4 col1"> 4761</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row4_col2" class="data row4 col2">$3,094,650.00</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row4_col3" class="data row4 col3">$650.00</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row4_col4" class="data row4 col4">77.072464</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row4_col5" class="data row4 col5">80.966394</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row4_col6" class="data row4 col6">66.057551</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row4_col7" class="data row4 col7">81.222432</td>
                        <td id="T_8da1e836_a90d_11ea_b01d_8863df8cd0c9row4_col8" class="data row4 col8">53.539172</td>
            </tr>
    </tbody></table>  


### Math Scores by Grade

* A table listing the average Math Score of students in each grade level (9th, 10th, 11th, and 12th) for every school was generated.

The table showcasing Math Scores by Grade appears in the following manner:

<table id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9"><thead>    <tr>        <th class="blank level0"></th>        <th class="col_heading level0 col0">9th</th>        <th class="col_heading level0 col1">10th</th>        <th class="col_heading level0 col2">11th</th>        <th class="col_heading level0 col3">12th</th>    </tr>    <tr>        <th class="index_name level0">School Name</th>        <th class="blank"></th>        <th class="blank"></th>        <th class="blank"></th>        <th class="blank"></th>    </tr></thead><tbody>
                <tr>
                        <th id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9level0_row0" class="row_heading level0 row0">Bailey High School</th>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row0_col0" class="data row0 col0">77.083676</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row0_col1" class="data row0 col1">76.996772</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row0_col2" class="data row0 col2">77.515588</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row0_col3" class="data row0 col3">76.492218</td>
            </tr>
            <tr>
                        <th id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9level0_row1" class="row_heading level0 row1">Cabrera High School</th>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row1_col0" class="data row1 col0">83.094697</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row1_col1" class="data row1 col1">83.154506</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row1_col2" class="data row1 col2">82.765560</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row1_col3" class="data row1 col3">83.277487</td>
            </tr>
            <tr>
                        <th id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9level0_row2" class="row_heading level0 row2">Figueroa High School</th>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row2_col0" class="data row2 col0">76.403037</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row2_col1" class="data row2 col1">76.539974</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row2_col2" class="data row2 col2">76.884344</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row2_col3" class="data row2 col3">77.151369</td>
            </tr>
            <tr>
                        <th id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9level0_row3" class="row_heading level0 row3">Ford High School</th>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row3_col0" class="data row3 col0">77.361345</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row3_col1" class="data row3 col1">77.672316</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row3_col2" class="data row3 col2">76.918058</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row3_col3" class="data row3 col3">76.179963</td>
            </tr>
            <tr>
                        <th id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9level0_row4" class="row_heading level0 row4">Griffin High School</th>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row4_col0" class="data row4 col0">82.044010</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row4_col1" class="data row4 col1">84.229064</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row4_col2" class="data row4 col2">83.842105</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row4_col3" class="data row4 col3">83.356164</td>
            </tr>
            <tr>
                        <th id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9level0_row5" class="row_heading level0 row5">Hernandez High School</th>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row5_col0" class="data row5 col0">77.438495</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row5_col1" class="data row5 col1">77.337408</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row5_col2" class="data row5 col2">77.136029</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row5_col3" class="data row5 col3">77.186567</td>
            </tr>
            <tr>
                        <th id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9level0_row6" class="row_heading level0 row6">Holden High School</th>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row6_col0" class="data row6 col0">83.787402</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row6_col1" class="data row6 col1">83.429825</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row6_col2" class="data row6 col2">85.000000</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row6_col3" class="data row6 col3">82.855422</td>
            </tr>
            <tr>
                        <th id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9level0_row7" class="row_heading level0 row7">Huang High School</th>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row7_col0" class="data row7 col0">77.027251</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row7_col1" class="data row7 col1">75.908735</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row7_col2" class="data row7 col2">76.446602</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row7_col3" class="data row7 col3">77.225641</td>
            </tr>
            <tr>
                        <th id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9level0_row8" class="row_heading level0 row8">Johnson High School</th>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row8_col0" class="data row8 col0">77.187857</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row8_col1" class="data row8 col1">76.691117</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row8_col2" class="data row8 col2">77.491653</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row8_col3" class="data row8 col3">76.863248</td>
            </tr>
            <tr>
                        <th id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9level0_row9" class="row_heading level0 row9">Pena High School</th>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row9_col0" class="data row9 col0">83.625455</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row9_col1" class="data row9 col1">83.372000</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row9_col2" class="data row9 col2">84.328125</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row9_col3" class="data row9 col3">84.121547</td>
            </tr>
            <tr>
                        <th id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9level0_row10" class="row_heading level0 row10">Rodriguez High School</th>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row10_col0" class="data row10 col0">76.859966</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row10_col1" class="data row10 col1">76.612500</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row10_col2" class="data row10 col2">76.395626</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row10_col3" class="data row10 col3">77.690748</td>
            </tr>
            <tr>
                        <th id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9level0_row11" class="row_heading level0 row11">Shelton High School</th>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row11_col0" class="data row11 col0">83.420755</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row11_col1" class="data row11 col1">82.917411</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row11_col2" class="data row11 col2">83.383495</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row11_col3" class="data row11 col3">83.778976</td>
            </tr>
            <tr>
                        <th id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9level0_row12" class="row_heading level0 row12">Thomas High School</th>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row12_col0" class="data row12 col0">83.590022</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row12_col1" class="data row12 col1">83.087886</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row12_col2" class="data row12 col2">83.498795</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row12_col3" class="data row12 col3">83.497041</td>
            </tr>
            <tr>
                        <th id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9level0_row13" class="row_heading level0 row13">Wilson High School</th>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row13_col0" class="data row13 col0">83.085578</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row13_col1" class="data row13 col1">83.724422</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row13_col2" class="data row13 col2">83.195326</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row13_col3" class="data row13 col3">83.035794</td>
            </tr>
            <tr>
                        <th id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9level0_row14" class="row_heading level0 row14">Wright High School</th>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row14_col0" class="data row14 col0">83.264706</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row14_col1" class="data row14 col1">84.010288</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row14_col2" class="data row14 col2">83.836782</td>
                        <td id="T_8da8ee10_a90d_11ea_b01d_8863df8cd0c9row14_col3" class="data row14 col3">83.644986</td>
            </tr>
    </tbody></table>  


### Reading Scores by Grade

* A table listing the average Reading Score of students in each grade level (9th, 10th, 11th, and 12th) for every school was generated.

The table of Reading Scores by Grade appears in the following manner:

<table id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9"><thead>    <tr>        <th class="blank level0"></th>        <th class="col_heading level0 col0">9th</th>        <th class="col_heading level0 col1">10th</th>        <th class="col_heading level0 col2">11th</th>        <th class="col_heading level0 col3">12th</th>    </tr>    <tr>        <th class="index_name level0">School Name</th>        <th class="blank"></th>        <th class="blank"></th>        <th class="blank"></th>        <th class="blank"></th>    </tr></thead><tbody>
                <tr>
                        <th id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9level0_row0" class="row_heading level0 row0">Bailey High School</th>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row0_col0" class="data row0 col0">81.303155</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row0_col1" class="data row0 col1">80.907183</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row0_col2" class="data row0 col2">80.945643</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row0_col3" class="data row0 col3">80.912451</td>
            </tr>
            <tr>
                        <th id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9level0_row1" class="row_heading level0 row1">Cabrera High School</th>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row1_col0" class="data row1 col0">83.676136</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row1_col1" class="data row1 col1">84.253219</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row1_col2" class="data row1 col2">83.788382</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row1_col3" class="data row1 col3">84.287958</td>
            </tr>
            <tr>
                        <th id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9level0_row2" class="row_heading level0 row2">Figueroa High School</th>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row2_col0" class="data row2 col0">81.198598</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row2_col1" class="data row2 col1">81.408912</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row2_col2" class="data row2 col2">80.640339</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row2_col3" class="data row2 col3">81.384863</td>
            </tr>
            <tr>
                        <th id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9level0_row3" class="row_heading level0 row3">Ford High School</th>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row3_col0" class="data row3 col0">80.632653</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row3_col1" class="data row3 col1">81.262712</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row3_col2" class="data row3 col2">80.403642</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row3_col3" class="data row3 col3">80.662338</td>
            </tr>
            <tr>
                        <th id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9level0_row4" class="row_heading level0 row4">Griffin High School</th>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row4_col0" class="data row4 col0">83.369193</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row4_col1" class="data row4 col1">83.706897</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row4_col2" class="data row4 col2">84.288089</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row4_col3" class="data row4 col3">84.013699</td>
            </tr>
            <tr>
                        <th id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9level0_row5" class="row_heading level0 row5">Hernandez High School</th>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row5_col0" class="data row5 col0">80.866860</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row5_col1" class="data row5 col1">80.660147</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row5_col2" class="data row5 col2">81.396140</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row5_col3" class="data row5 col3">80.857143</td>
            </tr>
            <tr>
                        <th id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9level0_row6" class="row_heading level0 row6">Holden High School</th>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row6_col0" class="data row6 col0">83.677165</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row6_col1" class="data row6 col1">83.324561</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row6_col2" class="data row6 col2">83.815534</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row6_col3" class="data row6 col3">84.698795</td>
            </tr>
            <tr>
                        <th id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9level0_row7" class="row_heading level0 row7">Huang High School</th>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row7_col0" class="data row7 col0">81.290284</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row7_col1" class="data row7 col1">81.512386</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row7_col2" class="data row7 col2">81.417476</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row7_col3" class="data row7 col3">80.305983</td>
            </tr>
            <tr>
                        <th id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9level0_row8" class="row_heading level0 row8">Johnson High School</th>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row8_col0" class="data row8 col0">81.260714</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row8_col1" class="data row8 col1">80.773431</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row8_col2" class="data row8 col2">80.616027</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row8_col3" class="data row8 col3">81.227564</td>
            </tr>
            <tr>
                        <th id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9level0_row9" class="row_heading level0 row9">Pena High School</th>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row9_col0" class="data row9 col0">83.807273</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row9_col1" class="data row9 col1">83.612000</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row9_col2" class="data row9 col2">84.335938</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row9_col3" class="data row9 col3">84.591160</td>
            </tr>
            <tr>
                        <th id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9level0_row10" class="row_heading level0 row10">Rodriguez High School</th>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row10_col0" class="data row10 col0">80.993127</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row10_col1" class="data row10 col1">80.629808</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row10_col2" class="data row10 col2">80.864811</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row10_col3" class="data row10 col3">80.376426</td>
            </tr>
            <tr>
                        <th id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9level0_row11" class="row_heading level0 row11">Shelton High School</th>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row11_col0" class="data row11 col0">84.122642</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row11_col1" class="data row11 col1">83.441964</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row11_col2" class="data row11 col2">84.373786</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row11_col3" class="data row11 col3">82.781671</td>
            </tr>
            <tr>
                        <th id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9level0_row12" class="row_heading level0 row12">Thomas High School</th>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row12_col0" class="data row12 col0">83.728850</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row12_col1" class="data row12 col1">84.254157</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row12_col2" class="data row12 col2">83.585542</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row12_col3" class="data row12 col3">83.831361</td>
            </tr>
            <tr>
                        <th id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9level0_row13" class="row_heading level0 row13">Wilson High School</th>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row13_col0" class="data row13 col0">83.939778</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row13_col1" class="data row13 col1">84.021452</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row13_col2" class="data row13 col2">83.764608</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row13_col3" class="data row13 col3">84.317673</td>
            </tr>
            <tr>
                        <th id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9level0_row14" class="row_heading level0 row14">Wright High School</th>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row14_col0" class="data row14 col0">83.833333</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row14_col1" class="data row14 col1">83.812757</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row14_col2" class="data row14 col2">84.156322</td>
                        <td id="T_8daf7eb0_a90d_11ea_b01d_8863df8cd0c9row14_col3" class="data row14 col3">84.073171</td>
            </tr>
    </tbody></table>


### Scores by School Spending

* A table breaking down school performances based on average Spending Ranges (Per Student) and grouping schools into four reasonable bins was generated. The table includes each of the following metrics:

  * Average Math Score
  * Average Reading Score
  * % Passing Math
  * % Passing Reading
  * % Overall Passing
 
The table showcasing Scores by School Spending appears in the following manner:
 
<table id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9"><thead>    <tr>        <th class="blank level0"></th>        <th class="col_heading level0 col0">Average Math Score</th>        <th class="col_heading level0 col1">Average Reading Score</th>        <th class="col_heading level0 col2">% Passing Math</th>        <th class="col_heading level0 col3">% Passing Reading</th>        <th class="col_heading level0 col4">% Overall Passing</th>    </tr>    <tr>        <th class="index_name level0">Per Student Budget</th>        <th class="blank"></th>        <th class="blank"></th>        <th class="blank"></th>        <th class="blank"></th>        <th class="blank"></th>    </tr></thead><tbody>
                <tr>
                        <th id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9level0_row0" class="row_heading level0 row0">&lt;$584</th>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row0_col0" class="data row0 col0">83.36</td>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row0_col1" class="data row0 col1">83.96</td>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row0_col2" class="data row0 col2">93.70</td>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row0_col3" class="data row0 col3">96.69</td>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row0_col4" class="data row0 col4">90.64</td>
            </tr>
            <tr>
                        <th id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9level0_row1" class="row_heading level0 row1">$585-629</th>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row1_col0" class="data row1 col0">79.98</td>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row1_col1" class="data row1 col1">82.31</td>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row1_col2" class="data row1 col2">79.11</td>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row1_col3" class="data row1 col3">88.51</td>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row1_col4" class="data row1 col4">70.94</td>
            </tr>
            <tr>
                        <th id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9level0_row2" class="row_heading level0 row2">$630-644</th>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row2_col0" class="data row2 col0">77.82</td>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row2_col1" class="data row2 col1">81.30</td>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row2_col2" class="data row2 col2">70.62</td>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row2_col3" class="data row2 col3">82.60</td>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row2_col4" class="data row2 col4">58.84</td>
            </tr>
            <tr>
                        <th id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9level0_row3" class="row_heading level0 row3">$645-675</th>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row3_col0" class="data row3 col0">77.05</td>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row3_col1" class="data row3 col1">81.01</td>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row3_col2" class="data row3 col2">66.23</td>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row3_col3" class="data row3 col3">81.11</td>
                        <td id="T_2f442c12_a94a_11ea_ac65_8863df8cd0c9row3_col4" class="data row3 col4">53.53</td>
            </tr>
    </tbody></table> 


### Scores by School Size

* A table created by grouping schools based on a reasonable approximation of school size (Small, Medium, Large) appears in the following manner. 

 The table includes the following metrics:
 
<table id="T_477df728_a949_11ea_ac65_8863df8cd0c9"><thead>    <tr>        <th class="blank level0"></th>        <th class="col_heading level0 col0">Average Math Score</th>        <th class="col_heading level0 col1">Average Reading Score</th>        <th class="col_heading level0 col2">% Passing Math</th>        <th class="col_heading level0 col3">% Passing Reading</th>        <th class="col_heading level0 col4">% Overall Passing</th>    </tr>    <tr>        <th class="index_name level0">Total Students</th>        <th class="blank"></th>        <th class="blank"></th>        <th class="blank"></th>        <th class="blank"></th>        <th class="blank"></th>    </tr></thead><tbody>
                <tr>
                        <th id="T_477df728_a949_11ea_ac65_8863df8cd0c9level0_row0" class="row_heading level0 row0">Small (&lt;1000)</th>
                        <td id="T_477df728_a949_11ea_ac65_8863df8cd0c9row0_col0" class="data row0 col0">83.828654</td>
                        <td id="T_477df728_a949_11ea_ac65_8863df8cd0c9row0_col1" class="data row0 col1">83.828654</td>
                        <td id="T_477df728_a949_11ea_ac65_8863df8cd0c9row0_col2" class="data row0 col2">93.952484</td>
                        <td id="T_477df728_a949_11ea_ac65_8863df8cd0c9row0_col3" class="data row0 col3">96.040317</td>
                        <td id="T_477df728_a949_11ea_ac65_8863df8cd0c9row0_col4" class="data row0 col4">90.136789</td>
            </tr>
            <tr>
                        <th id="T_477df728_a949_11ea_ac65_8863df8cd0c9level0_row1" class="row_heading level0 row1">Medium (1000-2000)</th>
                        <td id="T_477df728_a949_11ea_ac65_8863df8cd0c9row1_col0" class="data row1 col0">83.372682</td>
                        <td id="T_477df728_a949_11ea_ac65_8863df8cd0c9row1_col1" class="data row1 col1">83.372682</td>
                        <td id="T_477df728_a949_11ea_ac65_8863df8cd0c9row1_col2" class="data row1 col2">93.616522</td>
                        <td id="T_477df728_a949_11ea_ac65_8863df8cd0c9row1_col3" class="data row1 col3">96.773058</td>
                        <td id="T_477df728_a949_11ea_ac65_8863df8cd0c9row1_col4" class="data row1 col4">90.624267</td>
            </tr>
            <tr>
                        <th id="T_477df728_a949_11ea_ac65_8863df8cd0c9level0_row2" class="row_heading level0 row2">Large (2000-5000)</th>
                        <td id="T_477df728_a949_11ea_ac65_8863df8cd0c9row2_col0" class="data row2 col0">77.477597</td>
                        <td id="T_477df728_a949_11ea_ac65_8863df8cd0c9row2_col1" class="data row2 col1">77.477597</td>
                        <td id="T_477df728_a949_11ea_ac65_8863df8cd0c9row2_col2" class="data row2 col2">68.652380</td>
                        <td id="T_477df728_a949_11ea_ac65_8863df8cd0c9row2_col3" class="data row2 col3">82.125158</td>
                        <td id="T_477df728_a949_11ea_ac65_8863df8cd0c9row2_col4" class="data row2 col4">56.574046</td>
            </tr>
    </tbody></table>

### Scores by School Type

*  A solution was created to group schools based on school type (Charter vs. District). The table includes the following metrics:

A table of Scores by School Type looks as follows:

<table id="T_498fe534_a94a_11ea_ac65_8863df8cd0c9"><thead>    <tr>        <th class="blank level0"></th>        <th class="col_heading level0 col0">Average Math Score</th>        <th class="col_heading level0 col1">Average Reading Score</th>        <th class="col_heading level0 col2">% Passing Math</th>        <th class="col_heading level0 col3">% Passing Reading</th>        <th class="col_heading level0 col4">% Overall Passing</th>    </tr>    <tr>        <th class="index_name level0">Type of School</th>        <th class="blank"></th>        <th class="blank"></th>        <th class="blank"></th>        <th class="blank"></th>        <th class="blank"></th>    </tr></thead><tbody>
                <tr>
                        <th id="T_498fe534_a94a_11ea_ac65_8863df8cd0c9level0_row0" class="row_heading level0 row0">Charter</th>
                        <td id="T_498fe534_a94a_11ea_ac65_8863df8cd0c9row0_col0" class="data row0 col0">83.406183</td>
                        <td id="T_498fe534_a94a_11ea_ac65_8863df8cd0c9row0_col1" class="data row0 col1">83.406183</td>
                        <td id="T_498fe534_a94a_11ea_ac65_8863df8cd0c9row0_col2" class="data row0 col2">93.701821</td>
                        <td id="T_498fe534_a94a_11ea_ac65_8863df8cd0c9row0_col3" class="data row0 col3">96.645891</td>
                        <td id="T_498fe534_a94a_11ea_ac65_8863df8cd0c9row0_col4" class="data row0 col4">90.560932</td>
            </tr>
            <tr>
                        <th id="T_498fe534_a94a_11ea_ac65_8863df8cd0c9level0_row1" class="row_heading level0 row1">District</th>
                        <td id="T_498fe534_a94a_11ea_ac65_8863df8cd0c9row1_col0" class="data row1 col0">76.987026</td>
                        <td id="T_498fe534_a94a_11ea_ac65_8863df8cd0c9row1_col1" class="data row1 col1">76.987026</td>
                        <td id="T_498fe534_a94a_11ea_ac65_8863df8cd0c9row1_col2" class="data row1 col2">66.518387</td>
                        <td id="T_498fe534_a94a_11ea_ac65_8863df8cd0c9row1_col3" class="data row1 col3">80.905249</td>
                        <td id="T_498fe534_a94a_11ea_ac65_8863df8cd0c9row1_col4" class="data row1 col4">53.695878</td>
            </tr>
    </tbody></table>
