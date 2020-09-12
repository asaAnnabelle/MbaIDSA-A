

# Classes

The class Department is the rot class for the model. A Department object can contain multiple object of Course and Program. A Program will contain multiple object of Semester and can contain objects of Specialisation. The Semesterobject can belong to one Specialisation but doesn’t need to, and it can contain multiple Course objects.

A Program has a code, name, length of program in years and a start year and end year. The start and end year are used to keep track of Existing Programs.

A Course has a name, a unique code, a Studylevel (Enum), and number of credits for the semester. 

A Semester works as a “study plan” where all courses the student can take for each semester are located. There are two lists of Course objects; mandatoryCourses and selectableCourses. The Semester has a semesternumber which can maximum be number of programlength times two. The Semester also has a start year, and an end year. The start and end year are used to keep track of changes in the “study plan”. So if the list of courses haven’t changed in some years, there are no need to save unnecessary instances of Semesters. Each Semseter knows which Program it belongs to, and if it also belongs to a Specialisation. 

A Specialisation has a name a start year and an end year. It has a list of Semesters and the Program it belongs to. The start and end year are used to keep track of Existing Specialisations.


# Constraints

There are constraints on the classes to make sure that all instances are valid. There are multiple constraints to check if the numbers are valid. In Course the credit has to be a positive number. The same applies to lengthOfProgramInyears in Program. The attribute startyear and endyear are also in Program, Semester and Specialisation checks that the startyear are before the endyear if not the endyear is 0. When the endyear is 0 it has not been set yet and the Program, Semester or Specialisation is active. 

In a Semester there is a constraint on total credits for the courses. So the sum of total courses available has to be at least 30 credits, and maximum sum of credits for mandatoryCourses are 30 credits. 

In the Department there are two constraints that checks if the Courses and the Programs are unique. The Course is unique if the code is unique. The Program is unique if the code is unique. 


