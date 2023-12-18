# Foresight_Pharmaceuticals_SalesAnalysis

[Visualization](https://public.tableau.com/views/ForesightPharmaceuticals_17020144024680/SalesAnalysis?:language=en-US&:display_count=n&:origin=viz_share_link)

## **Introduction**

Foresight Pharmaceuticals, a prominent pharmaceutical manufacturing company with a global footprint, operates in various markets divided across different regions worldwide. The management of the Germany and Poland markets falls under one of these regions. Rather than selling directly to customers, the company collaborates with a select group of distributors in all their regions.

Through agreements with each distributor, Foresight Pharmaceuticals shares its sales data to gain insights down to the retail level. The products are distributed through two main channels—hospital and pharmacy—and four sub-channels—government, institution, private, and retail.

The dataset encompasses sales figures, distributor names, sales channels, sub-channels, sales teams, and other relevant information for the years 2017 to 2020. Refer to the provided [dataset](https://foresightbi.com.ng/practice-data/3-datasets-for-your-portfolio/) for more details.

The **key business task** of this analysis is to determine the acceptability and gross performance of all products sold over a period of 4 years in order to drive smarter decisions to increase revenue.

## **Data Preparation**

Upon opening the data in Microsoft Excel, I found minimal cleaning was required. I then focused on preparing the dataset for loading into Tableau.

To organize the data, I created named ranges for each column using the respective column headers. Subsequently, I utilized the COUNTA function to determine the count of non-empty cells, and the UNIQUE function to identify distinct values in the text columns. This process was instrumental in refining the dataset and ensuring its readiness for seamless integration into Tableau.

![Screenshot 2023-11-30 at 8 06 22 PM 2](https://github.com/alib25/Foresight_Pharmaceuticals_SalesAnalysis/assets/149107691/41a939d5-c6f6-4012-9c6f-507b97023493)

Also created a new column named month_no, then used VLOOKUP function to return the number equivalent of the month column.

![Screenshot 2023-](https://github.com/alib25/Foresight_Pharmaceuticals_SalesAnalysis/assets/149107691/26152c44-0720-4bf9-a34c-8f8ea33a25cc)

I established a 'Day' column by populating rows with '1', representing the first day of each month. Subsequently, I utilized the DATE function to concatenate the year, month, and day into a unified 'date' column.

![Screenshot 2023-11](https://github.com/alib25/Foresight_Pharmaceuticals_SalesAnalysis/assets/149107691/88593137-6794-4eec-b5ff-ec57922e5d89)

![Screenshot 2023-1=](https://github.com/alib25/Foresight_Pharmaceuticals_SalesAnalysis/assets/149107691/aed84344-54c2-4400-8c0f-f64dc0371f27)

## **Data Transformation**

For simplicity, I uploaded only the worksheet containing the dataset, planning to create dimension tables within the Power Query Editor. I duplicated the dataset five times and renamed each table as per the previously outlined model: Orders, Customers, Products, Geography, Sales_Team, and Distributors. Subsequently, I tailored each table to align with the schema.

![Screenshot 2023-11-30 at 8 37 27 PM](https://github.com/alib25/Foresight_Pharmaceuticals_SalesAnalysis/assets/149107691/c3f04d05-17a8-4f6e-88b7-ebe17f46d8f2)

In the case of the fact table, namely the 'Orders' table, I excluded the 'Day,' 'Month,' 'Month_no,' and 'Year' columns. Then, I merged the 'City,' 'Latitude,' and 'Longitude' columns, naming the result 'City_Lat_Long.' This serves as the primary key for the Geography table and acts as a foreign key in the Orders table. These transformations culminated in the 'Orders' table containing nine columns.

I continued to transform the 5 dimension tables by repeating the process above - that is, removing unnecessary columns. In addition, I removed duplicates from these tables using the the primary key column for each table. This is because as dimension tables, they should only contain unique values. See all dimension tables below after transformation.

![1*3i4tyF0d9zvomm-RrNoy2Q](https://github.com/alib25/Foresight_Pharmaceuticals_SalesAnalysis/assets/149107691/b37e1570-6240-4c48-bc6a-834f41890c84)

![1*pZY5g_E_3zda3472fyYetQ](https://github.com/alib25/Foresight_Pharmaceuticals_SalesAnalysis/assets/149107691/64a24c96-0851-4a3e-acd8-35c89e20d08e)

![1*B_IOmQlY3erraWWlwd_ttg](https://github.com/alib25/Foresight_Pharmaceuticals_SalesAnalysis/assets/149107691/55e2b0e7-7b55-4dcb-8cd6-4b42569265d9)

![1*SMOOcrpWuoE-T_Fycqfk4Q](https://github.com/alib25/Foresight_Pharmaceuticals_SalesAnalysis/assets/149107691/d681fb9a-993c-4565-a0e1-4585292ef954)

![1*3CIeOzCkY82uoOjENpVtcw](https://github.com/alib25/Foresight_Pharmaceuticals_SalesAnalysis/assets/149107691/48e85c73-fa38-408c-b954-df12fa729ef4)

## **Data Analysis**
The next step is to analyze the dataset which is carried out in powerbi. I used different charts to show various data points from insights can be gotten.

## **Insights**
- Monthly sales reached its peak in the month of August 2019 grossing $480m, and lowest revenue was generated in the month of January 2019 with a total of $98m.
- Annual sales was highest in the year 2018, generating a total of $3.5bn after selling about 8.4million units of products, whereas year 2020 saw the least sales generating about $2.7bn having sold about 6.5million units.
- The revenue generated in Germany is highly significant compared to that generated in Poland. Germany generates a whooping 96% of the total revenue, while the remaining 6% is generated by Poland.
- In terms of the channel of distribution, pharmacy recorded the highest sales with 53.94% in total sales.
- There was a 7.13% increase in sales in sales in Germany via the hospital channel in 2018, but a 1.79% and -13.40% in sales in 2019 and 2020 respectively. The sales representation in 2020 would have been as a result of the COVID19 pandemic.

## **Recommendation**

- There is a huge disparity between the sales performance of both countries. This could be due to the fact that there aren't as much distributors in Poland as there are in Germany. Or could it be that, in Poland, people rarely have health issues that may require them to visit the hospitals or purchase pharmaceutical products?
- Foresight pharmaceuticals should increase investment in research and development which will lead to innovation of new pharmaceutical products which will be readily acceptable.
