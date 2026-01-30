# Fitness Track Database

## I.	System documentation

### 1.	Executive summary 

This database aims to monitor user’s fitness activities like calories burned, nutrition, goals and progress over time. It allows users to set goals and track their progress. The system has different tables (interconnected) that help to manage information about users’ profile, goals, nutrition and coach details. 

### 2.	Purpose and keys features

The implementation of this database will help to do some calculations automatically (apply aggregations functions to determine the average, maximum calorie burned, exercise duration, week frequency, weight loss or gain, number of users enrolled for a specific session, …), track nutrition and goal progress, thereby enhancing user experience and overall fitness management.

In details, the advantages of a creating a fitness system are the follow: 

-	This system facilitates data storage, maintenance and data retrieval (make the data storage and retrieval simple and rapid),
-	Store and manage users’ information (personal and their activities at the fitness club), theirs goals, and track the progress toward their goals (users management), 
-	Manage user’s nutrition and their instructors (instructor/nutritionist management),
-	Keep tracks with detailed statistics,
-	It minimizes manual entry data and helps to manage reduce time (time efficiency).
-	The system increases transparency, integrity, accuracy and efficiency.  
-	Can store records for many years, manager can easily for last month or years.

### 3.	Users and their roles

**The system administrator** is responsible for overseeing and maintaining our database infrastructure, which includes security, backup, updates, performance, managing user access and permission, and handling any issues that may arise. 

**The fitness instructor** updates and accesses fitness record, creates and innovates fitness plans for users, trains and tracks their progress, and manages the nutritionist's information about their nutrition plan. 

**The nutritionist** evaluates the user's calorie burn and consumption, proteins consumed, and gives advice on their goals, diets, and consumption behaviour. 

**The user** is at the centre of fitness activities; he is responsible for his personal fitness and diet, and it is his duty to adhere to his or her goals and exercise regimen. Be prepared to accept and put coaches' and dietitians advise into practice. 

**The data analyst** is responsible for pre-processing the data, performing statistical analysis (finding patterns between users’ characteristics, progress trends, etc.), deploying the model, and narrating the story in a report since the fitness club uses fitness data to back its decisions. Users may occasionally run into system-related technical problems. 

**IT support** is responsible for helping them and resolving technical issues. Take use of the system's input and strengthen it.

Capitalize users’ comments and strengthen the system. The fitness manager oversees the club, establishes policies for patrons and employees, and evaluates exercise activities (effectiveness, quality control, etc.).

### 4.	Key entities and their functions

The key entities are : Users, Goals, Progress, Nutrition, Instructor, and Exercices

<img width="751" height="322" alt="image" src="https://github.com/user-attachments/assets/3ed7fb44-77e4-4fb2-8769-d05a04ec8bcf" />


### 5. Conceptual model using an ER diagram Crow's Foot notation

<img width="567" height="579" alt="image" src="https://github.com/user-attachments/assets/31c7617c-f483-4c6e-bb6a-cdfe432391d6" />

### 6.	Entity relationship and business rules

<img width="575" height="622" alt="image" src="https://github.com/user-attachments/assets/113739c9-d51e-45d5-b3f0-1cb5bc013b06" />

### 7. Normalization Documentation

#### A. First Normal Form 
**1NF** ensures that each record is unique and each table has a primary key.  For our database, some attributes were not in their atomic form(user address, user name, instructor address and instructor name). The potentials candidates keys are the follow: UserID, GoalID, ExerciceID, NutritionID, ProgressID.
To tackle that problem, we separate the first and last names of both users and instructors (user first name, user surname, instructor first name, and instructor second name). For the user and instructor addresses, we broken them into user street, user city, instructor street and instructor city.

<img width="8588" height="219" alt="image" src="https://github.com/user-attachments/assets/b92358cd-26c1-4f2a-a303-d27c3b9e05ab" />

#### B. 2nd Normal Form






