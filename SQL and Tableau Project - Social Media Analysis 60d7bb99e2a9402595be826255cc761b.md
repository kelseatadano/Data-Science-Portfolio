# SQL and Tableau Project - Social Media Analysis

### Download instagram dataset from kaggle + save it to local computer

[Top Instagram Accounts Data (Cleaned)](https://www.kaggle.com/datasets/faisaljanjua0555/top-200-most-followed-instagram-accounts-2023/data)

### Import the dataset in mySQL workbench

First, import the downloaded csv data from the kaggle dataset. If the dataset was not in csv format, pre-processing data in csv format, would be necessary before querying the data. 

Query the data, 

```sql
SELECT * FROM social_media_analysis;

// social_media_analysis is the name of the table the kaggle dataset was imported into //  
```

### Category Analysis

Get the different categories of the top 200 social media influencers from the dataset. 

Conveniently, the kaggle instagram dataset, categorized each of the 200 top instagram influencers into a specific influencer category, and grouped those categories into the ‘Category’ column.

<aside>
💡 **Question:**  what influencer categories are most common amongst the most popular influencers?

</aside>

After querying the data, 

```sql
SHOW COLUMNS FROM social_media_analysis ;
```

- show columns, displays the columns present in the dataset

Next, group the influencer categories by count in descending order

```sql
SELECT Category, COUNT(*) as count 
FROM social_media_analysis 
GROUP BY Category 
ORDER BY count DESC; 
```

This query results in the following result in mySQL workbench

![Screenshot 2024-03-25 at 6.23.02 PM.png](SQL%20and%20Tableau%20Project%20-%20Social%20Media%20Analysis%2060d7bb99e2a9402595be826255cc761b/Screenshot_2024-03-25_at_6.23.02_PM.png)

From here, 

Export the category and corresponding category count as a CSV file, and save it into Tableau for visualization. 

### Visualize the results using Tableau

[https://public.tableau.com/views/CategoryPieChart_17114137449220/Sheet1?:language=en-US&publish=yes&:sid=&:display_count=n&:origin=viz_share_link](https://public.tableau.com/views/CategoryPieChart_17114137449220/Sheet1?:language=en-US&publish=yes&:sid=&:display_count=n&:origin=viz_share_link)

I decided on a pie chart for this visualization, as it is a intuitive representation of proportions and percentages. Additionally, the simplicity of the chart and legend, allows viewers to visually simplify the results of the chart by comparing relative sizes of the pie slices. 

### Conclusion

In conclusion, this pie chart visualization  highlights the entertainment category's substantial presence among Instagram's top two-hundred influencers, claiming roughly 65% of the platform's most-followed accounts. This prominence underscores the central role of entertainment content in attracting and engaging Instagram's user base. The health/sports/fitness category, holding about 20%, stands out as the second most represented category, signaling a strong audience interest in wellness and active living. These insights demonstrate clear trends within Instagram's influencer ecosystem and can guide strategic decisions in social media marketing and content creation.