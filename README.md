Download Link: https://assignmentchef.com/product/solved-cs201-assignment-1-a-simple-registration-system-using-dynamic-memory-management
<br>
In this assignment, you will implement a simple registration system by using dynamic memory management. The registration system stores information about students and courses. For each student, the system stores an id, first name, last name, and a list of her/his course enrollments. Each course is represented by its id and title. This system <strong>MUST </strong>use a dynamically allocated array to store the students, and for each student, another dynamically allocated array to store the course enrollments for that student. The students are stored in ascending order of their ids. The courses are stored in an unsorted array. The arrays must be allocated dynamically and must use memory only as much as needed (in other words, you cannot assume a maximum size for students and courses to allocate arrays that are larger than needed).

The registration system will have the following functionalities; the details of these functionalities are given below:

<ul>

 <li>Add a student</li>

 <li>Delete a student</li>

 <li>Add a course for a student</li>

 <li>Withdraw a student from a course</li>

 <li>Cancel a course</li>

 <li>Show detailed information about a particular student</li>

 <li>Show detailed information about a particular course</li>

 <li>Show all students</li>

</ul>

This assignment has two parts, whose requirements will be explained below.

<strong><u>PART A: </u>To take the final exam, you MUST submit at least this part and MUST get at least half of its points.</strong>

This part includes the following four functionalities:

<ul>

 <li>Add a student</li>

 <li>Delete a student</li>

 <li>Show detailed information about a particular student</li>

 <li>Show all students</li>

</ul>

The details of these four functionalities will be given below. Note that this part does not involve any course information for the students. Therefore, in this part, the “Show detailed information about a particular student”or the “Show all students” functionalities will not be expected to display the list of the courses enrolled by the student(s).

<strong><u>PART B: </u></strong>In this part, you will complete the implementation of the entire registration system (all of the 8 functionalities listed above).

<strong>The details of all of the functionalities are given below:</strong>

<strong>Add a student: </strong>The registration system will allow to add a new student indicating her/his student id, first name, and last name. Since the student ids are unique positive integers, the system should check whether or not the specified student id already exists (i.e., whether or not it is the id of an existing student), and if the student id exists, it should not allow the operation and display a warning message. Moreover, if the first name or the last name are empty, it should not allow the operation and display a warning message. The array must remain <strong>sorted </strong>by student id after this operation.

<strong>Delete a student: </strong>The registration system will allow to delete an existing student indicating her/his student id. If the student does not exist (i.e., if there is no student with the specified id), the system should display a warning message. Note that this operation will also drop all courses in which the student was enrolled.

<strong>Add a course for a student: </strong>The registration system will allow to add a new course for a particular student. For that, the student id, the course id, and the course name have to be specified. The system should check whether or not this student exists; if she/he does not, it should prevent to add a course and display a warning message. If the student exists and the student is not already enrolled in this course, the given course is added to student’s course array. If the student is already enrolled in this course, it should display an appropriate message and the given course should not be added again. The courses are stored unsorted.

<strong>Withdraw a student from a course: </strong>The registration system will allow to delete an existing course indicating its course id from a student’s course enrollment array. If the student does not exist (i.e., if there is no student with the specified id) or the student is not enrolled in this course (i.e., if there is no course with the specified id), the system should display a warning message.

<strong>Cancel a course: </strong>The registration system will allow to delete an existing course indicating its course id. Note that this operation will remove the course from the course enrollment arrays for all students. If the course does not exist (i.e., if there is no course with the specified id), the system should display a warning message.

<strong>Show detailed information about a particular student: </strong>The registration system will allow to specify a student id and display detailed information about that particular student. This information includes the student id, the student name, the list of courses enrolled by this student including the course id and the course name for each course. If the student does not exist (i.e., if there is no student with the specified student id), the system should display a warning message.

<strong>Show detailed information about a particular course: </strong>The registration system will allow to specify a course id and display detailed information about that particular course. This information includes the course id, the course name, the list of students enrolled in this course including the student id and the student name for each student. If the course does not exist (i.e., if there is no course with the specified course id), the system should display a warning message.

<strong>Show the list of all students: </strong>The registration system will allow to display a list of all the students. This list includes the student id, the student name, and the list of courses enrolled by each student.

Below is the required public part of the RegistrationSystem class that you must write in this assignment. The name of the class <u>must </u>be RegistrationSystem, and <u>must </u>include these public member functions. We will use these functions to test your code. The interface for the class must be written in a file called RegistrationSystem.h and its implementation must be written in a file called RegistrationSystem.cpp. You can define additional public and private member functions and data members in this class. You can also define additional classes in your solution.

class RegistrationSystem { public:

RegistrationSystem(); ~RegistrationSystem();

void addStudent( const int studentId, const string firstName, const string lastName ); void deleteStudent( const int studentId );

void addCourse( const int studentId, const int courseId, const string courseName ); void withdrawCourse( const int studentId, const int courseId ); void cancelCourse( const int courseId );

void showStudent( const int studentId ); void showCourse( const int courseId ); void showAllStudents();

};

Here is an example test program that uses this class and the corresponding output. We will use a similar program to test your solution so make sure that the name of the class is RegistrationSystem, its interface is in the file called RegistrationSystem.h, and the required functions are defined as shown above. The example test code provided below is just a sample. You must test your program with different inputs as well.