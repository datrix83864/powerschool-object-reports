# Progress Reports

## School Specific

Due to the inability to switch between different logos and text color based on logic, each school gets it's own report system.

## Grade and Comment chaos, specifically in `Progress Report SHS`

In `Progress Report SHS` there is a lot of logic in place due to the setup of the classes at the school, specifically with the ability for classes to be two periods on the same day. A more simplified approach can be see in in `Progress Report CF` and `Progress Report LPO`.

### Logic breakdown

#### Comments

The following breaks down the logic found in the following code statement: `^(decode;^(*period_info;1-2(A);course_name);;^(*period_info;1(A);teacher_I_first_name) ^(*period_info;1(A);teacher_I_last_name): ^(*period_info;1(A);teacher_comment);^(*period_info;1-2(A);teacher_I_first_name) ^(*period_info;1-2(A);teacher_I_last_name): ^(*period_info;1-2(A);teacher_comment))`

The `^(decode;^(*period_info;1-2(A);course_name);` starts the logic. We check for the existance of a 1-2(A) course name. This specific version is similar to an if/else statement Results options:

- If there is no name, indicated by the `;;` where there is nothing between the two semi-colons then the course must be a 1(A) course, we then return the teacher first, last and comment from the 1(A) course that we assume to exist.
- Otherwise, it must be a 1-2(A) course, so we return the teacher first, last, and comment from the 1(A) course that we assume to exist

Further logic idea. It could be that the 1(A) and 1-2(A) courses don't exist, in which case we should return nothing at all. This would preferably happen in the first result option with another decode function.
