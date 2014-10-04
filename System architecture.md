4.1 High-level overview of the system
  Student have to login to be able to using application. Wifi signal will be used to track position. System will navigate position of student then send the position to the server. Server will process data and sendback the location of student. When student ensures location and class is correct, he presses start check attendance button. When start check attendance, a request will send to server with necessary information. Server starts counting the time of student in class and also sending student's info to teacher. In a special case, student can leave a message or execute exception mode for battery running out, dropping signal...application will collect device's info and take a screen shot then send to the teacher. Teacher can also check student's attendance manualy by tick on student name. .
  This application alows teacher setup a course, add or delete student to the course, view message... Teacher can set minimum attending time for student by percent of whole duration. for example 50%, 80%... etc.
  At the end of class, teacher can view the summary of class and course.

4.2 Main modules and their functions represented
  <img src="http://users.metropolia.fi/~quocdu/software/project_uml.jpg" alt="uml" >


  
  - User class is a parent class, which has the login logout and checkRole function. Check role function specifies the user role for creating children class as Student, Teacher or Admin. It has userId, userName, password and userRole parameters. Method: login(), logout(), checkRole()
  - Student class is a child of User. Parameter is studentId, studentName, group. It's functions are described bellow. method: startAttendance(), leaveMessage(), exceptionMode(), nextClass().
  - Teacher class is a child of User. Parameter is teacherId, teacherName. It's functions are described bellow. Method: getCourseList(), addCourse(), delCourse(), editCourse(), viewMessage(), viewCourse(), checkAttendance().
  - Admin class is a child of User. Which has the most powerful to this system.It's functions are described bellow. Method: addUser(), editUser(), delUser(), addCourse(), editCourse(), delCourse().
  - Course class has parameter courseId, courseInfo, courseName, classes. Parameter classes is an array which contains object. One course has many classes. Class as element. Method: addStudent(), delStudent(), save().
  - Class class refers to the teaching day of the course. Parameter: classId, classInfo. classInfo is an array which contains infomation like time, date, room...etc. Method: getRoom(), getDate(), getTime(), getDuration(), edit().
  - Client has some static function: validateInput(), countTime(), sendSessionInfo(), trackPos().
  - Server has some static function: validateInput(), validateUser(), saveSessionInfo(), dbQuery(), getLoc().
