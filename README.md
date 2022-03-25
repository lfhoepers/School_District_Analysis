# School District Analysis

## Overview of the school district analysis

This project's main objective is to analyze and deliver data on how students are behaving by district, school, spent range, by size, etc.
In addition to this main analysis, evidence of diapering was also found in the grades of Thomas High School ninth graders. With this, it was requested to remove these notes from the total analysis to have a more honest data.

The following files were used for this analysis, which can be downloaded here:

[Schools_Complete.csv](https://github.com/lfhoepers/School_District_Analysis/blob/137024a0de4837dbbc6cc1a094f9b585ef9b270a/Resources/schools_complete.csv) 

[Students Complete.csv](https://github.com/lfhoepers/School_District_Analysis/blob/137024a0de4837dbbc6cc1a094f9b585ef9b270a/Resources/students_complete.csv)

This project was fully developed in Python using Pandas and Numpy, code can be checked at the following link:

[PyCitySchools_Challenge.ipynb](https://github.com/lfhoepers/School_District_Analysis/blob/137024a0de4837dbbc6cc1a094f9b585ef9b270a/PyCitySchools_Challenge.ipynb)

- Codes used to change the grades of Students 9th Thomas High School to nan

student_data_df.loc[(student_data_df["grade"] == "9th") & (student_data_df["school_name"] == "Thomas High School"),"reading_score"] = np.nan  

student_data_df.loc[(student_data_df["grade"] == "9th") & (student_data_df["school_name"] == "Thomas High School"),"math_score"] = np.nan  

- Code used to new Student Count

**Step 1. Get the number of students that are in ninth grade at Thomas High School.**
**These students have no grades.**

student_count_9 = school_data_complete_df.loc[(school_data_complete_df["grade"] == "9th") & (school_data_complete_df["school_name"] == "Thomas High School"),"Student ID"].count() 

**Get the total student count**

student_count = school_data_complete_df["Student ID"].count()


**Step 2. Subtract the number of students that are in ninth grade at**
**Thomas High School from the total student count to get the new total student count.**

student_count = student_count - student_count_9
student_count


## Results:

- How is the district summary affected?

The overall and percentages were not affected by the withdrawal of Grade 9 students from the Thomas School. We can only see the old and the new analysis with the difference of 461 fewer students.

Before

![image](https://user-images.githubusercontent.com/100812079/160037820-673a6079-a295-44b7-9b46-986b32f05157.png)

After

![image](https://user-images.githubusercontent.com/100812079/160037931-3b18052a-ca7b-4e47-b602-b2dd751270a4.png)

- How is the school summary affected?

School summary only affected a small amount of Math, reading and overall percentages.

Before

![image](https://user-images.githubusercontent.com/100812079/160038748-9efa2841-cad0-429e-b63f-e3e6d6f3d1f1.png)

After

![image](https://user-images.githubusercontent.com/100812079/160038790-d2d5517d-cf3c-4c9f-b0cd-02e20bb21191.png)


- How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?

As we can see, there were no big changes in the final values, some variations such as %Passing reading and math that after the change Thomas High School dropped to 3rd. Place. However in the Overal it continued in 2nd. place.

Before

![image](https://user-images.githubusercontent.com/100812079/160039603-b9ee88ee-3f46-4c4d-82a0-8b5022e1566e.png)

After

![image](https://user-images.githubusercontent.com/100812079/160039710-79c92a27-1dea-4e40-809d-7815e409d660.png)

## How does replacing the ninth-grade scores affect the following:

- Math and reading scores by grade

As we only cut the ninth-grade scores from Thomas High School, the diference only appear on this school and grade.

![image](https://user-images.githubusercontent.com/100812079/160040515-2f42efe0-88d0-4ad7-a5c4-f1dc781f4110.png)

- Scores by school spending

Decrease Overall

Before

![image](https://user-images.githubusercontent.com/100812079/160041475-234842b2-1a78-4f6a-b422-9a3ee75920a4.png)

After

![image](https://user-images.githubusercontent.com/100812079/160041401-c16225d9-d912-4131-8113-6a8507869a30.png)


- Scores by school size

Decrease Overall

Before

![image](https://user-images.githubusercontent.com/100812079/160041774-9fbd75cb-5460-4590-9e26-4060e9d4470f.png)


After

![image](https://user-images.githubusercontent.com/100812079/160041873-56692d19-eadc-46bb-9ad9-57668295aed3.png)

- Scores by school type

Decrease Overall

Before

![image](https://user-images.githubusercontent.com/100812079/160041994-98d91686-4f45-4f87-bfe1-b4abf314a4da.png)

After

![image](https://user-images.githubusercontent.com/100812079/160042052-b58e12bf-f5c0-4b7d-92ad-151a59cf837c.png)


## Summary: 

Summarize four changes in the updated school district analysis after reading and math scores for the ninth grade at Thomas High School have been replaced with NaNs.

- Total Students decreased to 38709 instead 39170;
- %overall Passing scores by school type charter decreased 90.392533 instead 90.432244;
- %overall passing scores by school size medium decreased 90.557997 instead 90.621535;
- %overall passing scores by spending ranges(per Student) 631-645 decreased 62.778233 instead 62.857656;


I appreciate the opportunity to present this project, I am available for any clarification.

**Luiz Fernando Hoepers**  
###### UofT SCS Data Analytics Boot Camp
