# Exploratory Analysis on Mechanical Engineering Placement Data.


## Objective:
This project aims to discover patterns in the placement procedure during the academic year of 2022-23. The dataset was created internally by the Training and Placement Cell via Google Forms. The analysis searches for patterns like offers made by different companies during the process, distribution of students recruited off campus and on campus, etc. The tool used for cleaning and wrangling the dataset was Microsoft Excel. The findings were then plotted into charts on Power BI. And an interactive dashboard was created.


## About Dataset:
The data was collected by Training and Placement Cell from the individual students via Google Forms. The dataset includes details like, Name of the Student, Name of Recruiter, Year of Passing, PRN No, Roll No, Nature of Recruitment, Salary Package Offered, as well as some sensitive information like email addresses (which have been removed from the dataset for privacy). 


## Observations:
1. The dataset had a total row count of 49. The columns in the dataset were "Timestamp", "YEAR OF PASSING",  "FULL NAME", "CONTACT NUMBER", "E-MAIL ID(i.e. Used during Placement)", "PRN NO.", "BE-ROLL NO.(Eg.402X001)", "NATURE OF PLACEMENT", "NAME OF THE RECRUITER(Read the instructions given at the form description no.3)", "APPOINTMENT LETTER REFERENCE NO. WITH DATE",  "PACKAGE (E.g.:-4.0 LPA) ", "Average Package(LPA)", "Highest package(LPA)", "UPLOAD APPOINTMENT LETTER(Letter of Intent or Letter Of Recruitment)", "Trainings or Practice which you have gone through before the placement, Which actually helped you, in your Placements." 

2. "NAME OF THE RECRUITER" column had a few discrepancies, a few names of the companies were misspelt. 

3. A few entries in the column "PACKAGE (E.g.:-4.0 LPA)" had characters "LPA" added. Ex. "5.5LPA". 

4. The entire columns of "Highest package(LPA)" and "Average Package(LPA)" were empty.

5. A few values in "APPOINTMENT LETTER REFERENCE NO. WITH DATE" and "Trainings or Practice which you have gone through before the placement, Which actually helped you, in your Placements" were missing.


## Processing:
1. Remove irrelevant columns ie, Timestamp, Year of Passing, Contact Number, Email ID, PRN No., Roll No..
2. Rename column titles ie, Name of Recruiter.
3. Create a pivot table to find abnormalities in data.
	i. A few values in Name of Recruiters are repeated.
	ii. A few values in Sum of Package have values of 0.
4. To remove all the repeated Name of Recruiters with slight mistakes in names use conditional formatting to highlight them.
	i. After highlighting all the fields with mistaken names, use Find and Replace to replace all the incorrect names.
5. A few values in Package column contain string values, to convert all of them to Integer values, use Find and Replace. 
	i. Select the column of Package and select Find and Replace;
	ii. Find all the values that contains "LPA" and replace them with "".


## Manipulation:
1. Create a new column "No. of Offers per Student" that stores an Integer value of number of offers per student.
	i. Create a new empty column and use the formula, "=LEN(C#)-LEN(SUBSTITUTE(C#,",",""))+1";
2. Create Pivot Table:
	i. Company Pivot Table: Contains Unique Recruiter Name, Count of Pacakge and Average of Package'
	ii. No. of Offers Pivot Table: Contains Unique values of Number of Offers per Student and Frequency of Students.
	iii. Nature of Placemant Pivot Table: Contains Unique values of Nature of Placement(InCampus/OffCampus) and Count of Students.


## Visualization:
Tool used for plotting charts and creating dashboards was PowerBI. 
Charts plotted were:
1. Average Package Offered vs Companies,
2. Offers Made vs Companies,
3. Nature of Placement by Placed Students,
4. Number of Offers per Student by Placed Students.
A drop down filter was added to review the charts according to the companies.


## Findings and Conclusion:
1. It was found that the recruiter Cognizant hired the maximum number of students(15) in the year of 2022-23. The numbers of offers made by recruiters in decreasing order are, L&T Infotech, Hind Rectifiers, Kohler, TCS, Camgemini, Forvia Faurecia, Neilsoft, Reliance Industries Ltd.
2. The average pakage was offered by Forvia Faurecia & Reliance Industries Ltd.(5.5Lakhs INR pa). Companies in decreasing order of their average packages are Kohler, Capgemini, L&T Infotech, Cognizant, TCS, Hind Rectifiers, Neilsoft.
3. Of all the 49 placed students, 91.61% ie 44 students were recruited via incampus companies.
4. Majority of the students had a single offer from a particular company. Though 3 students had offers from two different companies. 
