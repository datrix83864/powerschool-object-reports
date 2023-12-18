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

Under Current Schedule, anything that is the period number `^(*period_info;1(A);course_name)` in this case 1(A), needs to be changed to the periods that are possible for a student. It is best to look at your school's/district's master schedule to find the variations that exist.

## Potential differences for other users

### Terms

We have a high school with quarters and then two high schools with semesters. This specific transcript has both semester and quarter grades showing

- Fixes: You can remove S1 and S2 references, and be left with quarters. Will need to adjust the vertical lines

### District Info

The District name will be different, however, the details for the school should automatically be generated for the student. Our students on graduation get moved to a "Graduated Students" school, school number 999999. This is used in the header function to test for what info to display as school, address, phone number, and fax number. If the school is "graduated students", it will display the District office information.

### Graduation Date

In the report as S_ID_STU_X.GraduationDate this uses the S_ID_STU_X table and the column GraduationDate. This would change to your school/district table and column for where graduation date is stored. In our district, this information is changed on a students Demographics page, near the bottom, under Idaho State Information.

### Civics Test

Our setup has a Civics test (graduation requirement in Idaho) similar to SAT, however, the two 'test' values of Pass and Fail. Schools are supposed to put either P or F in the civics test passed alpha grade based on if the student passed or not. PowerSchool specifically requires the `result=value` to make the alpha return properly.

### Current Schedule Chaos

Looking at the current schedule section will show a lot of things happening. In short this is taking into account all the variations that are possible between the three schools.

### Header setup

This looks if a student is currently in a school that isn't the Graduated Students school, those in graduated students school get the district office information instead of school specific.

## Current limitation

Students moved to graduated students school do not have their rank saved. This is a PowerSchool limitation and is being investigated for a solution by our staff.
