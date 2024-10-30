# Analysis-of-PBJ-Nurse-Staffing-2024Q1

## Sections

- [About](#about)
- [Analysis and Visualization](#analysis)
- [Findings](#findings)

## About <a id="about"></a>

My full jupyter notebook [file](https://github.com/RobCaamano/Analysis-of-PBJ-Nurse-Staffing-2024Q1/blob/main/Analysis%20of%20PBJ%20Nurse%20Staffing%202024Q1.ipynb) and [report](https://github.com/RobCaamano/Analysis-of-PBJ-Nurse-Staffing-2024Q1/blob/main/Analysis%20of%20PBJ%20Nurse%20Staffing%202024Q1.pdf) can be found within this repository.

The [*Payroll Based Journal Daily Nurse Staffing*](https://data.cms.gov/quality-of-care/payroll-based-journal-daily-nurse-staffing/data?query=%7B%22filters%22%3A%7B%22rootConjunction%22%3A%7B%22label%22%3A%22And%22%2C%22value%22%3A%22AND%22%7D%2C%22list%22%3A%5B%5D%7D%2C%22keywords%22%3A%22%22%2C%22offset%22%3A0%2C%22limit%22%3A10%2C%22sort%22%3A%7B%22sortBy%22%3A%22Hrs_RNDON_emp%22%2C%22sortOrder%22%3A%22ASC%22%7D%2C%22columns%22%3A%5B%5D%7D) dataset consists of **33** columns and **1,330,965** entries, detailing the daily staffing hours of various categories of nurses across healthcare facilities for the most recent quarter available (2024Q1). It captures information about both directly employed nursing staff and those who are contracted, making it a valuable resource for analyzing nursing workforce patterns and staffing levels.

By exploring variations in nurse staffing we can gain insights into the optimal staffing configurations that promote better patient outcomes. The geographic identifiers included in the dataset allow for spatial analyses, enabling us to assess how staffing levels vary by location and to investigate disparities in nursing care across different regions.

#### The following are the categories of nurses:
|  |  |  |  |  |  |  |
| - | - | - | - | - | - | - |
| Registered Nurses | Registered Nurse Admins | Licensed Practical Nurses | Licensed Practical Nurse Admins | Certified Nursing Assistants | Nursing Assistant in Training | Medication Aides |

#### The following are all the columns and short descriptions:

| Column | Description |
| -------|------------ |
| PROVNUM | Provider number, a unique identifier for each provider |
| PROVNAME | Provider name, indicating the name of the healthcare facility |
| CITY | The city where the provider is located |
|STATE | The state where the provider operates |
| COUNTY_NAME | Name of the county where the provider is located |
| COUNTY_FIPS | Federal Information Processing Standard (FIPS) code for the county |
| CY_Qtr | Calendar Year Quarter, indicating the quarter of the year |
| WorkDate | The work date, typically in a numeric or timestamp format |
| MDScensus | MDS (Minimum Data Set) census, likely indicating the number of patients |
| Hrs_RNDON | Total hours worked by Registered Nurses (RN) on duty |
| Hrs_RNDON_emp	| Total hours worked by Registered Nurses employed directly by the provider |
| Hrs_RNDON_ctr	| Total hours worked by contracted Registered Nurses on duty |
| Hrs_RNadmin | Total hours worked by Registered Nurse Administrators |
| Hrs_RNadmin_emp | Hours worked by RN administrators employed directly by the provider |
| Hrs_RNadmin_ctr | Hours worked by contracted RN administrators |
| Hrs_RN | Total hours worked by all Registered Nurses |
| Hrs_RN_emp | Hours worked by employed Registered Nurses |
| Hrs_RN_ctr | Hours worked by contracted Registered Nurses |
| Hrs_LPNadmin | Hours worked by Licensed Practical Nurse (LPN) administrators |
| Hrs_LPNadmin_emp | Hours worked by employed LPN administrators |
| Hrs_LPNadmin_ctr | Hours worked by contracted LPN administrators |
| Hrs_LPN | Total hours worked by Licensed Practical Nurses |
| Hrs_LPN_emp | Hours worked by employed Licensed Practical Nurses |
| Hrs_LPN_ctr | Hours worked by contracted Licensed Practical Nurses |
| Hrs_CNA | Total hours worked by Certified Nursing Assistants (CNAs) |
| Hrs_CNA_emp | Hours worked by employed Certified Nursing Assistants |
| Hrs_CNA_ctr | Hours worked by contracted Certified Nursing Assistants |
| Hrs_NAtrn | Total hours worked by Nursing Assistants in training |
| Hrs_NAtrn_emp | Hours worked by employed Nursing Assistants in training |
| Hrs_NAtrn_ctr | Hours worked by contracted Nursing Assistants in training |
| Hrs_MedAide | Total hours worked by Medication Aides |
| Hrs_MedAide_emp | Hours worked by employed Medication Aides |
| Hrs_MedAide_ctr | Hours worked by contracted Medication Aides |

## Analysis and Visualization <a id="analysis"></a>

### Registered Nurse Hours per State

The following stacked bar graph visualizes the hours among directly employed Registered Nurses (RNs) and contracted RNs in each state. Each bar represents a state's total hours, featuring dark blue for contracted RNs and light blue for employed RNs. The chart is sorted in descending order based on the total hours worked, providing a clear view of where the most nursing hours are concentrated.

![Total Hours Worked by RNs Per State](https://github.com/user-attachments/assets/680222c8-9dfb-4068-9add-4da79bebe7d0)

### States With Highest Percentage of Contracted RNs

The following pie charts display the top 10 states with the highest percentage of contracted RNs to directly employed RNs. Each chart illustrates the distribution of hours worked between contracted and employed RNs, highlighting the higher reliance on contracted staffing across different states.

![States With Highest Percentage of Contracted RNs](https://github.com/user-attachments/assets/1e44ba7d-c50e-4c77-a811-8450028b9b03)

### States With Lowest Percentage of Contracted RNs

The following pie charts display the 10 states with the lowest percentage of contracted RNs to directly employed RNs. Each chart reveals the distribution of hours worked between contracted and employed RNs in these states, illustrating the lower reliance on contracted staffing in contrast to their counterparts.

![States With Lowest Percentage of Contracted RNs](https://github.com/user-attachments/assets/45b74796-5bda-4490-928c-1f1dbc56230e)

### Registered Nurse Hours per Month

The following stacked bar graph illustrates the total hours worked by RNs within the current quarter. Employed RNs are represented in dark blue, while contracted RNs are shown in light blue. This visual comparison allows for an understanding of the distribution of nursing hours, highlighting the relative contributions of employed versus contracted staff during this quarter.

![Total Hours Worked by RNs per Month - Bar Graph](https://github.com/user-attachments/assets/7efc6556-28df-495b-bdbc-c53a3a55a289)

- Employed RNs work 10.6 times more than contracted RNs

With access to historical data, the use of a line graph could highlight trends over time. However, when only using 2024Q1 the plot does not produce a good visual. Focusing solely on the data from 2024Q1 limits the visualization's effectiveness, as it may not adequately convey meaningful patterns or changes. For this reason, a stacked bar graph provides a clearer representation of the distribution of hours worked by employed and contracted RNs within that specific quarter.

![Total Hours Worked by RNs per Month - Line Graph](https://github.com/user-attachments/assets/c3ec1b70-29e7-4990-a94f-9f8e2b944b48)

### Top Providers' Hours for Contracted Registered Nurses

The following bar graph focuses on the top providers within the dataset, specifically highlighting the 20 providers with the highest total hours worked. By grouping the data by provider, we can identify the key players in terms of staffing levels, offering insights into which facilities rely more heavily on contracted nursing staff.

![Total Hours Worked by Contracted RNs for Top 20 Providers](https://github.com/user-attachments/assets/113950f0-1f51-468a-9805-6255872f8f8b)

### Bottom Providers' Hours for Contracted Registered Nurses

The following bar graph focuses on the bottom providers within the dataset, specifically highlighting the 20 providers with the lowest total hours worked. This offers insights into which facilities rely almost entirely on directly employed staff.

- Number of providers with less than 24 total hours: 9295

![Total Hours Worked by Contracted RNs for Bottom 20 Providers](https://github.com/user-attachments/assets/0f21e9b1-2ea3-4706-bd7f-309e2004d604)

### Mean Providers' Hours for Contracted Registered Nurses

The following bar graph emphasizes the mean providers within the dataset by showcasing the 20 providers whose hours worked are closest to the average. This method offers insights into the typical workload for contracted RNs across different facilities, highlighting those that operate near the mean.

- Mean hours worked by contracted RNs: 273

![Total Hours Worked by Contracted RNs for Providers Around the Mean](https://github.com/user-attachments/assets/f0e70e34-b64b-453c-bdbb-6ca8b1c6e216)

### Hours Worked for Each Contracted Group

The following pie chart shows the distribution of hours worked among all contracted nursing groups, providing a clear visual representation of how total hours are allocated across different categories. This chart highlights the proportion of hours contributed by each group, allowing for an easy comparison of workload distribution among contracted nurses.

![Hours Worked by Contracted Group](https://github.com/user-attachments/assets/eb09a218-98ed-4cc8-9c4a-a6c44ceaa23b)

## Findings <a id="findings"></a>

### Optimizing Staffing State-Wide

Analyzing the total hours worked by registered nurses (RNs) across various states provides critical insights into staffing needs. The top 5 states with the most total hours are as follows (values have been rounded to the nearest hour).

| State | Contracted Hours | Employed Hours | Total Hours |
| - | - | - | - |
|NY | 776,878 | 3,639,189 | 4,416,067 |
|CA | 85,274 | 3,347,767 | 3,433,042 |
|FL | 107,718 | 3,168,570 | 3,276,288 |
|PA | 411,631 | 2,421,978 | 2,833,609 |
|IL | 369,883 | 2,408,731 | 2,778,614 |

**Fig. 1.** reveals that New York leads with a substantial margin of **983,025 total** hours over the next highest state (CA), indicating a pronounced reliance on nursing services. New York also stands out with a substantial margin of **365,247** total hours of contracted work over the next highest state (PA). This data emphasizes the necessity for ensuring an adequate supply of contracted RNs in high-demand states like New York, California, Florida, Pennsylvania, and Illinois, where total hours worked are substantial.

In terms of market potential, **Fig. 2.** highlights states with the highest percentages of contracted RNs. New York exhibits a **17.6%** contracted to employed RN ratio, followed by Massachussets (**17.1%**), Delaware (**16.5%**), Oregon (**16.1%**) and Maine (**15.5%**). Despite New York’s large total hours, the relatively modest percentage of contracted RNs suggests that there is significant room for growth in this segment. Targeting recruitment efforts in these states could substantially increase market share and ability to meet local nursing demands.

Conversely, **Fig. 3.** identifies states with the lowest percentages of contracted RNs, notably Alabama and Puerto Rico, each at a mere **1.8%**, followed by Louisiana (**1.9%**) and Texas (**2.3%**). At fifth, California, with **2.5%** contracted RNs, presents a contrast; while it holds the second-highest total hours of RN work, its low percentage of contracted RNs highlights a potential market gap. This warrants further investigation into the barriers preventing a more extensive use of contracted RNs in these areas. Outreach programs should be considered in these states to educate healthcare facilities on the flexibility and cost-effectiveness of contracting RNs.

Focusing on California and Florida as investment opportunities could be beneficial given their total hours worked. Despite Florida ranking third for total hours at **107,718**, it has the tenth lowest percentage of contracted RNs. This discrepancy signifies a valuable opportunity for growth. In California, while the total hours are substantial, the low percentage of contracted RNs suggests potential for expanding contracted services to fulfill the apparent demand.

Overall, optimizing staffing state-wide involves not only targeting high-demand states with robust total hours worked but also addressing regions with low contracted RN usage through strategic marketing and education initiatives. By aligning recruitment strategies with data-driven insights from total hours and contracted RN percentages, service delivery and the impact on the nursing landscape in these states can be significantly enhanced.

### Provider Performance Insights

**Fig. 6.** provides a comprehensive analysis of provider performance, highlighting both the top-performing facilities. The top five providers by total hours worked by contracted RNs include Workmens Circle Multicare Center (**29,469**), The Plaza Rehab and Nursing Center (**22,796**), Franklin Center for Rehabilitation and Nursing (**21,670**), New York Center for Rehabilitation & Nursing (**20,377**), and Queens Boulevard Extended Care Facility (**16,297.75**). These providers not only demonstrate high engagement in contracted RN hours but also reflect an established operational framework conducive to effective staffing solutions. Strengthening partnerships with these high-performing providers can significantly enhance service delivery and client satisfaction, ultimately leading to improved outcomes for the healthcare facilities they serve.

On the other hand, **Fig. 7.** presents insights into the bottom-performing providers, such as Canyon Springs Post-Acute, Callaway Good Life Center, Wynwood Rehabilitation and Healthcare Center, Shepherd of The Valley-Boardman, and Shepherd of the Valley Howland. All of these providers logged at most **1** hour of contracted RN service and represent the lower end of the performance spectrum. Notably, there are **9,295** providers with fewer than **24** total hours, indicating a substantial number of facilities underutilizing contracted RNs. This presents an opportunity consider strategies for improvement or phasing out underperforming providers to maintain quality service standards.

**Fig. 8.** displays some of the average providers. The mean hours worked by contracted RNs stands at **273** hours, which underscores the performance disparities across providers. Facilities that exceed this average, particularly those seen in **Fig. 6.**, can be pivotal in identifying best practices that lead to successful outcomes. Sharing insights and strategies from these high-performing providers can foster a culture of continuous improvement across all facilities. Implementing performance benchmarking and regular assessments will allow targeted goals for underperforming providers, encouraging them to adopt successful strategies utilized by their higher-performing counterparts.

The analysis of provider performance reveals critical insights that can guide decision-making processes. By bolstering relationships with successful providers, investigating the causes behind underperformance, and promoting the usage of best practices, the overall efficacy of contracted RN services can be enhanced, leading to better healthcare delivery and higher levels of client satisfaction.

### Evaluating Contracted Groups

The analysis presented in **Fig. 9.** provides a detailed breakdown of hours worked by various contracted nursing groups, offering insights into their effectiveness and potential areas for prioritization. The data reveals that Certified Nursing Assistants (CNAs) dominate the workforce, accounting for **56.4%** of the total hours worked. Given their substantial contribution, strategies to enhance their training, support, and retention to ensure continued quality care should be considered. Licensed Practical Nurses (LPNs) contribute **28.1%** of total hours worked, making them a significant group within the contracted workforce.

Registered Nurses (RNs), while still an important group, represent **12.8%** of the total hours. This lower percentage could reflect an underutilization of RNs within contracted services. Staffing models may need to be reassessed to ensure RNs are deployed effectively, potentially expanding their roles to take on more complex patient care tasks that align with their training.

Registered Nurse Administrators (RN Admins) and Medication Aides (Med Aides) contribute minimally, accounting for **1.1%** and **1.0%** of total hours, respectively. This suggests that these roles may not be fully utilized within current contracted frameworks. 

The data also indicates a very small fraction of hours attributed to Nursing Assistant in Training (NA, Training) and Licensed Practical Nurse Administrators (LPN Admins), both at just **0.3%**. These groups may require additional focus to increase their effectiveness and support within healthcare settings.

Overall, evaluating the hours worked by each contracted group not only highlights the significant contributions of CNAs and LPNs but also underscores potential areas for development within the RN and administrative roles. By strategically focusing on these areas, staffing efficiency, improved patient outcomes, and ultimately higher quality healthcare services can be improved.

### Historical Data

The analysis of historical data is crucial for enhancing decision-making through time series predictions. However, with the current dataset limited to 2024 Q1, performing such predictions is impossible. As demonstrated in **Fig. 4.**, the stacked bar graph indicates that employed Registered Nurses (RNs) work **10.6** times more hours than contracted RNs in this quarter. Integrating historical data could offer deeper insights into staffing trends and resource allocation over time.

**Fig. 5.** presents a line graph, which would be more effective if historical data were available. Time series analysis requires multiple data points over time to identify trends, seasonality, and cyclical patterns. By combining this dataset with past data, it becomes possible to make informed predictions about future staffing needs and contracted RN utilization.

To enhance the analytical capabilities of this dataset, the following suggestions could be considered for providing predictions:
1. **Linear Regression**: A straightforward approach, linear regression can model the relationship between the number of employed RNs and various independent variables such as patient volume, seasonal trends, and geographical factors. Although it assumes a linear relationship, it can serve as a baseline model and help identify key drivers of RN hours worked.
2. **Random Forests**: This ensemble learning method is excellent for regression tasks, as it can handle nonlinear relationships and interactions between variables. By using historical data on RN hours worked, staffing levels, and patient outcomes, a Random Forest model can provide insights into the factors that most influence RN utilization and predict future staffing needs with high accuracy.
3. **Gradient Boosting Machines (GBM)**: Similar to Random Forests, GBMs are powerful for regression tasks. They build models in a stage-wise fashion, optimizing for predictive accuracy. This technique can provide detailed insights into feature importance, allowing to prioritize factors that impact staffing efficiency.
4. **Neural Networks**: For more complex datasets, deep learning techniques can be employed. A neural network could capture intricate patterns in the data, potentially improving prediction accuracy for RN staffing levels

By utilizing machine learning algorithms, historical data can be analyzed more effectively, leading to better predictions of staffing needs. This, in turn, will enable proactive staffing strategies, ensuring that healthcare facilities have the necessary resources to meet patient demands efficiently. Combining multiple algorithms and validating them against historical outcomes can further enhance predictive accuracy and provide a comprehensive understanding of staffing dynamics.
