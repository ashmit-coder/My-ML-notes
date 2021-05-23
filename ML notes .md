# Notes from documentation
1.  To see the first N rows of a DataFrame, use the head() method with the required number of rows
Interested in the last N rows instead? pandas also provides a tail() method. For example, titanic.tail(10) will return the last 10 rows of the DataFrame.
2. A check on how pandas interpreted each of the column data types can be done by requesting the pandas dtypes attribute:
3. Whereas read_* functions are used to read data to pandas, the to_* methods are used to store data. The to_excel() method stores the data as an excel file. In the example here, the sheet_name is named passengers instead of the default Sheet1. By setting index=False the row index labels are not saved in the spreadsheet
__imp use sheet.save() at the end__
4. .info() will give the summary of the entire file 
# Sorting out rows and coloumns
5. To select a single column, use square brackets [] with the column name of the column of interest.
6. Each column in a DataFrame is a Series. As a single column is selected, the returned object is a pandas Series. We can verify this by checking the type of the output:
7. DataFrame.shape is an attribute (remember tutorial on reading and writing, do not use parentheses for attributes) of a pandas Series and DataFrame containing the number of rows and columns: (nrows, ncolumns). A pandas Series is 1-dimensional and only the number of rows is returned.
8. To select multiple columns, use a list of column names within the selection brackets [].
9. The inner square brackets define a Python list with column names, whereas the outer brackets are used to select the data from a pandas DataFrame as seen in the previous example.
10. The selection returned a DataFrame with 891 rows and 2 columns. Remember, a DataFrame is 2-dimensional with both a row and column dimension.
11. The output of the conditional expression (>, but also ==, !=, <, <=,… would work) is actually a pandas Series of boolean values (either True or False) with the same number of rows as the original DataFrame. Such a Series of boolean values can be used to filter the DataFrame by putting it in between the selection brackets []. Only rows for which the value is True will be selected.
12. Similar to the conditional expression, the isin() conditional function returns a True for each row the values are in the provided list. To filter the rows based on such a function, use the conditional function inside the selection brackets []. In this case, the condition inside the selection brackets titanic["Pclass"].isin([2, 3]) checks for which rows the Pclass column is either 2 or 3.
__this will help us use a list rather than a condn which makes easy to use certain values__
13.  The notna() conditional function returns a True for each row the values are not an Null value. As such, this can be combined with the selection brackets [] to filter the data table.
14. In this case, a subset of both rows and columns is made in one go and just using selection brackets [] is not sufficient anymore. The loc/iloc operators are required in front of the selection brackets []. When using loc/iloc, the part before the comma is the rows you want, and the part after the comma is the columns you want to select.
15. When using the column names, row labels or a condition expression, use the loc operator in front of the selection brackets []. For both the part before and after the comma, you can use a single label, a list of labels, a slice of labels, a conditional expression or a colon. Using a colon specifies you want to select all rows or columns.
16. Again, a subset of both rows and columns is made in one go and just using selection brackets [] is not sufficient anymore. When specifically interested in certain rows and/or columns based on their position in the table, use the iloc operator in front of the selection brackets [].
17. fig.savefig()  
18. To create a new column, use the [] brackets with the new column name at the left side of the assignment.
19. The calculation is again element-wise, so the / is applied for the values in each row. Also other mathematical operators (+, -, *, /) or logical operators (<, >, =,…) work element wise. The latter was already used in the subset data tutorial to filter rows of a table using a conditional expression.
20. The rename() function can be used for both row labels and column labels. Provide a dictionary with the keys the current names and the values the new names to update the corresponding names. The mapping should not be restricted to fixed names only, but can be a mapping function as well. For example, converting the column names to lowercase letters can be done using a function as well:
21. .mean() will give mean of a aparticular series
22. .meadian() will give the median
23. The aggregating statistic can be calculated for multiple columns at the same time. Remember the describe function from first tutorial tutorial?
24. Instead of the predefined statistics, specific combinations of aggregating statistics for given columns can be defined using the DataFrame.agg() method:
25. As our interest is the average age for each gender, a subselection on these two columns is made first: titanic[["Sex", "Age"]]. Next, the groupby() method is applied on the Sex column to make a group per category. The average age for each gender is calculated and returned.
26.  layout attribute of plot will  result in layout of different graphs as(rows, coloumns)
# iris project and video notes 
1. we split the data set into 80 and 20  where the 20 precent is used to test the model 
2. suppervised learning has several methods, regreesion model has two types __simple__ and __multiple__ both differe on the number of input variables
3. Once you train the model, it is desirable that the model should be persist for future use so that we do not need to retrain it again and again. It can be done with the help of dump and load features of joblib package.
4. sklearn does not work with datafrmames it works wtih array so after exploring the data with pandas we need to use sklearn with numpy
5. sklear meterics hleps us to find the score or performance of the the model
6. 