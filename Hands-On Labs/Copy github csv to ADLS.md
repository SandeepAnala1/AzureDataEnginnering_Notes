# Steps to copy single github file to ADLS Gen2
## Source
- **Linked Service:** A connection configuration that defines the connection information for an external service or data source, enabling interaction with external systems within a data integration or processing environment.
  ![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/230069e7-d50f-4bec-a07b-a80f7a1ae30d)

  > Note: If observed we just gave base URL as Linked Service is the connection string. We can use REST also but as the file is csv, during source dataset. It won't work. Hence we will be using HTTP. REST only supports JSON format.

- **Dataset:** A structured collection of data that represents a specific aspect of information, often organized in tables or files, used for analysis, reporting, or processing within a data management system. Basically it stores the format of the data
  ![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/7cdf410b-dc97-4ea4-b07f-3e3d73fa1644)

## Sink
- **Creating Sink LS & Datasets:** A configuration defining the connection details for a destination system or service where data is written or loaded during data integration or processing pipelines. Organized collections of structured or semi-structured data that represent a specific entity or aspect of information, typically used for analysis, reporting, or processing within a data management system.
  ![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/dd2acaa3-be99-4278-94d9-ff1a9734a6bf)

## Pipeline
- A pipeline in Azure Data Factory is a logical grouping of activities that together perform a task, orchestrating data movement and transformation workflows.
- Pipelines can include various activities such as copying data, executing stored procedures, and running data flows, enabling the automation and scheduling of complex data processes.
  ![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/640f0606-8ad8-427b-8a3e-ca8828dbfc37)
  ![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/4b8b00b9-7380-4c77-935d-2d2d222eaf93)
- Debug the pipeline
  ![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/48402d68-1a35-4802-912a-a0bf03bcdf20)

## Find the csv file ingested from Github to ADLS
![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/c2c93832-97ef-42b5-8711-c3b378aae2d8)
