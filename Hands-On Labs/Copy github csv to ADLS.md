# Steps to copy single github file to ADLS Gen2
## Source
- **Linked Service:** A connection configuration that defines the connection information for an external service or data source, enabling interaction with external systems within a data integration or processing environment.
  ![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/230069e7-d50f-4bec-a07b-a80f7a1ae30d)

  > Note: If observed we just gave base URL as Linked Service is the connection string. We can use REST also but as the file is csv, during source dataset. It won't work. Hence we will be using HTTP. REST only supports JSON format.

- **Dataset:** A structured collection of data that represents a specific aspect of information, often organized in tables or files, used for analysis, reporting, or processing within a data management system. Basically it stores the format of the data
  ![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/7cdf410b-dc97-4ea4-b07f-3e3d73fa1644)

- **Creating Sink LS & Datasets:** A configuration defining the connection details for a destination system or service where data is written or loaded during data integration or processing pipelines. Organized collections of structured or semi-structured data that represent a specific entity or aspect of information, typically used for analysis, reporting, or processing within a data management system.
  ![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/dd2acaa3-be99-4278-94d9-ff1a9734a6bf)


