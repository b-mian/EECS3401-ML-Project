# EECS3401-ML-Project

Machine Learning Project Report
Predicting Students’ Academic Success

Date — March 24, 2024
EECS 3401 Report 1

Table of Contents
1. The Big Picture — Framing the Problem
2. Dataset Description and Graphs of EDA
3. Data Cleaning and Pre-processing Pipeline
4. Machine Learning Models and Evaluation
•  #1 — Decision Tree Classification
A. Summary and Code Snippet
B. Results and Evaluation
• #2 — Multi-Class Logistic Regression
A. Summary and Code Snippet
B. Results and Evaluation
• #3 — Support Vector Machine Classification
A. Summary and Code Snippet
B. Results and Evaluation
•Performance Comparison Table
5. Best Performance Graphs
6. Limitations
7. Next Steps

1. The Big Picture — Framing the Problem

The purpose of this analysis is to predict the academic success of a student in
university based on several traits/features unique to them. A few of these features
include: Admissions Grades, First and Second Semester Grades, Mother’s and Father’s
Qualifications (educational background), Up To Date Tuition Fees, Debt/No Debt,
Gender, Is a Scholarship Holder and so on. The target set consists of three elements
(dropout, graduate, and enrolled). This target is the prediction output of the machine
learning models implemented, and represents the state of a student at the end of their
university program.

In total, there are 4424 rows (students) in the dataset, along with 35 features (not
including the target feature). The feature set was reduced to 19 total, and this was a
conscious decision to remove those traits that were seen as irrelevant to the analysis
performed. Some of these features include nationality, time of application and course
choice/preference when applying, as well as the GDP, inflation rate and employment rate
at the time of course enrolment. These features are out of the student’s control, and the
purpose of this project is to control for those features that are deemed unique/relevant
to student success in academics, and drop the others (nationality, ethnicity, economic
conditions and time/program choice in application to university, and so on).

3. Dataset Description and Graphs of EDA

This dataset was sourced from the UC Irvine Machine Learning Repository. The
data is recent (December 2021) and was collected by researchers at the Instituto
Politécnico de Portalegre in Portugal for a study on student academic performance. The
original purpose of open-sourcing the dataset is to use “machine learning techniques to
identify students at risk at an early stage of their academic path, so that strategies to
support them can be put into place” (Martins, 2021).

From the original 4424 instances and 35 features in the dataset, a few modifications
were made. As mentioned earlier, several columns were dropped from the set. From the
target (output) set, all rows with the value “Enrolled” were removed as to enforce binary
classification machine learning models. The reason for this decision was due to the much
lower accuracy and reliability of the models when trying to predict a student as still
enrolled at the end of their studies. By removing this option, the predictive validity of the
models was greatly improved, as will be demonstrated.

1. Histograms of admissions grades along with first and second semester grades.
These graphs all conform to a right-skewed normal distribution, which was interesting
EECS 3401 Report 3
because the graphs of academic performance between pre-university training and first
year of university look nearly identical in shape.

3. Scatter plot of first versus second semester GPA (on a 10 to 20-point scale). As
shown, there seems to be a strong correlation between first and second semester GPA.
What’s more interesting here is that scholarship holders, shown as blue dots, don’t seem
to have higher first-year grades than non-scholarship holders, though the scholarship
holders tend to have GPA’s clustering around the 12/20 to 16/20 range, and less at the
lower end of the GPA scale. There is also noticeably less scatter in GPA amongst
scholarship holders, whereas non-scholarship holders are all over the grade range.

4. Multi-dimensional scatter plot across four features, which shows relationships
between first year grades (both semesters), admissions grades, and grades from previous
qualifications (previous degree/diploma/credential). The red dots represent students
who dropped out from their program, and the blue dots are students that graduated. As
is clear from every one of these graphs, grades achieved are very strongly correlated to
whether a student drops out (which is almost a trivial assumption to make, but shown
nevertheless).

#1 — Decision Tree Classification

EVALUATION of #1
For the decision tree classification model, the predictive accuracy was good after
data processing was complete, achieving an average accuracy score between 75% and
80% across several runs of the code, classifying a student as a graduate or dropout.
EECS 3401 Report 7
Other metrics such as f1_score (average of recall and accuracy) and ROC Area Under
Curve as presented below, which show reasonably good predictive accuracy overall.

#2 — Logistic Regression Classification

EVALUATION of #2
For the logistic regression classification model, the predictive accuracy was better
than the decision tree model, achieving an average accuracy probability score between
82% and 86% across several runs of the code. Another metric like the f1_score (weighted
average of recall and accuracy) is presented below in the code snippet, which shows very
good predictive accuracy of the classification task.


#3 — Support Vector Machine Classification


EVALUATION of #3
For the support vector machine classification models, the predictive accuracy was in
the middle of the other two, achieving an average accuracy probability score between
82% and 86% across several runs of the code. Other metrics like the f1_score (weighted
average of recall and accuracy) is presented below in the code snippet, along with just
recall and accuracy. This model, along with Logistic Regression, has very good predictive
accuracy of the classification task.


5. Best Performing Algorithm
The Best Performing model was found to be #2 Logistic Regression Classification

Graphs - Confusion Matrix and Regression Plot

6. Limitations
No real limitations were detected, except that many of the features in the dataset
seemed out of a student’s control, such as the inflation and unemployment rate, along
with other socio-economic factors like GDP and nationality/ethnicity. The goal with the
creation of this dataset by the researchers was to facilitate and encourage new modes of
intervention to help students in their post-secondary education, using machine learning
as an investigative tool. Perhaps this analysis was not at a depth that a professional
would be happy with, but the relationships in the data exploration phase seemed rather
obvious and intuitive, with grades (overall) being the strongest predictors of academic
success.

7. Next Steps
If the scope of this project were larger, it would be important to not only focus on an
even smaller subset of the features listed for analysis, but also to explore relationships/
interactions among variables other than grades. This way, the objective of the research
done by the team at Instituto Politécnico de Portalegre can be better understood and
practical responses to the results can be made. For example, if student stress was found
to be a high predictor of dropout rates, then reducing tuition/debt, course loads or
changing evaluation schemes and teaching methods would be better able to address
student academic success.

