### Use case scenarios

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
| Assumption | <ul><li> •	Students possess registered accounts </li><li>	Students have already enrolled for the courses</li></ul> |
