### A/ Cover 
Title: Requirements Documentation of 'Autocheck Attendance'

Team name: QL 

Team member: Tran Dinh Linh & Duong Quoc Quan 

Date: 2.10.2014
---------------------

### B/ Introduction
---------------------

### C/ Use cases 

#### 1. User groups definition. 

| User groups | Brief definition | Definition |
| --- | --- | --- |
| Administrator | Owner of the software | The admin is responsible for functioning of the software but has no right to access users' data. |
| User/ Lecturers | Registered user | Lecturer users are registered by school according to courses that they have. This kind of users is able to access information related to courses as well as assigning some particular factors in the system. |
| User/ Students | Registered user | Student user type can login to system to do attendance check but has no right to modify any setting of the system. |

#### 2. Use cases of primary actors for Autocheck Attendance. 

| Primary Actors | Use cases | 
| ------------- |-------------|
| Administrator | <ul><li> Accept users’ registration  </li><li> Modify rights of users </li><li> Make changes in system settings </li><li> Overall attendance info </li></ul> |  
| Lecturers | <ul><li> Login </li><li> Logout </li><li>	Choose courses </li><li> View courses info </li><li> View number of attending students and their status </li><li>	Add features to a particular course </li><li><h5> Save or download an attendance figure from system </h5></li></ul> | 
| User/ Students | <ul><li> Login  </li><li> Logout </li><li> View courses info </li><li><h5> View attending time </h5></li><li> View following classes </li></ul> | 

#### 3. Use case scenarios

| Use case ID | 1 |
| --- | --- |
| Use case name | Download an attendance figure |
| Created by | Tran Dinh Linh |
| Date created | 29th Sep 14 |
| Actors | Lecturers |
| Description | Teachers login to system to download an attendance file |
| Preconditions | <ul><li> Teachers have logged in  </li><li> Teachers see the starting page and choose the targeted courses </li></ul> |
| Post conditions |	Teachers have downloaded successfully the file |
| Normal flow | <h5>1. Download an attendance file</h5> <ul><li>a) Teachers login </li><li>b) Teachers choose course name from the course list drop down </li><li>c) System shows a list of files sorted by category </li><li>d) Teachers choose date </li><li>e)System will show the file according to the chosen date  </li><li>f) Teachers download the file  </li></ul> |
| Alternative flows | 2. Download multiple files (branch out of step c above) <ul><li> a)	Teachers choose multiple dates by checking dates’ checkboxes  </li><li> b)	Teachers continue with step e) and f) from above. </li></ul> |
| Exceptions | 1.1 Lose Internet connection <ul><li>Alert message pops up to indicate the problem of Internet connection</li></ul> 1.2	Exceed to maximum idle time <ul><li>System sends message of a ‘request time of’ to users.</li><li>	System requires users to login again to continue </li><li> Teachers login again to continue the process </li></ul>  1.3	Password incorrect <ul><li> Teachers send a form to system for password resetting </li></ul> 1.4 Exceed to maximum idle time <ul><li>	System sends message of a ‘request time of’ to users </li><li>	System requires users to login again to continue the process </li></ul>|
| Assumption | <ul><li> Lecturers have registered accounts</li><li> Lecturers login successfully </li></ul> |


| Use case ID | 2 |
| --- | --- |
| Use case name | View attending time  |
| Created by | Tran Dinh Linh |
| Date created | 29th Sep 14 |
| Actors | Students |
| Description | Students login to system to check attending time |
| Preconditions | <ul><li>	Students have logged in  </li><li> System shows the students view after logging in </li></ul> |
| Post conditions |	Students check successfully attending time |
| Normal flow | <h5>1. View attending time </h5> <ul><li>a) Students login </li><li>b)	System automatically navigates to the local class where students are currently participating </li><li>c)	Students check courses name, classes, and attending time. </li><li>d) Students log out. </li></ul> |
| Alternative flows | 2. Battery runs out <ul><li> a)	After logging in to system, users’ devices power runs out  </li><li> b) System notifies the situation and sends notifications of the cases to teachers e)	Students log out and have enough proof for their present. </li></ul> |
| Exceptions | 1.1 Lose Internet connection <ul><li>Alert message pops up to indicate the problem of Internet connection</li></ul> 1.2	Exceed to maximum idle time <ul><li>System sends message of a ‘request time of’ to users.</li><li>	System requires users to login again to continue </li><li> Teachers login again to continue the process </li></ul>  1.3	Password incorrect <ul><li> Students send a form to system for password resetting </li></ul> 1.4 Exceed to maximum idle time <ul><li>	System sends message of a ‘request time of’ to users </li><li>	System requires users to login again to continue the process </li></ul>|
| Assumption | <ul><li>	Students possess registered accounts </li><li>	Students have already enrolled for the courses</li></ul> |
--------------------------

### D/ System architecture 

#### 1. High-level overview of the system


  Student have to login to be able to using application. Wifi signal will be used to track position. System will navigate position of student then send the position to the server. Server will process data and sendback the location of student. When student ensures location and class is correct, he presses start check attendance button. When start check attendance, a request will send to server with necessary information. Server starts counting the time of student in class and also sending student's info to teacher. In a special case, student can leave a message or execute exception mode for battery running out, dropping signal...application will collect device's info and take a screen shot then send to the teacher. Teacher can also check student's attendance manualy by tick on student name. .
  This application alows teacher setup a course, add or delete student to the course, view message... Teacher can set minimum attending time for student by percent of whole duration. for example 50%, 80%... etc.
  At the end of class, teacher can view the summary of class and course.

#### 2. Main modules and their functions represented


  <img src="http://users.metropolia.fi/~quocdu/software/project_uml.jpg" alt="uml" >


  
  - User class is a parent class, which has the login logout and checkRole function. Check role function specifies the user role for creating children class as Student, Teacher or Admin. It has userId, userName, password and userRole parameters. Method: login(), logout(), checkRole()
  - Student class is a child of User. Parameter is studentId, studentName, group. It's functions are described bellow. method: startAttendance(), leaveMessage(), exceptionMode(), nextClass().
  - Teacher class is a child of User. Parameter is teacherId, teacherName. It's functions are described bellow. Method: getCourseList(), addCourse(), delCourse(), editCourse(), viewMessage(), viewCourse(), checkAttendance().
  - Admin class is a child of User. Which has the most powerful to this system.It's functions are described bellow. Method: addUser(), editUser(), delUser(), addCourse(), editCourse(), delCourse().
  - Course class has parameter courseId, courseInfo, courseName, classes. Parameter classes is an array which contains object. One course has many classes. Class as element. Method: addStudent(), delStudent(), addClass(), delClass(), save().
  - Class class refers to the teaching day of the course. Parameter: classId, classInfo. classInfo is an array which contains infomation like time, date, room...etc. Method: getRoom(), getDate(), getTime(), getDuration(), edit().
  - Client has some static function: validateInput(), countTime(), sendSessionInfo(), trackPos().
  - Server has some static function: validateInput(), validateUser(), dataProcess(), saveData() , dbQuery(), getLoc().

--------------------------

### E/ Requirements
--------------------------

### F/ User interface

##### 1. Views
•	Startup page

•	Users page

##### 2. Components
•	Logo 

•	Login/Logout

•	Course list 

•	ID 

•	Information related to courses

•	Attendance figure

•	Minimum attending time


<h6>Views</h6>
•	Startup page: Select languages, campus location, input ID and password to log in. 

•	Users page: Views from different users differentiate from each other. (More details are shown in mock-up paper)

<h6>Components</h6>
•	Logo: Click to navigate to front-page. 

•	Login/out:

•	Course list: a drop-down list of courses will be shown. 

•	ID: ID of users is located at the upper right corner of the screen.

•	Information related to courses: Course name (class), room, and teachers’ name, number of students.   

•	Attendance figure: For lecturers, this would be a table which showing student names, IDs, statuses and additional information. For students, this would be a counting or processing pie chart with time is counting. 

•	 Minimum attending time: The least amount of time that students need to be in the classes. For teachers, editing option is available but not for student users. 

<h6> Lecturers view </h6>
<img src="http://users.metropolia.fi/~dinhtr/SE/Photo%2002-10-14%2018%2028%2011.jpg" />

<h6> Students view </h6>
<img src="http://users.metropolia.fi/~dinhtr/SE/Photo%2002-10-14%2018%2028%2039.jpg" /> 
--------------------------

### G/ Project management and self reflection
<p> The time for doing this project was quite tight in our group's perspective. However, we tried our best to accomplish to project. 
In general, the project at some points was more into theories which sometimes lead us to a theorical overload. It would be much 
more easier to understand new kind of concepts if there are real cases to practise on. Nevertheless, we learnt how to structure
a software requirements from scratch as well as how work-flow goes. Back to the project, we are happy and satisfied with what we
have done so far. Group members worked so hard and contributed a large amount of time to the project. In particular, each member
probably worked individually approximately 20 hours and between 6-8 hours together. Althought many hours were spent for the project
there are still some parts need to be clarified in more detailed. Therefore, on the following project we will know how to do more
efficiently. </p>
