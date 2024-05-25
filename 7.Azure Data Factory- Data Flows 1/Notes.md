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









