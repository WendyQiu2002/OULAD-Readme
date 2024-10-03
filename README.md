# OULAD-Readme

## GENERAL INFORMATION

Open University Learning Analytics Dataset (OULAD) contains data about courses, students and their interactions with Virtual Learning Environment (VLE) for seven selected courses (called modules). Presentations of courses start in February and October - they are marked by “B” and “J” respectively. The dataset consists of tables connected using unique identifiers. All tables are stored in the csv format.

- Dataset administrators:
Jakub Kuzilek,
Martin Hlosta,
Zdenek Zdrahal.

- Address:
Knowledge Media Institute,
The Open University,
Milton Keynes,
MK7 6AA,
United Kingdom.

- First online date, Posted date: 2017-06-06


## DATA AND FILE OVERVIEW
![model](https://github.com/user-attachments/assets/6eb4ef31-57c4-4e89-954d-6b30342f1f03)

### 1.courses.csv
The file contains the list of all available modules and their presentations. The columns are:
- code_module - code name of the module, which serves as the identifier.
- code_presentation - code name of the presentation. It consists of the year and "B" for the presentation starting in February and "J" for the presentation starting in October.
- length - length of the module-presentation in days.

The structure of B and J presentations may differ and therefore it is good practice to analyse the B and J presentations separately. Nevertheless, for some presentations the corresponding previous B/J presentation do not exist and therefore the J presentation must be used to inform the B presentation or vice versa. In the dataset this is the case of CCC, EEE and GGG modules.

### 2.assessments.csv
This file contains information about assessments in module-presentations. Usually, every presentation has a number of assessments followed by the final exam. CSV contains columns:

- code_module - identification code of the module, to which the assessment belongs.
- code_presentation - identification code of the presentation, to which the assessment belongs.
- id_assessment - identification number of the assessment.
- assessment_type - type of assessment. Three types of assessments exist: Tutor Marked Assessment (TMA), Computer Marked Assessment (CMA) and Final Exam (Exam).
- date - information about the final submission date of the assessment calculated as the number of days since the start of the module-presentation. The starting date of the presentation has number 0 (zero).
- weight - weight of the assessment in %. Typically, Exams are treated separately and have the weight 100%; the sum of all other assessments is 100%.
If the information about the final exam date is missing, it is at the end of the last presentation week.

### 3.vle.csv
The csv file contains information about the available materials in the VLE. Typically, these are html pages, pdf files, etc. Students have access to these materials online and their interactions with the materials are recorded.
The vle.csv file contains the following columns:

- id_site - an identification number of the material.
- code_module - an identification code for module.
- code_presentation - the identification code of presentation.
- activity_type - the role associated with the module material.
- week_from - the week from which the material is planned to be used.
- week_to - week until which the material is planned to be used.

### 4.studentInfo.csv
This file contains demographic information about the students together with their results. File contains the following columns:

- code_module - an identification code for a module on which the student is registered.
- code_presentation - the identification code of the presentation during which the student is registered on the module.
- id_student - a unique identification number for the student.
- gender - the student's gender.
- region - identifies the geographic region, where the student lived while taking the module-presentation.
- highest_education - highest student education level on entry to the module presentation.
- imd_band - specifies the Index of Multiple Depravation band of the place where the student lived during the module-presentation.
- age_band - band of the student's age.
- num_of_prev_attempts - the number times the student has attempted this module.
- studied_credits - the total number of credits for the modules the student is currently studying.
- disability - indicates whether the student has declared a disability.
- final_result - student's final result in the module-presentation.

### 5.studentRegistration.csv
This file contains information about the time when the student registered for the module presentation. For students who unregistered the date of unregistration is also recorded. File contains five columns:

- code_module - an identification code for a module.
- code_presentation - the identification code of the presentation.
- id_student - a unique identification number for the student.
- date_registration - the date of student's registration on the module presentation, this is the number of days measured relative to the start of the module-presentation (e.g. the - - negative value -30 means that the student registered to module presentation 30 days before it started).
- date_unregistration - date of student unregistration from the module presentation, this is the number of days measured relative to the start of the module-presentation. Students, who completed the course have this field empty. Students who unregistered have Withdrawal as the value of the final_result column in the studentInfo.csv file.

### 6.studentAssessment.csv
This file contains the results of students' assessments. If the student does not submit the assessment, no result is recorded. The final exam submissions is missing, if the result of the assessments is not stored in the system.
This file contains the following columns:

- id_assessment - the identification number of the assessment.
- id_student - a unique identification number for the student.
- date_submitted - the date of student submission, measured as the number of days since the start of the module presentation.
- is_banked - a status flag indicating that the assessment result has been transferred from a previous presentation.
- score - the student's score in this assessment. The range is from 0 to 100. The score lower than 40 is interpreted as Fail. The marks are in the range from 0 to 100.

### 7.studentVle.csv
The studentVle.csv file contains information about each student's interactions with the materials in the VLE.
This file contains the following columns:

- code_module - an identification code for a module.
- code_presentation - the identification code of the module presentation.
- id_student - a unique identification number for the student.
- id_site - an identification number for the VLE material.
- date - the date of student's interaction with the material measured as the number of days since the start of the module-presentation.
- sum_click - the number of times a student interacts with the material in that day.


## SHARING AND ACCESS INFORMATION

### 1.Licenses
The dataset is made publicly available for academic research and educational purposes. It is released under a Creative Commons Attribution 4.0 International License [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

### 2.Citing the dataset
When citing the dataset please use the following reference:
[Kuzilek J., Hlosta M., Zdrahal Z. Open University Learning Analytics dataset Sci. Data 4:170171 doi: 10.1038/sdata.2017.171 (2017).](https://www.nature.com/articles/sdata2017171)

### 3.Recommended citation for the data
- Papamitsiou, Z. & Economies, A. A. Learning Analytics and Educational Data Mining in Practice: A Systematic Literature Review of Empirical Evidence. Educational Technology & Society 17, 49-64 (2014).
- Stamper, J., Niculescu-Mizil, A., Ritter, S., Gordon, G. J. & Koedinger, K. R. Algebra | 2008-2009. Challenge data set from KDD Cup 2010 Educational Data Mining Challenge (2010).

### 4.Examples:
Open Data Mashup 2015

- [Document describing a Mashup example](https://analyse.kmi.open.ac.uk/resources/documents/mashupExample.pdf)
- [Example subset of OULAD](https://analyse.kmi.open.ac.uk/resources/documents/mashupData.RData)


## METHODOLOGICAL INFORMATION
![41597_2017_Article_BFsdata2017171_Fig3_HTML](https://github.com/user-attachments/assets/5f7c319a-6890-4347-9878-48a390353251)
### 1.Distinguish different data types
- Demographic-represents the basic information about the students including their age, gender, region, previous education, etc.
- Performance-reflects students' results and achievements during their studies at the OU.
- Learning behaviour-is the log of student activities in the VLE.

### 2.Data selection
The data warehouse contains information about students, namely: their demographics, modules and VLE activities, since 2012. We selected several representative modules taught at the OU during 2013 and 2014. The selection process followed these rules:

- The number of students in the selected module-presentation is larger than 500.
- At least two presentations of the module exist.
- VLE data are available for the module-presentation (since not all the modules are studied via VLE).
- The module has a significant number of failing students.

Out of the all modules that satisfy these criteria we selected 7 modules: 4 Science, Technology, Engineering, and Mathematics (STEM) modules and 3 Social Sciences modules. The total number of students in the selected modules is 38.239.

### 3.Data anonymisation
The dataset anonymisation process was designed according to the ethical and privacy requirements applied at the OU. The whole process of dataset creation and release was supervised by the OU management, and approved by the Vice-Chancellor Executive committee. Anonymisation itself was performed in a series of steps. The first step removed private information about students and modules. This includes the social security number, dates of birth and unique identifiers used at the OU for students. Module names have been replaced by semantic-free symbols and all temporal information has been expressed in relative terms with respect to the presentation start. In addition, all numeric identifiers (i.e., student _id, code_module, etc.) have been reassigned and completely randomised.


## DATA-SPECIFIC INFORMATION
The dataset contains the information about 22 courses, 32,593 students, their assessment results, and logs of their interactions with the VLE represented by daily summaries of student clicks (10,655,280 entries).

![41597_2017_Article_BFsdata2017171_Fig4_HTML](https://github.com/user-attachments/assets/d91e8a9b-d3f7-4683-9ab5-eb86c116d998)

### 1.Table studentInfo
This table contains student demographic information and also their results in each module they studied. It consists of 32,593 rows with the following columns:

- code_module—module identification code on which the student is registered.
- code_presentation—presentation identification code during which the student is registered on the module.
- id_student—the unique student identification number.
- gender—student’s gender.
- region—the geographic region, where the student lived while taking the module-presentation.
- highest_education—the highest student education level on entry to the module presentation.
- imd_band—the IMD band of the place where the student lived during the module-presentation.
- age_band—a band of student’s age.
- num_of_prev_attempts—the number of how many times the student has attempted this module.
- studied_credits—the total number of credits for the modules the student is currently studying.
- disability—indicates whether the student has declared a disability.
- final_result—student’s final result in the module-presentation.

### 2.Table courses
The table contains the list of all available modules and their presentations. It consists of 22 rows with the following columns:

- code_module—code name of the module, which serves as the identifier.
- code_presentation—code name of the presentation.
- length—the length of the module-presentation in days from module start date to module end date.

The structure of B and J presentations may differ and therefore it is recommended to analyse the B and J presentations separately. The following table (Table 1) contains information about the study domain, the number of students and the number of presentations of each module included in the dataset.

### 3.Table studentRegistration
Contains information about the time when the student registered for the module presentation. For students who unregistered, the date of un-registration is also recorded. It consists of 32,593 rows with the following columns:

- code_module—the module identification code.
- code_presentation—the presentation identification code.
- id_student—the unique student identification number.
- date_registration—the day of student’s registration for the module presentation.
- date_unregistration—the day of student unregistration from the module presentation. Students, who completed the course have this field empty. Students who unregistered have Withdrawal as the value of the final_result in the studentInfo table.

### 4.Table assessments
This table contains information about assessments in module-presentations. Usually, every presentation has a number of assessments followed by the final exam. The table consists of 206 rows with the following columns:

- code_module—module identification code, to which the assessment belongs.
- code_presentation—presentation identification code, to which the assessment belongs.
- id_assessment—assessment identification number.
- assessment_type—a type of assessment. Three types of assessments exist—Tutor Marked Assessment (TMA), Computer Marked Assessment (CMA) and Final Exam (Exam).
- date—information about the cut-off day of the assessment.
- weight—the weight of the assessment. Typically, Exams are treated separately and have the weight equal to 100%; the sum of all other assessments is also 100%.

If the information about the final exam cut-off day is missing, it takes place during the last week of the module-presentation.

### 5.Table studentAssessment
The table contains the results of students’ assessments. If the student does not submit the assessment, no result is recorded. Results of the final exam are usually missing (since they are scored and used for the final marking immediately at the end of the module). It consists of 173,912 rows with the following columns:

- id_assessment—the assessment identification number.
- id_student—the unique student identification number.
- date_submitted—the day of assessment submission.
- is_banked—the status flag indicating that the assessment result has been transferred from a previous presentation.
- score—the student’s score in this assessment. The range is from 0 to 100. The score lower than 40 is interpreted as Fail. The marks are in the range from 0 to 100.

### 6.Table studentVle
The studentVle table contains information about student’s interactions with the VLE. It consists of 10,655,280 rows with the following columns:

- code_module—the module identification code.
- code_presentation—the presentation identification code.
- id_student—the unique student identification number.
- id_site—the VLE material identification number.
- date—the day of student’s interaction with the material.
- sum_click—the number of times the student interacted with the material.

### 7.Table vle
The vle table contains information about the materials available in the VLE. Typically these are HTML pages, pdf files, etc. It consists of 6,364 rows with the following columns:

id_site—the identification number of the material.
code_module—the identification code for the module.
code_presentation—the identification code of the presentation.
activity_type—the role associated with the module material.
week_from—the week from which the material is planned to be used.
week_to—the week until which the material is planned to be used.

