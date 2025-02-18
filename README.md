# Exercises: Creating Database and Tables

This exercise is preparation for the next exercises. You will need these tables in the following exercises. You can use MySQL Workbench.

Return either:
- a document containing SQL commands for each task
- or screenshots from MySQL Workbench showing that you have done the exercises

## Tasks

1. **Create a database called `mybusiness`.**  
   - 1 point

2. **Create the following tables with data.**  
   Be careful when creating these tables, as you will need them in the next exercises.  
   - 4 points

### `salesman` Table

| Column         | Type            | Description                                    |
|----------------|-----------------|------------------------------------------------|
| `salesman_id`  | int (Primary Key, Auto Increment) | Unique ID for each salesman                   |
| `name`         | varchar         | Name of the salesman                           |
| `city`         | varchar         | City where the salesman is located             |
| `commission`   | decimal(10,2)    | Commission rate for the salesman               |

| salesman_id | name        | city      | commission |
|-------------|-------------|-----------|------------|
| 5001        | James Hoog  | New York  | 0.15       |
| 5002        | Nail Knite  | Paris     | 0.13       |
| 5005        | Pit Alex    | London    | 0.11       |
| 5006        | Mc Lyon     | Paris     | 0.14       |
| 5007        | Paul Adam   | Rome      | 0.13       |
| 5003        | Lauson Hen  | San Jose  | 0.12       |
| 5010        | Ben Johnson | San Jose  | 0.13       |
| 5011        | Sam Lawson  | Santiago  | 0.11       |

### `customer` Table

| Column       | Type           | Description                              |
|--------------|----------------|------------------------------------------|
| `customer_id`| int (Primary Key, Auto Increment) | Unique ID for each customer      |
| `cust_name`  | varchar        | Name of the customer                     |
| `city`       | varchar        | City where the customer is located       |
| `grade`      | int            | Customer grade                           |
| `salesman_id`| int (Foreign Key) | Salesman ID associated with the customer |

| customer_id | cust_name     | city      | grade | salesman_id |
|-------------|---------------|-----------|-------|-------------|
| 3002        | Nick Rimando  | New York  | 100   | 5001        |
| 3007        | Brad Davis    | New York  | 200   | 5001        |
| 3005        | Graham Zusi   | California| 200   | 5002        |
| 3008        | Julian Green  | London    | 300   | 5002        |
| 3004        | Fabian Johnson| Paris     | 300   | 5006        |
| 3009        | Geoff Cameron | Berlin    | 100   | 5003        |
| 3003        | Jozy Altidor  | Moscow    | 200   | 5007        |
| 3001        | Brad Guzan    | London    | 300   | 5005        |
| 3010        | Marion Cameron| San Jose  | 300   | 5010        |

### `orders` Table (Note: `order` is a reserved word and cannot be used as a table name)

| Column       | Type            | Description                             |
|--------------|-----------------|-----------------------------------------|
| `ord_no`     | int (Primary Key, Not Null) | Unique order number         |
| `purch_amt`  | decimal         | Purchase amount                         |
| `ord_date`   | date            | Order date                              |
| `customer_id`| int (Foreign Key) | Customer ID associated with the order  |
| `salesman_id`| int (Foreign Key) | Salesman ID associated with the order  |

| ord_no | purch_amt | ord_date  | customer_id | salesman_id |
|--------|-----------|-----------|-------------|-------------|
| 70001  | 150.5     | 2012-10-05| 3005        | 5002        |
| 70009  | 270.65    | 2012-09-10| 3001        | 5005        |
| 70002  | 65.26     | 2012-10-05| 3002        | 5001        |
| 70004  | 110.5     | 2012-08-17| 3009        | 5003        |
| 70007  | 948.5     | 2012-09-10| 3005        | 5002        |
| 70005  | 2400.6    | 2012-07-27| 3007        | 5001        |
| 70008  | 5760      | 2012-09-10| 3002        | 5001        |
| 70010  | 1983.43   | 2012-10-10| 3004        | 5006        |
| 70003  | 2480.4    | 2012-10-10| 3009        | 5003        |
| 70012  | 250.45    | 2012-06-27| 3008        | 5002        |
| 70011  | 75.29     | 2012-08-17| 3003        | 5007        |
| 70013  | 3045.6    | 2012-04-25| 3002        | 5001        |
| 70014  | 1786.4    | 2012-06-25| 3004        | 5006        |
