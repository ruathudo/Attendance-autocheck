Requirements

5.1 Functional requirements:

- User.login() : check weather user ID and password are correct or not. If invalid, will so a warning message.
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
- Course.addClass(): add new class to the course
- Course.delClass(): remove class from the course
- Course.save(): save all information for the course

- Class.getRoom() : get class room
- Class.getDate() : get date of the class
- Class.getTime() : get time start class
- Class.getDuration() : get the duration of class
- Class.edit(): edit time, duration,  date, room... of class

  Client Function:
- validateInput(): validate all input for security reason
- countTime(): time counter function to calculate percent of work done during class
- sendSessionInfo() : send the session information to server for processing.
- trackPos(): track user position using indoor navigation API, return the position in longtitude-latitude

  Server Function:
- validateInput(): validate input second time to ensure security
- validateUser() : check identity or user
- dataProcess() : Analyze data before saving
- saveData(): save data session into database
- dbQuery() : is a class with many child functions, use for query tasks from database.
- getloc(): get the location based the position of user send to server, return location eg: B213


5.2 Non-functional system requirements:

  - Usability:
    To ensure. As description, It only needs a device with wifi connection. Nowadays, everybody, especially IT student must have at least 1 wireless device, so it may not be a problem. About functionality, It must be automatic and visual. Students just need to login and press 1 button: start check. If is there any exception, student can press exception mode button and leave an message. 

  For teacher's part, he can get a list courses belong to him, select one course and start working with. By default, the course will come with accepted students. However, teacher can also add new student to the course just by add button. delete or edit is the same. Setting a class is also simple like filling a form. Any one can do it with a normal knowledge about computer.
    
  - Reliability: 
    To ensure system is realiable, we have make serveral exceptions for that. For example, input valid in both client and server ensure nobody can put a bad stuff on. All private data is protected by hash. if any one have a dropped signal or battery running out or any accident with his phone, application will collect device's status and let student send it to the teacher with message. Of course, it rarely happends because nobody want to cheat with a low battery phone in every week. 
    If some students don't have any smart phone, tablet... they can ask teacher check mannualy by his phone. So nobody will miss the class.

  - Efficiency: 
    This application will save many time for both students and teachers. Students don't need to wait in queue for signing in the paper. No paper equal with no tear, no lost. All information will be stored in server. Teachers don't have to calculate how many percent students presented, application will do it. The data is going to be stored for long time. People can retrieve them like a big data to do some statistical research.
    
  - Other non-functional requirements:
    - Maintainance: The system must be easy to edit and maintain for any IT technical.
    - Flexibility: This application must be compatible with many platform as ios, android, windows phone...etc
    - Size: This app must have a small size and use little device resource.
    - Extensibility: The system can be extenable for the future.
    - Capacity
    - Security
    - Scalability
    - Performance
    - Accuracy
    - Usability
    - Reliability
    - Efficiency

