# OnlineBankingSystem
Online Banking System Full Project (4 CRUD Functions)

Used Tools

Mysql - MySQL Workbench 8.0 CE

java - java version "18.0.2" 2022-07-19
Java(TM) SE Runtime Environment (build 18.0.2+9-61)
Java HotSpot(TM) 64-Bit Server VM (build 18.0.2+9-61, mixed mode, sharing)

Apache tomcat 9.0

MySql-connector-java-8.0.30

Eclipse IDE for Java Developers - 2022-03

SQL

create database bank;
use bank;
select * from customers;
INSERT INTO customers (Name, Email, Password, Phone, Address)
VALUES
    ('John Doe', 'johndoe@example.com', 'password123', '1234567890', '123 Main St'),
    ('Jane Smith', 'janesmith@example.com', 'p@ssw0rd', '9876543210', '456 Elm St'),
    ('Michael Johnson', 'michaeljohnson@example.com', 'securepass', '5555555555', '789 Oak St'),
    ('Sarah Williams', 'sarahwilliams@example.com', 'mypassword', '1112223333', '321 Pine St'),
    ('David Brown', 'davidbrown@example.com', 'brown123', '4444444444', '567 Walnut St'),
    ('Emily Taylor', 'emilytaylor@example.com', 'password456', '8888888888', '901 Maple St'),
    ('Matthew Davis', 'matthewdavis@example.com', 'davismatt', '7777777777', '234 Cedar St'),
    ('Olivia Martinez', 'oliviamartinez@example.com', 'password789', '9999999999', '345 Birch St'),
    ('Daniel Anderson', 'danielanderson@example.com', 'daniel123', '6666666666', '678 Oakwood St'),
    ('Sophia Thomas', 'sophiathomas@example.com', 'thomas456', '2222222222', '789 Maplewood St');

CREATE TABLE contactUs (
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL,
    subject VARCHAR(255) NOT NULL,
    message TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
select * from contactUs;
INSERT INTO contactUs (Name, Email, Subject, Message)
VALUES
    ('Sophia Thomas', 'sophiathomas@example.com', 'Feedback', 'Your customer service team was very helpful.'),
    ('John Doe', 'johndoe@example.com', 'Inquiry', 'I have a question about your products.'),
    ('Jane Smith', 'janesmith@example.com', 'Feedback', 'I just wanted to say how satisfied I am with your service.'),
    ('Michael Johnson', 'michaeljohnson@example.com', 'Complaint', 'I had a negative experience with one of your employees.'),
    ('Sarah Williams', 'sarahwilliams@example.com', 'Order Inquiry', 'I want to check the status of my recent order.'),
    ('David Brown', 'davidbrown@example.com', 'Product Support', 'I need assistance with setting up the product.'),
    ('Emily Taylor', 'emilytaylor@example.com', 'Feedback', 'Your company has exceeded my expectations.'),
    ('Matthew Davis', 'matthewdavis@example.com', 'General Inquiry', 'I have a question about your company policies.'),
    ('Olivia Martinez', 'oliviamartinez@example.com', 'Complaint', 'I received a damaged product.'),
    ('Daniel Anderson', 'danielanderson@example.com', 'Product Inquiry', 'I would like more information about your new product.');

CREATE TABLE transactions (
    transaction_id INT PRIMARY KEY AUTO_INCREMENT,
    timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    amount DECIMAL(10, 2),
    sender VARCHAR(255),
    receiver VARCHAR(255),
    description VARCHAR(255),
    status VARCHAR(20)
);
INSERT INTO transactions (timestamp, amount, sender, receiver, description, status) VALUES
    (CURRENT_TIMESTAMP, 100.00, 'John Doe', 'Jane Smith', 'Payment for services', 'Completed'),
    (CURRENT_TIMESTAMP, 50.00, 'Alice Johnson', 'Bob Williams', 'Product purchase', 'Completed'),
    (CURRENT_TIMESTAMP, 75.50, 'Sarah Thompson', 'Michael Davis', 'Loan repayment', 'Completed'),
    (CURRENT_TIMESTAMP, 200.00, 'David Brown', 'Emily Wilson', 'Shared expense', 'Completed'),
    (CURRENT_TIMESTAMP, 30.00, 'Robert Lee', 'Olivia Taylor', 'Dinner bill', 'Completed'),
    (CURRENT_TIMESTAMP, 120.75, 'Sophia Anderson', 'Daniel Clark', 'Monthly subscription', 'Completed'),
    (CURRENT_TIMESTAMP, 80.50, 'Emma Hall', 'Matthew Turner', 'Online purchase', 'Completed'),
    (CURRENT_TIMESTAMP, 25.00, 'Oliver Evans', 'Ava Moore', 'Gift card redemption', 'Completed'),
    (CURRENT_TIMESTAMP, 60.25, 'Logan Nelson', 'Chloe Green', 'Donation to charity', 'Completed'),
    (CURRENT_TIMESTAMP, 150.00, 'Ethan Perez', 'Grace Harris', 'Rent payment', 'Completed'),
    (CURRENT_TIMESTAMP, 45.50, 'Liam Rivera', 'Zoe Brooks', 'Utility bill', 'Completed'),
    (CURRENT_TIMESTAMP, 90.00, 'Mia Mitchell', 'Sebastian Hughes', 'Event ticket purchase', 'Completed'),
    (CURRENT_TIMESTAMP, 15.75, 'Lucas Price', 'Harper Butler', 'Coffee purchase', 'Completed'),
    (CURRENT_TIMESTAMP, 70.00, 'Jackson Simmons', 'Luna Foster', 'Reimbursement', 'Completed'),
    (CURRENT_TIMESTAMP, 50.25, 'Aiden Powell', 'Stella Reed', 'Pet supplies', 'Completed'),
    (CURRENT_TIMESTAMP, 40.50, 'Carter Cook', 'Victoria Gray', 'Grocery shopping', 'Completed'),
    (CURRENT_TIMESTAMP, 85.00, 'Penelope Bell', 'Aiden Powell', 'Service fee', 'Completed'),
    (CURRENT_TIMESTAMP, 200.00, 'Daniel Scott', 'Nora Morgan', 'Loan disbursement', 'Completed'),
    (CURRENT_TIMESTAMP, 20.25, 'Sofia Phillips', 'Henry Ward', 'Movie ticket purchase', 'Completed'),
    (CURRENT_TIMESTAMP, 55.50, 'Joseph Diaz', 'Lily Simmons', 'Restaurant bill', 'Completed');

select * from transactions;
ALTER TABLE transactions
DROP COLUMN timestamp;

CREATE TABLE favourites (
    id INT AUTO_INCREMENT PRIMARY KEY,
    accountNumber VARCHAR(50) NOT NULL,
    bankName VARCHAR(100) NOT NULL,
    accountHolderName VARCHAR(100) NOT NULL,
    branch VARCHAR(100) NOT NULL
);

INSERT INTO favourites (accountNumber, bankName, accountHolderName, branch)
VALUES
    ('1234567890', 'Bank A', 'John Doe', 'Branch A'),
    ('9876543210', 'Bank B', 'Jane Smith', 'Branch B'),
    ('5555555555', 'Bank C', 'Michael Johnson', 'Branch C'),
    ('1111111111', 'Bank D', 'Emily Davis', 'Branch D'),
    ('9999999999', 'Bank E', 'Robert Wilson', 'Branch E'),
    ('7777777777', 'Bank F', 'Jessica Brown', 'Branch F'),
    ('2222222222', 'Bank G', 'Christopher Taylor', 'Branch G'),
    ('4444444444', 'Bank H', 'Sophia Anderson', 'Branch H'),
    ('6666666666', 'Bank I', 'William Martinez', 'Branch I'),
    ('8888888888', 'Bank J', 'Olivia Thomas', 'Branch J'),
    ('3333333333', 'Bank K', 'Daniel Clark', 'Branch K'),
    ('7777777777', 'Bank L', 'Isabella Scott', 'Branch L'),
    ('2222222222', 'Bank M', 'Andrew Wright', 'Branch M'),
    ('1111111111', 'Bank N', 'Mia Green', 'Branch N'),
    ('9999999999', 'Bank O', 'David Hall', 'Branch O'),
    ('5555555555', 'Bank P', 'Abigail Turner', 'Branch P'),
    ('4444444444', 'Bank Q', 'James Adams', 'Branch Q'),
    ('6666666666', 'Bank R', 'Charlotte Lee', 'Branch R'),
    ('8888888888', 'Bank S', 'Ethan Hernandez', 'Branch S'),
    ('1234567890', 'Bank T', 'Sofia Young', 'Branch T');

select * from favourites;
