# Index
- [Mapping Data Flows](#what-are-mapping-data-flows)
- [DataFlow Definition](#dataflow-definition)
- [Narrow Partition and Wide Partition](#narrow-partition-and-wide-partition)
- [UI](#ui)
- [Data Flow Use Case](#lets-learn-data-flow-with-a-usecase)
  - [Data Ingestion](#1data-ingestion)
  - [Transformation](#2transformation)
  - [Data Flow](#3dataflow)


# What are mapping data flows?
        
> #### Layman
>
> - Transformation  -> Cleansing the data
> 
> **Removing the null values, Casting the types, Filter, Formatting Data, Aggregation, Window Aggregations(Rank, Dense Rank...), Joins(left, right, cross join, self), Removing Duplicates**

# DataFlow Definition
Mapping data flows are visually designed data transformations in Azure Data Factory. 
Data flows allow data engineers to develop data transformation logic without writing code. The resulting data flows are executed as activities within Azure Data Factory pipelines that use scaled-out Apache Spark clusters.

  > Spark: Spark is a open source in memory(RAM) computation engine
    
  > Cluster: Pool of machines (computer) and from outside world it appears you are working in one machine

# Narrow Partition and Wide Partition:

- **Narrow Partition:** Think of it like a single lane road where only one car can pass at a time. It's efficient for smaller datasets or tasks where data processing can be done in a single step.
- **Wide Partition:** Now imagine a multi-lane highway where multiple cars can pass at once. This is useful for bigger datasets or complex tasks where parallel processing can speed things up.
    - **Removing Null Values (Narrow)**
    - **Casting the Types (Narrow)**
    - **Filter (Narrow)**
    - **Formatting Data (Narrow)**
    - **Aggregation (Wide)**
    - **Window Aggregations (Rank, Dense Rank...) (Wide)**
    - **Joins (left, right, cross join, self) (Wide)**
    - **Removing Duplicates (Narrow)**

# UI
![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/82d78b19-a70b-4da3-837f-2df8ca08b5c3)

# Let's learn Data Flow with a UseCase
- ABCD is a company who wants to analyze data for movies based on ratings provided to each movies
  
## 1.Data Ingestion
Here you can find the details [Data Ingestion](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/blob/main/Hands-On%20Labs/Copy%20github%20csv%20to%20ADLS.md)

## 2.Transformation
        1) Read the file from raw container and move it to archive folder. 
        2) In the Name as field, change 'Rotton' to 'Rotten'.
        3) Drop the Rating column.
        4) Only interested in movies made after 1910 and less than 2000.
        5) Only care about the first genre in genres column
        6) Interested in how a movie ranks within its year for its specific genre.
        7) For every genre and year, let's get the average Rotten Tomatoes rating, the highest and lowest rated movie and the number of movies that are in each group.
        8) Set the data Quality /Validation if validation fails send the data to error.
        9) If data is older than 1970 move to processed folder
        10) If data is greater than 1970 move to sqldb

## 3.DataFlow
Key points
- Dataflow must have a source and a sink.

1. Start with adding Source, here the source data is data we added to sink i.e., ADLS here
![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/4bc73adb-1e40-4f00-b956-3a4276c943dd)

   - **Schema drift:** Schema drift in Azure Data Factory refers to the ability of a data flow to handle changes in the source schema dynamically, such as the addition or removal of columns, without requiring manual  adjustments to the data flow.
   - **Infer Drifted Column Types**: In Azure Data Factory, inferring drifted column types automatically detects and assigns data types to new or modified columns in the source schema during runtime. This dynamic type inference allows the data flow to accurately process schema changes without manual updates. It enhances flexibility and ensures data integrity in evolving data environments.
   - You can't have both allow schema drift and validate schema, validate schema is like you have a fixed schema. 
   - **Early Binding (Validate Schema)**: This approach requires defining and validating the schema at design time. The schema must match the data source structure precisely, ensuring strict adherence to the expected schema before execution.
   - **Late Binding (Schema Drift)**: This approach allows the schema to be determined at runtime, enabling the data flow to dynamically adapt to changes in the source schema, such as new or missing columns, without requiring pre-defined schema validation.

2. Click on Map drifted to do modifications of the table columns, once you clicked on Map drifted a derived column activity comes into picture
![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/d3ee3e47-6eb0-4d14-bdb3-e8f74d27f54a)
![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/1baf65e8-dec2-4824-9f57-e177fc8744c6)

3. If you keenly observe you can change name and type of the column
![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/a992f676-f935-4768-8984-fd1b8a505644)
4. If you observed here, I have added filter before derived column as below dataflow
![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/9cc7ea3d-f4c4-4117-a2a4-7a367836ecdf)
   - It won't work because filter doesn't even know what are column names are, to check this you can do data preview
![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/469a3ca9-d52d-4c3e-bffb-ac5a7128c6bb)

- **Note:** Data flows won't work with self hosted IR, because data needs to be present in Cloud and for that AutoResolve IR is sufficient

5. Transformation: (5) Only care about the first genre in genres column
   - Ideas to solution
        1) Identify the position (X) of first pipe delimiter | (instr('Action|Drama|Comedy','|')) X=7
        2) Substring (genres,1,X-1)
        3) If X>0 then Substring(genres,1,X) else genres
![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/40fdb105-69ff-41ea-867e-0c90e940571d)
![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/62e59fac-fccc-4d36-9ce3-94adc59848d5)
![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/50614baa-5d8f-4255-ad0b-0a1c92c7159e)
![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/9f5bfa7c-b06a-40b9-b68f-62fd6982055c)



           
     
        

































