# Student Performance Dataset

This folder contains the UCI Student Performance data for Portuguese and Math courses, along with a helper script to merge them. Both CSVs use semicolon separators and include the same schema.

## Files
- student-mat.csv: Math course records.
- student-por.csv: Portuguese language course records.
- student-merge.R: R script to merge the two course datasets on common keys.
- student.txt: Original dataset description from UCI.

## Schema
| Feature | Description |
| --- | --- |
| school | Student's school (GP, MS). |
| sex | Student's sex (F, M). |
| age | Age 15-22. |
| address | Home address type (U urban, R rural). |
| famsize | Family size (LE3 <=3, GT3 >3). |
| Pstatus | Parents' cohabitation status (T together, A apart). |
| Medu | Mother's education level (0 none, 1 primary 4th grade, 2 5th-9th grade, 3 secondary, 4 higher). |
| Fedu | Father's education level (0 none, 1 primary 4th grade, 2 5th-9th grade, 3 secondary, 4 higher). |
| Mjob | Mother's job (teacher, health, services, at_home, other). |
| Fjob | Father's job (teacher, health, services, at_home, other). |
| reason | Reason to choose this school (home, reputation, course, other). |
| guardian | Student's guardian (mother, father, other). |
| traveltime | Home-to-school travel time (1 <15m, 2 15-30m, 3 30-60m, 4 >60m). |
| studytime | Weekly study time (1 <2h, 2 2-5h, 3 5-10h, 4 >10h). |
| failures | Past class failures (1-3, else 4). |
| schoolsup | Extra educational support (yes, no). |
| famsup | Family educational support (yes, no). |
| paid | Extra paid classes in subject (yes, no). |
| activities | Extra-curricular activities (yes, no). |
| nursery | Attended nursery school (yes, no). |
| higher | Wants higher education (yes, no). |
| internet | Internet access at home (yes, no). |
| romantic | In a romantic relationship (yes, no). |
| famrel | Family relationship quality (1 very bad to 5 excellent). |
| freetime | Free time after school (1 very low to 5 very high). |
| goout | Going out with friends (1 very low to 5 very high). |
| Dalc | Workday alcohol consumption (1 very low to 5 very high). |
| Walc | Weekend alcohol consumption (1 very low to 5 very high). |
| health | Current health status (1 very bad to 5 very good). |
| absences | Number of school absences (0-93). |
| G1 | First period grade (0-20). |
| G2 | Second period grade (0-20). |
| G3 | Final grade (target, 0-20). |

## Notes
- No missing values are reported in the source documentation.
- Targets are G1, G2, and G3; G3 is typically used as the main prediction target.
- License: Refer to student.txt (UCI Machine Learning Repository terms).
