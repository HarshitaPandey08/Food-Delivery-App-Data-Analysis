# Food-Delivery-App-Data-Analysis

![image](https://user-images.githubusercontent.com/53274845/236834653-b76ae7ec-6d1a-4018-b81a-5e18d40d4249.png)


# Project Description

This project helps you to understand how a real-world database is analyzed using SQL, how to get maximum available insights from the dataset,
pre-process the data using python for better upcoming performance, and how a structured query language helps us retrieve useful information from the database.


There are two modules 
1.Data Processing using Python and Excel
2.Data analysis using SQL


Initially the uncleaned excel file had 13 columns and 56235 rows
1.    address
2.    name
3.    online_order
4.    book_table
5.    rate
6.    votes
7.    phone  
8.    location
9.    rest_type
10.    dish_liked
11.   cuisines
12.   approx_cost(for two people)
13.   listed_in(type)

![image](https://user-images.githubusercontent.com/53274845/236832853-dd482969-9db9-43ae-8211-b842325e3836.png)



**Module 1 Data Processing**

importing the necessary libraries for the data processing

![image](https://user-images.githubusercontent.com/53274845/236831523-6e663c29-fd44-4d80-a92a-06d9b3906eca.png)


**Task 1** : Removing unwnated columns


![image](https://user-images.githubusercontent.com/53274845/236833824-448a67b0-ed65-4e2b-bc84-3dfb488bf786.png)

**Task 2** : Renaming and selecting columns in the dataset

Only these columns are allowed in the dataset:
1.    Id
2.    Name
3.    online_order
4.    book_table
5.    rating
6.    votes
7.    location
8.    rest_type
9.    dish_liked
10.    cuisines
11.    approx_cost
12.    type

![image](https://user-images.githubusercontent.com/53274845/236849858-e518f87b-9732-4db0-962c-248cb8ede6f5.png)

![image](https://user-images.githubusercontent.com/53274845/236850233-1b664cb2-0b15-4c30-87c4-b92f2b7682ca.png)


 **Task 3** : Dealing with null values in dataset


    delete null values of name column as name is the primary identifier of the dataset
    replace null values of online order with NA
    replace null values of book_table with NA
    replace null values of rating to zero as it is a numerical datatype
    replace null values of votes to zero as it is a numerical datatype
    replace null values of location to NA
    replace null values of rest_type to NA
    replace null values of dishliked to NA
    replace null values of cuisines to NA
    replace null values of approxcost to 0 as it is a numerical value
    replace null values of type to NA

![image](https://user-images.githubusercontent.com/53274845/236850502-68b23b46-2119-4b1e-bb24-1a0b22581564.png)

![image](https://user-images.githubusercontent.com/53274845/236850636-78882a4a-a363-4c26-8bb0-e78073551a48.png)



