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


**Task 1: Removing unwnated columns**


![image](https://user-images.githubusercontent.com/53274845/236833824-448a67b0-ed65-4e2b-bc84-3dfb488bf786.png)

**Task 2: Renaming and selecting columns in the dataset**

Only these columns are allowed in the dataset:
1.    Id
2.    name
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

![image](https://user-images.githubusercontent.com/53274845/236852431-2d0ac8da-301a-47ee-b537-93df1a5e41e1.png)

 **Task 3: Dealing with null values in dataset**
 
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

![image](https://user-images.githubusercontent.com/53274845/236850887-0688ef7c-b42e-421a-a8a9-83472ca4fb80.png)

![image](https://user-images.githubusercontent.com/53274845/236852691-bf00a323-fd8a-4a5c-a264-e297a5f94676.png)

**Task 4: Identifying duplicate data in the dataset**

 drop all the duplicate values keeping the first value as it is
 
 ![image](https://user-images.githubusercontent.com/53274845/236851987-80fb7e56-5be7-4d2c-bdb9-3398fec1c54e.png)
 
 ![image](https://user-images.githubusercontent.com/53274845/237009576-6d617cdd-d004-4af4-9ec3-196b36cb2f4b.png)


 


**Task 5: Text cleaning**

 we have irrelevant reviews like string eg(RATED,Rated) in our name,online_order etc columns
 remove this irrelevant text from all the columns
 
![image](https://user-images.githubusercontent.com/53274845/237009687-5b5cb79c-e509-4ee4-a920-101b195d64e0.png)

![image](https://user-images.githubusercontent.com/53274845/237009742-46eeb813-1e0c-4a3c-afa7-36941df174aa.png)


**Task 6: Unique value check and irrelevant value handling**

online order column should have only yes and no because it is necessary to have the online order as yes or no only for zomato to perform further analysis, remove other values
check for rating column and remove NEW,- values to 0 and remove /5 as rating column should only contain decimal values

![image](https://user-images.githubusercontent.com/53274845/237010053-b58fd5ce-bc91-47a9-9d5c-62f9273a6972.png)


![image](https://user-images.githubusercontent.com/53274845/237009968-ade4c99f-b58a-46dc-9551-4bcdf2d15773.png)


   
    
**Task 7: claening and exporting dataset**

remove the unknown character from the dataset, we have Ã charachter in our names column

![image](https://user-images.githubusercontent.com/53274845/237010326-8d4b30bc-7900-45f0-82a6-c5685ad00252.png)

    
    
**Task 8: datacleaning andanalysis with excel and mysql**

Step1: Download the exported data set "zomatocleaned.csv"

Step2: Eliminate any identical rows in the Excel dataset by performing the deduplication task.

Step3: Upload the final dataset to the database provided to conduct an analysis in MySQL.

Step4: Retrieve the database host, username, password, and database information from the "Database Info" tab and input it into db.py.

Step5: To complete the current task, click on "Run Test" and confirm that your table has been successfully created.


#check if mysql table is created using "zomatocleaned.csv"
#Use this final dataset and upload it on the provided database for performing analysis in  MySQL
#To Run this task first Run the appliation for Terminal to create table named 'Zomato' and then run test.
def start():
    remove_the_unknown_character()

def task_runner():
    start()

**Module 2 Data analysis using SQL**

![image](https://user-images.githubusercontent.com/53274845/237012910-02e436a1-6b16-41d3-944c-29ad49cdaf0c.png)

![image](https://user-images.githubusercontent.com/53274845/237011090-a710b266-5792-463a-be15-4ea99fa8e3a1.png)

                                                        
**Task 1: 
For a high-level overview of the hotels, provide us the top 5 most voted hotels in the delivery category.**


SELECT name,votes,rating from zomato
where type='delivery'
order by votes DESC 
limit 5;


**Task 2: 
The rating of a hotel is a key identifier in determining a restaurant’s performance. Hence for a particular location called Banashankari find out the top 5 highly rated hotels in the delivery category.**

SELECT name,rating,location,type from zomato
where type='delivery' and  location ='Banashankari '
order by rating DESC 
limit 5;



**Task 3: 
Compare the ratings of the cheapest and most expensive hotels in Indiranagar.
 
![image](https://user-images.githubusercontent.com/53274845/237013059-645a0ed7-cf7f-4963-92c1-34231ce6e531.png)


    
**Task 4: 
Online ordering of food has exponentially increased over time. Compare the total votes of restaurants that provide online ordering services and those that don’t provide online ordering services.**

![image](https://user-images.githubusercontent.com/53274845/237013638-12968466-9e6b-47d5-bd20-22bbbceafabe.png)

**Task 5: 
Number of votes defines how much the customers are involved with the service provided by the restaurants For each Restaurant type, find out the number of restaurants, total votes, and average rating. Display the data with the highest votes on the top( if the first row of output is NA display the remaining rows).**

![image](https://user-images.githubusercontent.com/53274845/237015425-f8cd68d3-78c0-4f03-ab59-5997bffac593.png)

**Task 6: 
What is the most liked dish of the most-voted restaurant on Zomato(as the restaurant has a tie-up with Zomato, the restaurant compulsorily provides online ordering and delivery facilities.**
![image](https://user-images.githubusercontent.com/53274845/237015697-05bd6297-69be-4cb6-a833-01f6c7033a7a.png)

**Task 7:
To increase the maximum profit, Zomato is in need to expand its business. For doing so Zomato wants the list of the top 15 restaurants which have min 150 votes, have a rating greater than 3, and is currently not providing online ordering. Display the restaurants with the highest votes on the top.**

![image](https://user-images.githubusercontent.com/53274845/237016050-dd9ea586-dc0b-4303-935d-9338590eaacb.png)
    
    
    
  

    
    



   

