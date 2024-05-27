Continuation of Data Flow Notes, previous notes can be found [here](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/blob/main/7.Azure%20Data%20Factory-%20Data%20Flows%201/Notes.md)
- Let's start with a question
# Instead of using Mapdrifted is there a way to get columns without import projection?
Ans: With byName you can dynamically use columns without Mapdrifted

![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/c47dc203-4c15-41a1-a599-0db3a388d392)

- To make this work dynamically, we need to ensure for the dataset, First row as header is enabled
![image](https://github.com/SandeepAnala1/AzureDataEnginnering_Notes/assets/163712602/2ad6e356-8527-448a-9579-e78f29fc743b)

# Transformations resumed
