# Transcript

Universal Transcript for LPOSD with:

- The grade a student took a course, the Quarter or Semester grade obtained, and credits received.
- weighted and unweighted GPA
- class rank with a # out of # style
- if student has not taken, passed, or failed their civics test (Idaho requirement)
- If the student has taken the SAT, it displays the SAT score for reading/writing and Math. If they haven't, nothing is displayed.
- Student data generated on run:
  - Student Name
  - Address
  - DOB
  - District ID #
  - State ID #
  - Graduation year
  - Graduation Date
  - Exit Date

## Yearly changes

Each year should have a change in Right Header, on the final line there is an exit date for all students to end the school year. For the 23-24 school year this reads, 06/08/2024, this value should be changed to the date set to all students. Approximately around line 283.

## Potential differences for other users

Terms - We have a high school with quarters and then two high schools with semesters. This specific transcript has both semester and quarter grades showing

- Fixes: You can remove S1 and S2 references, and be left with quarters. Will need to adjust the vertical lines

District Info - The District name will be different, however, the details for the school should automatically be generated for the student. Our students on graduation get moved to a "Graduated Students" school, school number 999999. This is used in the header function to test for what info to display as school, address, phone number, and fax number. If the school is "graduated students", it will display the District office information.

Graduation Date - In the report as S_ID_STU_X.GraduationDate this uses the S_ID_STU_X table and the column GraduationDate. This would change to your school/district table and column for where graduation date is stored. In our district, this information is changed on a students Demographics page, near the bottom, under Idaho State Information.
