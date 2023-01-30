# First Project


**First hypotesis**

![tiburon1](imagens/tiburon1.jpeg)

### **I intend to demonstrate that, of the three countries with the most attacks (the United States, Australia, and South Africa), the most fatal attacks are in the United States by the Bull shark three species only excluding, the White shark, Tiger shark, and Bull shark**.



I start cleaning and filtering:
I deleted the NaN's columns and rows, I get the info from the DataFrame with the intentions of analise the information and try to get some questions to plant the hypothesis.

I reate a regular expression pattern that matches white shark, tiger shark or bull shark and Extract the matched strings from the specified column and put them in a new column with "Species cleaned"

I filter the data to only include attacks that occurred in the USA, Australia, or South Africa. 
Creating a Boolean mask based on the 'Country' column and using it to filter the Data

I grouped the filtered data by country and species. 
I used the size() function to get the number of attacks for each group.

then we cloud use the pivot_table() function to reshape the data and make it easier to visualize.
I filtered only by fatal attacks.

I grouped the fatal attacks by country and species and use the size() function to get the number of fatal attacks for each group

![Table](imagens/Pivot_table_1.png)

You can see the number of fatal attacks for each species in each country, and we can use the pivot_table to compare the number of fatal attacks of the Bull shark in the USA with the number of fatal attacks of the White and Tiger shark.
![Graphic](imagens/graphic1.png)

Second hypotesis
I'll use the database "attacks" to demonstrate that American women experience the most non-lethal shark attacks.