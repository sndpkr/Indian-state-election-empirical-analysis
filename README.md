# Indian-state-election-empirical-analysis
## AN EMPIRICAL ANALYSIS OF INDIAN STATE ASSEMBLY ELECTION DATA. 
Repository for my M.S. Project completed under the supervision of Dr. Wasim Ahmad \
Project submitted- 26-04-2022 \
\
Abstract
--
How do candidates allocate their campaign resources? Using data of over 1.1 million individual items expenditure which is submitted by candidates who ran for Bihar Assembly seats 2020. We provide a detailed picture of how candidates allocate their limited resources among different categories of activities to examine the potential relationships between Total Votes received by an individual candidate with their expenditure habits, Fund received by the public, and their respective political parties. We have analyzed the Expenditure pattern of more than 1100 individual candidates to derive the result by using the Multiple Regression with logarithmic transformation. We have used the Position/Rank Gender of the candidate as conditional variables. The results (1) show a minor or unreliable relationship between some of the expenditure variables. There was also multicollinearity in the result (1) to solve that we used Principal Component Analysis (PCA) to find out the maximum no of variables required to explain the dependent variable which is Log(Total Votes). To identify those variables, we used recursive feature elimination (RFE) to select features by recursively considering smaller and smaller sets of features. The findings of this study will be of interest to educators, political consultants as well as researchers. It could help the political consultants or an individual to comment on the expenditure habits of an election candidate in order to gain more Votes than the expected number of votes.

\
**Introduction**
--
Electoral campaigns design strategies to gain more votes and win elected offices. Although this claim is straightforward and simple, there is still a great deal of uncertainty about what constitutes the most effective strategy to secure those goals. A researcher and a campaign operative Richard Fenno, told that told that “Seventy-five percent of all the money we spend in a campaign is wasted. But we don’t know which 75 percent” 
The Total votes received by an individual candidate after the election campaign are not only related to his/her campaign expenditure but also to influence power and public support for that individual. Which is an alternate way of saying how much one can generate funds from public. Sometimes also the face of a political party matters a lot. This helps them to do effective campaigning with Political stars and here we have that variable as total expenditure on public meetings with stars (PMS). There are also some secondary factors like gender and cast. 
It is important to examine candidates’ resource allocation decisions to understand the underlying relationship between campaign spending and electoral outcomes. The effectiveness of campaigns on electoral outcomes critically hinges on how candidates allocate their limited resources depending on electoral landscapes. 
In this paper, we take advantage of detailed campaign expenditure reports posted by the Election Commission of India (ECI) to provide a comprehensive description of campaign resource allocations and to examine which factor of expenditure was more significant in the 2020 Bihar assembly election, the ECI has required candidates, to disclose their daily operating expenditures and at the end of the election, he/she should submit aggregate expenditure list within a week. This expenditure data includes information on when, why, and where each campaign spent its funds along with how much was spent. For this paper, we use data for expenditures made in the Bihar Assembly races for 2020. In total, there were over 1.1 million observations of unique expenditures among the Assembly seat races. We focus on expenditures that were made by campaigns of candidates more effective and significant. We classify the expenditures in one of six categories: Public Meeting with Star (PMS), Public Meeting Non-Star (PMNS), Media (M), Vehicle (V), Campaign Worker salary (CW), and fundraising or Another Person Fund (APF). 
First, in contrast to conventional wisdom, we find that there is significant variation in the allocation of campaign resources across candidates. Although the spending limit for Assembly constituencies was hiked from Rs 20 lakh-Rs 28 lakh to Rs 28 lakh- Rs 40 lakh (depending on the state).

\
**Data and Data Sources**
--
We have used Cross-sectional data for different explanatory variables for the study from the Election commission of India. The independent variables that would be taken into account for research are:

PMS = Expenditure on Public Meeting with Star\        
PMNS = Expenditure on Public Meeting Non-Star (general meeting with campaign workers) \
M =   Expenditure on Media (Electronics and non-electronics media Advertisement)  \
V = Expenditure on Vehicle \
CW = Expenditure on Campaign Worker salary \
APF = Another Person Fund received \
With Position/Rank and Gender of candidate as dummy variables to calculate the Total Votes received by the candidates during the assembly election
Also, we have large data for all the independent variables mentioned above for the year 2020. The data are collected from Election commission of India.


**Key findings**
--
- First result
- --
![image](https://user-images.githubusercontent.com/45443887/165253071-776ee1dd-252e-4ee9-b177-0b18b94311dd.png)\
*Figure 1: Individual maximum spending in different segments of the election campaign

- --
- Second result
- --
![image](https://user-images.githubusercontent.com/45443887/165253521-5337dd1b-1f07-4325-a664-967fff8e5f92.png)\
*Figure 2: Individual maximum fundraising from different sources

- --
- Third result
- --
![image](https://user-images.githubusercontent.com/45443887/165256124-f1fe450f-1815-43e7-8c00-f9d623fe82c8.png)\
Figure 3:  Eigenvalue Vs n (number of feature variables) \
Eigenvalues are coefficients applied to eigenvectors that give the vectors their length or magnitude. So, PCA is a method that: Measures how each variable is associated with one another using a Covariance matrix. Understands the directions of the spread of our data using Eigenvectors. So, this graph explains that about six variables among them could explain the output variable lVotes, which is log (Total Votes).

- --
- Forth result
- --
![image](https://user-images.githubusercontent.com/45443887/165256827-2c3674af-5d60-4735-b563-55160c700a5d.png)

Table 1: It is a correlation matrix of (8X8) required variables\
From Table 1, we could figure out the six sufficient variables for the multiple regression analysis. Such that we should not have a multicollinearity issue in the result.

- --
Regression Model
--
The regression equation is: 

Log (Votes)i ~ β0 + β1(Position) + β2(Gender) + β3 Log (PMS)i + β4 Log (PMNS)i + β5Log (M)i + β6 Log (V)i+ β7 Log (CW)i + β8 Log (APF)i + €i \
Where,

PMS = Expenditure on Public Meeting with Star \     
PMNS = Expenditure on Public Meeting Non-Star (Self Meeting with campaign workers)\
M =   Expenditure on Media (Electronics and non-electronics media Advertisement)  \
V = Expenditure on Vehicle\
CW = Expenditure on Campaign Worker salary\
APF = Another Person Fund received\
Position is:
•	(p) if the ith individual position (p) is in the Result; p = {1,2,3,4,5} \
Gender is:
•	1 if the ith individual is Male
•	0 other wise\
Parameters:  β1, β2, β3, β4, β5, β6, β7, β8\
Null Hypothesis:  
𝐻0: 𝛽i = 0 for all i, where i = 1,2,3,4,5,6,7,8\
𝐻1: 𝛽i ≠0 for at least one i, where i = 1,2,3,4,5,6,7,8

Tests
--
Tests done for
Multicollinearity: To check multicollinearity by using we are using VIF- Variance Inflation Factor. It is important to check whether our data exhibit multicollinearity or not. VIF allows to check how strong corelation between the various independent variables. It is calculated by taking a variable and regressing it against every other variables. VIF calculates how much the variance of a coefficient is inflated because of its linear dependencies with other predictors. Hence its name.\
Table 2: VIF table

![image](https://user-images.githubusercontent.com/45443887/165258331-56b5e495-ca3e-41e2-8f02-cfe48fca2410.png)


VIF is calculated by using the following formula:
 
Where R2 is calculated by using OLS regression. Which explain the percentage of data being explained by that OLS regression.

Results and Discussions
--
**OLS Regression Results **

Result Table 2.1
	
![image](https://user-images.githubusercontent.com/45443887/165260158-76e0885c-fde4-4896-ac7c-321815b81568.png)

Result Table 2.2                                                                                      

![image](https://user-images.githubusercontent.com/45443887/165260355-c071b1ef-3bd4-486a-bc34-14cb21ea6bc1.png)

Result Table 2.3

![image](https://user-images.githubusercontent.com/45443887/165260545-ede956ac-1e1d-4776-9049-c5c35b31f4a5.png)
--


![image](https://user-images.githubusercontent.com/45443887/165261286-52a84855-93fc-4354-9d07-d19972368d55.png)

Figure 4: Representation of Actual vs Fitted Values

This graph shows how much our Fitted Value curve in (blue) deviates from the Actual Value curve in (red)



The Equation is:
--
log (Votes) = 10.50 - 0.19 x Position_2 - 1.54 x Position_3 - 2.37 x Position_4 - 2.77 x Position_5 + 0.11 x Sex_MALE + 0.021 x log (PMS)+ 0.008 x log (PMNS) + 0.012 x log (M) + 0.01 x log (V) + 0.006 x log (CW) + 0.006 x log (APF)

