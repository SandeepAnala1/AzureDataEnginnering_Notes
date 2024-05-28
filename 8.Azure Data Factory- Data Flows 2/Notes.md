Continuation of Data Flow Notes, previous notes can be found [here](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/blob/main/7.Azure%20Data%20Factory-%20Data%20Flows%201/Notes.md)
- Let's start with a question
# Instead of using Mapdrifted is there a way to get columns without import projection?
Ans: With byName you can dynamically use columns without Mapdrifted

![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/c47dc203-4c15-41a1-a599-0db3a388d392)

- To make this work dynamically, we need to ensure for the dataset, First row as header is enabled
![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/2ad6e356-8527-448a-9579-e78f29fc743b)

# Transformations resumed
     6) Interested in how a movie ranks within its year for its specific genre.
     7) For every genre and year, let's get the average Rotten Tomatoes rating, the highest and lowest rated movie and the             number of movies that are in each group.
     8) Set the data Quality /Validation if validation fails send the data to error.
     9) If data is older than 1970 move to processed folder
     10) If data is greater than 1970 move to sqldb

## Rank ((6) Interested in how a movie ranks within its year for its specific genre.)
    
    SELECT 
      RANK() / DENSE_RANK() / ROW_NUMBER() OVER ( -- Compulsory expression
        PARTITION BY partitioning_expression -- Optional expression
        ORDER BY order_expression) -- Compulsory expression
    FROM table_name;
## Pseudo code
![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/21bb8ba6-33ac-4f4b-bdc2-0f47aa6c4510)


We use Window activity for movie rank
![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/3a24f40a-6b66-4bfe-941d-e12d7818e9bf)
![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/8c6d7602-6f7e-40ca-abf6-01570853fa07)
![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/0a187440-5ea2-48c1-b98b-3f7680cf705a)
![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/a6bb209a-550d-46a5-93c0-afdb985e670d)

### ROW_NUMBER vs. RANK vs. DENSE_RANK

ROW_NUMBER(): This function assigns a unique sequential number to each row within a window. It's like numbering the rows in order.

RANK(): The RANK() function handles tied values by assigning the same rank to them. However, it may skip subsequent ranks, leaving gaps in the sequence.
If we are ranking by year and if it has duplicates, rank will skip the duplicate ones. But dense rank gives them a unique rank

DENSE_RANK(): Similar to RANK(), DENSE_RANK() also handles tied values by assigning the same rank. However, it does not skip ranks, resulting in no gaps in the sequence.

Note: If we are ranking by year and if it has duplicates, rank will skip the duplicate ones. But dense rank gives them a unique rank


## Aggregate (For every genre and year, let's get the average Rotten Tomatoes rating, the highest and lowest rated movie and the number of movies that are in each group.)

### Pseudo code
![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/a803d040-22dd-475f-883e-3b8d6beed691)

![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/83c54014-dd6e-4e3c-9e2f-1916199251ab)

![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/a88ac67c-125c-4120-a58d-1529723b41b9)

![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/61093804-685d-48cf-a556-80c90211216b)

---------------------------------------------------------------------------------------------------------------------

# Data Quality Check
###Layman Explanation
      Before we sink any data after doing transformation, it should be the clean data. We need to do quality validation to ensure that there is no bad data going to sink

### Assert Activity
![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/085d0212-011f-41c0-8351-64b1c55b4f47)

Here for Assert, it's description is important to get the error file into error container. Else it will show as O byte with no data
![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/da223c0b-dfff-41fa-b80c-b97690048bbc)

![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/e09d7a7d-d037-4d53-8fc9-e12f5880a034)


In Sink Activity error section, you'll find the Assert failure storage path
![image](https://github.com/SandeepAnala1/AzureDataFactory_Notes/assets/163712602/fb671d37-0547-4d0a-bd6b-240e819e9825)

# & Logic Apps !
It is a service provided by Azure, used to integrate two different services



























