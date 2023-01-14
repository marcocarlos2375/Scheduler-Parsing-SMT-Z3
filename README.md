# Scheduler_Parser_with_Z3


### Description:
The project is a tool for reading data from a file and parsing them in a valid form to use the Z3 theorem prover to find solutions, if they exist. 
E.g. a number of tasks with their durations and dependencies are given. The program will dive the start and end time for each task if a solution exists. If not, a default message will be printed like "Unsolvable!"<br>
Of Course with Python :)
### Requirements : 
* Python 3.x
* Z3 library for Python (can be installed via pip)

### File Format :
The data file should be formatted as follows:
* The file should contain a task name (task + task number)
* The duration of a task should be clearly defined by the keyword "takes"
The dependencies of a task are defined by the keyword "takes". A task can depend on other tasks, meaning it can't start before the other one ends, or maybe it needs no other tasks to start (none)
### Example:

* Input: "Scheduler-Parsing-SMT-Z3/SimpleScheduling-master/Examples/scheduling_problem" <br>
Task1 <br>
takes 1 <br>
needs none <br>
Task2 <br>
takes 2 <br>
needs ((Task1 and Task3) or Task4) <br>
Task3 <br>
takes 3 <br>
needs Task2 <br>
Task4 <br>
takes 2 <br>
needs (Task2 or Task1)

* output: <br> Task1: begin 0 end 1 <br>
Task2: begin 3 end 5 <br>
Task3: begin 5 end 8 <br>
Task4: begin 1 end 3 <br>
[('Task1', 0, 1), ('Task2', 3, 5), ('Task3', 5, 8), ('Task4', 1, 3)]



### Another Examples and other cases in "Scheduler-Parsing-SMT-Z3/SimpleScheduling-master/Examples/"

## Please note: The parser part has been implemented by a colleague. I was responsible for Z3 part
