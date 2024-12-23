# Microservice Project setup
Architecture of the microservice for code checkout main branch
A small demo is attached

https://github.com/user-attachments/assets/5ba3fbf7-db92-4ecf-a196-5e4003d1e588

There are two db here one is questiondb and quizdb. questiondb contains all the questions along with the all the details. and quizdb is only accessing the questiondb with id for three methonds getscore,generate quiz and get question. here also question service is running.
![image](https://github.com/user-attachments/assets/08fd22ea-515d-4839-8351-4f201ccfd420)

for db setup pgadmin4 is being used with two db as shown below
![image](https://github.com/user-attachments/assets/88a21d23-a4bc-4566-ab9d-4f683491dcf4)

Need to insert the data into the table with the following example

INSERT INTO Question (id, category, difficultyLevel, option1, option2, option3, option4, question_title, right_answer) VALUES (1, 'Java', 'Easy', '8 bits', '16 bits', '32 bits', '64 bits', 'What is the size of int in Java?', '32 bits');
and 
quiz db has ids as
![image](https://github.com/user-attachments/assets/a727185f-f394-48f9-8a1d-147a01c1e76c)




![image](https://github.com/user-attachments/assets/76128b99-b650-4436-ba05-8be3b861bc0b)

Euraka server(running on port 8761) is being used for discovery and register to service registery so that each microservice is aware of the other and can check there
![image](https://github.com/user-attachments/assets/4cb1ee0f-d38e-4c80-8b25-6d4d6eb52343)
instances of eureka server which are up
![image](https://github.com/user-attachments/assets/3301e5a5-f324-49da-a809-67cf136ffad6)


quiz to question calling b/w microservice --> here the quiz service(running of port 8090) is asking to question serive the question and this is being done by openfeign 
![image](https://github.com/user-attachments/assets/a1fce603-88dc-4211-8723-db62de29e343)

load balancing two instances of same microservice --> two instance of question serivce is running on port 8080 and 8081 and load balancing is being done by spring cloud.
![image](https://github.com/user-attachments/assets/0b5bf1d4-a2ad-4c75-9b41-2c5b7aafc34f)


api gateway --> running of port 8765
![image](https://github.com/user-attachments/assets/d8c2f069-4b84-47e1-a42a-e2d721583bfd)


