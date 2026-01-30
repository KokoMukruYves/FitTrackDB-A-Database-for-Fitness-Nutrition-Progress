# Fitness Track Database

<img width="766" height="283" alt="image" src="https://github.com/user-attachments/assets/953face4-9757-4b3b-bf6b-2f7e7983f0cc" />

<details>
<summary id="Systement- Documentation"> I.	System documentation</summary>


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


</details>

---

<details>
<summary id="Normalization - Documentation"> II. Normalization Documentation</summary>

#### A. First Normal Form 

 1NF ensures that each record is unique and each table has a primary key.  For our database, some attributes were not in their atomic form(user address, user name, instructor address and instructor name). The potentials candidates keys are the follow: UserID, GoalID, ExerciceID, NutritionID, ProgressID.
To tackle that problem, we separate the first and last names of both users and instructors (user first name, user surname, instructor first name, and instructor second name). For the user and instructor addresses, we broken them into user street, user city, instructor street and instructor city.


#### B. 2nd Normal Form


Our tables are already in the 1NF, the next step was to check if there are any instances of partial dependencies. At this stage, it was preferable to verify that every non-key attribute depends entirely on the primary key functionality.  After checking, we realize that there’s no instance of partial dependency (all non-key attributes depend on the whole primary keys). So, our tables are already in 2NF.

#### C. Third Normal Form (3NF)

3NF ensures that our tables has no problem of partial dependency. The next step was to check if there are any instances of transitive dependencies. Unfraternally, there is a transitivity dependency of street on city for both users and instructor tables. And also between the number of sets and number of repetitions, because a set is a collection of repetitions.
 To solve that challenge, new tables named user address and instructor address should be created.  And remove the 2 transitive attributes in the progress table by creating a new table.##

#### D. Fourth Normal Form (4NF)

The tables are already in the 3NF and there is no multi-valued dependency (any non-key attribute has multiple entry instance of one of the composite keys).  Thus, our tables are in the 4 NF already.
#### Normalized table

<img width="722" height="337" alt="image" src="https://github.com/user-attachments/assets/0b5984cc-0cb2-4e57-ab6b-f8db6a21660a" />


</details>

---

<details>
<summary id="System-implementation-using-SQL-Server-Management-Studio"> III. System implementation using SQL Server Management Studio</summary>

### •	Create the Database
 <img width="477" height="526" alt="image" src="https://github.com/user-attachments/assets/397b7dd8-23c0-4a93-be25-4e1d9414d33c" />

### III.1.  Create Tables
#### 1.	Create user address table
<img width="838" height="136" alt="image" src="https://github.com/user-attachments/assets/60f65332-f549-4fdd-bf89-fb1b37e44206" />

##### 2.	Create users table
<img width="945" height="225" alt="image" src="https://github.com/user-attachments/assets/ee741354-e002-496a-a740-10448224fb3e" />
 
##### 3.	 Create Goals table
<img width="945" height="225" alt="image" src="https://github.com/user-attachments/assets/ebf020f8-eefe-4ce3-ab14-2397ca48bcfc" />

##### 4.	 Create Exercise table
<img width="945" height="167" alt="image" src="https://github.com/user-attachments/assets/23674cce-6346-4ee8-8c1b-4f4b448035f3" />
 
5.	Create Nutrition table
<img width="945" height="162" alt="image" src="https://github.com/user-attachments/assets/7c415164-4610-4483-85ac-ef996aa594d5" />

6.	Create Progress table
<img width="945" height="185" alt="image" src="https://github.com/user-attachments/assets/442e1218-1233-4ef5-8a08-09260eccb0ec" />

7.	 Create Work out details table
<img width="903" height="150" alt="image" src="https://github.com/user-attachments/assets/644522f3-2687-4656-90b2-4de7eb3615d5" />

8.	Create ProgressWorkout_jonc table
<img width="859" height="175" alt="image" src="https://github.com/user-attachments/assets/d998e564-b875-4ee5-901f-7f3f4a2a09f6" />

9.	 Create Instructor address table

<img width="945" height="151" alt="image" src="https://github.com/user-attachments/assets/b69c0eb6-c099-4cfc-a55c-b95c61362b08" />

10.	 Create Instructor table

<img width="945" height="149" alt="image" src="https://github.com/user-attachments/assets/6973fa50-082f-4ffb-a2db-b4c263e277c7" />

### III.2. Values insertion in the created tables
#### 1.	Values insertion into users table

<img width="945" height="267" alt="image" src="https://github.com/user-attachments/assets/e4778d58-7d41-4af3-a676-1bd27bb1c426" />

#### 2.	Values insertion into Exercise table

<img width="945" height="324" alt="image" src="https://github.com/user-attachments/assets/b1e9a11f-34c5-4bb0-93af-55b7c160ae29" />

#### 3.	Values insertion in UserAddress table

<img width="431" height="389" alt="image" src="https://github.com/user-attachments/assets/72473cf1-95b5-44b7-92b5-732414518381" />

#### 4.	Values insertion into User_Exercice_Joinction Table 

<img width="361" height="380" alt="image" src="https://github.com/user-attachments/assets/8c759c68-0eb1-430b-baea-d111569c2a3e" />

#### 5.	Values insertion in Goals table
<img width="945" height="368" alt="image" src="https://github.com/user-attachments/assets/1e0c466c-4f6d-4e58-85d4-27e5d01a596d" />

#### 6.	Values insertion into Nutrition table
<img width="945" height="356" alt="image" src="https://github.com/user-attachments/assets/66a489cd-afa3-450b-b4cd-f8f8ebe1d893" />

#### 7.	Values insertion into work out details table
<img width="478" height="372" alt="image" src="https://github.com/user-attachments/assets/29867939-75c6-4812-bf88-5837b9e7c6e5" />
 
#### 8.	Values insertion into progress table
<img width="592" height="370" alt="image" src="https://github.com/user-attachments/assets/a0510511-4e5c-4793-ad74-7feca577abea" />

 
#### 9.	Values insertion into progress workout junction 
<img width="477" height="380" alt="image" src="https://github.com/user-attachments/assets/b0e66643-4f6b-4f28-a768-d12e408473b1" />

#### 10.	Values insertion into Instructor address table

<img width="569" height="370" alt="image" src="https://github.com/user-attachments/assets/6840b0f6-98de-4d2f-a4a5-b8fb3e52a223" />

#### 11.	Values insertion into instructor table

<img width="945" height="269" alt="image" src="https://github.com/user-attachments/assets/ba0038a9-3496-4a71-b7d6-d8753760c693" />

</details>

---

<details>
<summary id="System-functionality-demonstaration"> III. System functionality demonstration </summary>

### 1. Select all records in Exercise Table

<img width="945" height="305" alt="image" src="https://github.com/user-attachments/assets/bde3d26a-6552-42a4-9ce8-72e060968cfc" />

### 2. Select user who burned more than 2000 Kcal
<img width="945" height="148" alt="image" src="https://github.com/user-attachments/assets/3c7139ef-fd08-430b-9b02-afc196777c6b" />

### 3. Select Exercice Duration and exercice type from Exercice table

<img width="303" height="370" alt="image" src="https://github.com/user-attachments/assets/4de0a01f-c997-4d2e-bd59-05d630f88987" />

### 4. Count the number of users who did Yoga and with a duration activity equals to 1, and  with calory burned greater than 1200 and used to train Biceps
<img width="230" height="106" alt="image" src="https://github.com/user-attachments/assets/5a8eba01-45ea-42ab-83d7-9a8a0f403844" />

### 5. Select people who did start_exercice between 11:00  and 19:00 

<img width="342" height="172" alt="image" src="https://github.com/user-attachments/assets/b3c15035-d5ba-4692-ab84-61a93238be5b" />

### 6. Compute the average of calory burned per hour for user who did exercise between 11:00  and 19:00 
<img width="330" height="225" alt="image" src="https://github.com/user-attachments/assets/e2ff2cc7-3721-4eed-88e7-55e7b5b60890" />

### 7. Select the name of the user who performed multiples exercises
<img width="491" height="148" alt="image" src="https://github.com/user-attachments/assets/a7a04d15-be28-4917-92b7-bd14e11a1e45" />

### 8. Select users for whom their goals will expire before '2025-11-01'
<img width="945" height="295" alt="image" src="https://github.com/user-attachments/assets/5e3b78b1-1233-4cd1-bd97-8705ff559af6" />

### 9. Select Users with a goal description is Fat lose and with professional level of complexity

<img width="945" height="135" alt="image" src="https://github.com/user-attachments/assets/cba5687d-00b0-4699-8e4e-2d60873294c1" />

### 10. Select users older than 40
<img width="945" height="111" alt="image" src="https://github.com/user-attachments/assets/52fb5edc-84bd-4b62-af30-abf91316a691" />

### 11. Select Users with a BMI greater than 30 (susceptible to obesity)
<img width="320" height="133" alt="image" src="https://github.com/user-attachments/assets/067abf92-3a44-46d6-87ad-b8f6dfe393eb" />

### 12. Select Users who consumed proteins is greater than the mean 
<img width="945" height="114" alt="image" src="https://github.com/user-attachments/assets/2b9f434c-02db-4ea1-a987-2fc01a2bf19c" />

### 13. Update the feeding type for a specific nutrition record
#### Before
<img width="945" height="60" alt="image" src="https://github.com/user-attachments/assets/8ea04a9c-f263-484c-ac39-fd5d90aa3de5" />
#### After updating
<img width="945" height="51" alt="image" src="https://github.com/user-attachments/assets/68bf0ae8-4d5f-4e0d-b3df-a30a3ea3db77" />

### 14. Select User with a high week frequency
<img width="628" height="141" alt="image" src="https://github.com/user-attachments/assets/2ab4ef71-a720-419b-801d-cba961c36c1c" />
### 15. Compute the average weight lost for all users
<img width="200" height="72" alt="image" src="https://github.com/user-attachments/assets/b3ae1eb2-6c83-4484-b258-7ae43c160bc6" />

### 16. Select Instructor who are specialist in nutrition

<img width="945" height="159" alt="image" src="https://github.com/user-attachments/assets/a15ddc81-2e8c-4193-be86-dc1539bfa1bf" />

### 17. Find Users with Specific Goals and Their Instructors

<img width="786" height="191" alt="image" src="https://github.com/user-attachments/assets/01ba348b-c58b-448b-81a0-5edd692da000" />

### 18. Compute the total Calories Burned by Users with a certain Medical Conditions
<img width="377" height="134" alt="image" src="https://github.com/user-attachments/assets/b6a6dc54-21ed-4ecc-a24b-927696c03124" />

### 19. Find Users with the Most Calories Burned
<img width="455" height="153" alt="image" src="https://github.com/user-attachments/assets/b93596bc-d959-43a9-b705-230704888fcb" />

### 20. Users who met their goals
<img width="723" height="147" alt="image" src="https://github.com/user-attachments/assets/4ad81469-fcb3-4aac-badb-1f12f1ccac14" />

### 21. Identify the most common exercise
<img width="355" height="130" alt="image" src="https://github.com/user-attachments/assets/21327da6-461f-4dc8-8bb4-fcf61c73a12f" />

### 22. Users with most calories consumed on a specific date

<img width="470" height="136" alt="image" src="https://github.com/user-attachments/assets/50512f08-24aa-4230-966d-47ee9263cbb3" />

### 23. Find the exercise performed by each user last moth 
<img width="625" height="384" alt="image" src="https://github.com/user-attachments/assets/1914ac2d-cb3c-4eec-9d5b-5c879eff7037" />

</details>

---

<details>
<summary id="DB-Weakness-and-future-perspectives"> IV. DB Weakness and future perspectives</summary>

In terms of futures improvements, an online system could be the best because it offers users the possibilities to follow this progress everywhere on the globe. And facilitate the communication between users and staff.

Also, this design meets his main goal but there are some aspects of the gym that can be include in order to ensure his completes: manage equipment inventory, payment and billing, feedback and reviews.

Finally, the system needs to be updated regularly the system to avoid obsolescence. And to be evaluate/tested in a really world to ensure that it satisfied the business requirement.

</details>

---

## 📬 Contact

**© 2026 Koko Mukuru Yves**. All rights reserved.

For questions or collaborations, feel free to reach out!

Email: kmukuru_yves@st.ug.edu.gh 

LinkedIn: https://www.linkedin.com/in/koko-mukuru-yves-98621a14a










