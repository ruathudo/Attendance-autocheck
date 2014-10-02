5. Requirements

5.1 Functional requirements

- User.login() : check weather user ID and password are correct or not. If invalid, will so warning message.
- User.checkRole() : When login successful, check user's role. If it is student, go to student interface, if it is teacher, go to teacher interface, if it is system admin, go to admin interface.
- User.logout() : Logout from application and delete all session.

- Student.startAttendance() : Student start check attendance and send the request to server
- Student.leaveMessage() : leave message to the teacher
- Student.exceptionMode() : when execute exception mode, eg battery running out, app will take screen shot and device info                             then send to server 
- Student.nextClass() : show the next class notification to student.

- Teacher.getCourseList() : get all courses belong to teacher ID.
- Teacher.addCourse() : teacher can mamually add new course to course list or add an event
- Teacher.delCourse() : teacher can delete the course or an event
- Teacher.editCourse() : teacher can edit the course or an event
- Teacher.viewCourse() : teacher can view the course information with avearage student's time attended, date, class...etc
- Teacher.viewMessage() : teacher can view student message and exception
- Teacher.checkAttendance() : teacher can manually check attendance for student by tick next to student's name

- Admin.addUser() : admin can add user to the system and set role for user
- Admin.editUser() : admin can also edit user info
- Admin.delUser() : admin can delete user
- Admin.addCourse() : admin can add new courses to the system.
- Admin.editCourse() : admin can edit course in the system
- Admin.delCourse(): admin can delete course in the system

- Course.addStudent(): add new student to the course
- Course.delStudent(): remove student from the course
- Course.save(): save all information for the course

  Client Function:
- validateInput(): validate all input for security reason
- countTime(): time counter function to calculate percent of work done during class
- sendSessionInfo() : send the session information to server for processing.

  Server Function:
- validateInput(): validate input second time to ensure security
- validateUser() : check identity or user
- dataProcess() : Analyze data before saving
- saveData(): save data session into database
- dbQuery() : is a class with many child functions, use for query tasks from database.



