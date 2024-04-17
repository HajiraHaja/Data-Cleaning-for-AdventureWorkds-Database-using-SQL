Project overview
This project aims to conduct thorough data exploration and supplement information by reviewing insights from the company’s website, newspaper and economic websites from Brazil to gain a comprehensive understanding of the current market landscape surrounding the company. The fundamental analysis revealed that Olist operates within a diverse yet competitive market environment which is the e-commerce. While the company has experienced notable successes, some potential challenges were identified, including stagnation in sales for specific products. 

In this project, with a use of Microsoft Power BI tool, a presented dashboards that summarizes the company in terms of the sales, customers, products and products performance. As well as descriptive, clustering analysis and forecasting analysis.

Objectives
1.	What is the total cost, sales, profit?
2.	Total order by city, relationship between orders and reviews.
3.	4.	What is the number of customers by state and sentimental analysis from reviews? 
5.	What are the top and bottom 10 products by categories?
6.	What are the total sellers, most profitable seller and where they are located?

Main Approach
The data schema was viewed to split data into key categories and take note of key points and potential links. After this, possible questions/statements of analysis for each category were formulated. The formula expression DAX was formed and new columns to find better insights from the variables. 
For example:a new column was named regions to find the accurate region of the state and visualise in a better way the business behaviour across the city. 

Region =
SWITCH (
    'olist_customers_dataset'[customer_state],
    "AL", "East",
    "AM", "North",
    "AP", "North",
    "BA", "East",
    "CE", "East",
    "DF", "West",
    "ES", "East",
    "GO", "West",
    "MA", "North",
    "MG", "Southeast",
    "MS", "West",
    "MT", "West",
    "PA", "North",
    "PB", "East",
    "PE", "East",
    "PI", "Northeast",
    "PR", "South",
    "RJ", "Southeast",
    "RN", "East",
    "RO", "North",
    "RR", "North",
    "RS", "South",
    "SC", "South",
    "SE", "East",
    "SP", "Southeast",
    "TO", "North",
    "Unknown"
)

A column to describe the name of each city was created.

Full State Name =
SWITCH (
    'olist_customers_dataset'[customer_state],
    "AC", "Acre",
    "AL", "Alagoas",
    "AM", "Amazonas",
    "AP", "Amapá",
    "BA", "Bahia",
    "CE", "Ceará",
    "DF", "Distrito Federal",
    "ES", "Espírito Santo",
    "GO", "Goiás",
    "MA", "Maranhão",
    "MG", "Minas Gerais",
    "MS", "Mato Grosso do Sul",
    "MT", "Mato Grosso",
    "PA", "Pará",
    "PB", "Paraíba",
    "PE", "Pernambuco",
    "PI", "Piauí",
    "PR", "Paraná",
    "RJ", "Rio de Janeiro",
    "RN", "Rio Grande do Norte",
    "RO", "Rondônia",
    "RR", "Roraima",
    "RS", "Rio Grande do Sul",
    "SC", "Santa Catarina",
    "SE", "Sergipe",
    "SP", "São Paulo",
    "TO", "Tocantins",
    "Unknown"
)
And, a named Olist_review_dataset [Sentiment_review_category] was created, Where we created 3 categories under [review_score], Positive (5,4), Negative (1), Neutral (2,3) reviews. 

Additionally, some new measures were created to find the accumulate profit of the organization.

•	Total Cost = SUMX ('olist_order_items_dataset', 'olist_order_items_dataset'[price] + 'olist_order_items_dataset'[freight_value])

•	Total_Revenue = SUM('olist_order_payments_dataset'[payment_value])

•	Profit = [Total_Revenue] - [Total Cost]

The creation of new columns and measures was driven by the goal of generating meaningful indicators and relationships, which could be analysed to extract insights regarding products, orders, sellers, and sales.

Then, started visualizing our possible questions/statements of analysis to find the best-presented visuals to showcase the findings. The file was uploaded on power Bi service to create dashbaord. Key visuals were pinned across all areas to provide a quick snapshot of the fidnings .


Analysis using Power Bi 

Here is the overall Dashboard:
![Olist store dashoard](https://github.com/HajiraHaja/Olist-Store-Analysis---PowerBi/assets/166501265/35968517-78ba-45ed-b9a4-e0653da0449f)
The individua pages of the report are as follows:
Overview
![Overview](https://github.com/HajiraHaja/Olist-Store-Analysis---PowerBi/assets/166501265/1446401d-a5e5-4813-a7a5-2eb50026434b)
Sales 
![Sales](https://github.com/HajiraHaja/Olist-Store-Analysis---PowerBi/assets/166501265/495fa2e6-8faa-4c6b-b5d7-f612f9996c89)
Products
![Products](https://github.com/HajiraHaja/Olist-Store-Analysis---PowerBi/assets/166501265/62f225fe-61ed-47ac-8af5-ab5028b86602)
Reviews
![Reviews](https://github.com/HajiraHaja/Olist-Store-Analysis---PowerBi/assets/166501265/d4163cf2-d560-495e-a542-9940f3f291f1)
Shipping 
![Shipping](https://github.com/HajiraHaja/Olist-Store-Analysis---PowerBi/assets/166501265/9f41b94e-688d-4b25-b5b8-98c3f9c3c148)
Seller 
![Shipping](https://github.com/HajiraHaja/Olist-Store-Analysis---PowerBi/assets/166501265/86b33a98-a9af-4569-a280-659f83575f4a)
