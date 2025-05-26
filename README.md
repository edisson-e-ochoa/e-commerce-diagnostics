# Ecommerce Diagnostics

Whiskique is an online pet supply store with presence in the USA. This project consists of analyzing the data they have gathered on their 2021 sales and answering three questions:

1. Which are the states with more sales and the most profitable product categories?
2. How can the current sales get increased?
3. Is there a way to reduce operating costs?

## Importing the Data

The first step was to import the 5 given tables to Power BI and clean the data give it the correct format. After that I applied the necessary connections between tables.

![Table schema](/Visuals/Table_schema.png)

## Measures

To ease the analysis, 11 new measures were created. These were especially useful in the study of the company's shipment costs. Here are some of them.

### Running Difference between Shipping Cost Calculations

```
Difference running total = SUMX(FILTER(ALLSELECTED(Sales), Sales[Transaction Date] <= MAX(Sales[Transaction Date])), [Shipping (Difference)])
```

### Shipping Cost Factor

```
Blended Shipping Cost Factor = IF('What-if quantity'[What-if quantity Value] = 1, 1,
                                IF('What-if quantity'[What-if quantity Value] <= 2, 0.8,
                                IF('What-if quantity'[What-if quantity Value] <= 4, 0.6,
                                IF('What-if quantity'[What-if quantity Value] <= 7, 0.5, 
                                IF('What-if quantity'[What-if quantity Value] <= 9, 0.4, 0.3)))))
```

## Dashboards

Finally, to get answers for the initial questions, I created three main dashboard pages:

- Executive Summary
- Shipping Metrics
- Market Basket Analysis

## Executive Summary

As its name says, this dashboard summarizes the most general facts, focusing on the sales distribution by product, category and state. It also allows drilling into any of these aspects.

![Executive summary](/Visuals/Executive_summary.png)

The main findings here are that California, Texas and Florida are the states that generate the most revenue, while electronics, grooming and cleaning supplies are the most profit-generating categories, with 44.28, 35.29, and 28.16 percent, respectively.

## Shipping Metrics

Whiskique doesn't have an automatic shipping cost capture for each transaction, so there is a great chance that these expenses are not as optimized as they can be.

Originally, the estimated cost of shipping for every unit is 0.7 times the cost of the first one. The logistics team has recently found a new way to calculate these estimations:

| Units shipped (less than or equal) | Percentage of single-unit shipment cost per unit |
|---|---|
|1|100%|
|2|80%|
|4|60%|
|7|50%|
|9|40%|
|else|30%|

This dashboard page was created to compare both of these with the intent of looking for a saving opportunity.

It shows the average quantity ordered by category and the total shipping cost for each state. However, its main focus is on shipping costs, analyzing both an overall view and each product individually, along with the potential savings if shipments include a certain unit's quantity; it is convenient to review each case in a deeper way.

![Shipping metrics](/Visuals/Shipping_metrics.png)

The charts reveal that dispatching 10 or more units per shipment gives the biggest savings to the company, being these of $118,190 in a year.

## Market Basket Analysis

A way to increase sales is understanding the customers purchasing patterns. For this case, the marketing team has proposed the idea of creating special price bundles for products commonly purchased together. This dashboard page was created to help with that task, it displays not only the best-selling products but also, by selecting a description, it will show the most often purchased products along with that one.

![Market basket analysis](/Visuals/Market_basket_analysis.png)

This dashboard shows that the best-selling products in terms of revenue are Taste of the Wild Dog Food, Memory Foam Pet Beds, and the Dog and Puppy Pads.

Furthermore, it also reveals that the best pairs of products to include in an offer are

- Taste of the Wild Dog Food with Memory Foam Pet Beds.
- Memory Foam Pet Beds with Purina ONE Smartblend.
- Dog and Puppy Pads with Earth Rated Dog Poop Bags.

## Conclusion

The following is a summary of the insights found:

1. California, Texas and Florida are the states that give more revenue to the company; the categories with the highest profit are electronics, grooming and cleaning supplies, with percentages of 44.28, 35.29, and 28.16, respectively.
2. By making shipments with 10 or more units, Whiskique can save $118,190 in operating costs.
3. Special offers on products that are commonly purchased together are an opportunity to increase the company's sales. The best pairs to try this strategy on are Taste of the Wild Dog Food with Memory Foam Pet Beds, Memory Foam Pet Beds with Purina ONE Smartblend, and Dog and Puppy Pads with Earth Rated Dog Poop Bags.
