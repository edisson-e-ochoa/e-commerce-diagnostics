# Ecommerce diagnostics

Whiskique is an online pet supply store with presence in the USA. This project consists of analyzing the data they have gathered on their 2021 sales and answering three questions:

1. Which are the states with more sales and the most profitable product categories?
2. How can the current sales get increased?
3. Is there a way to reduce operating costs?

## Importing the data

The first step was to import the 5 given tables to Power BI, clean the data give it the correct format. After that I applied the necessary connections between tables.

(table schema)

## Measures

To ease the analysis, 11 new measures were created. These were especially useful in the study of the company's shipment costs. Here are some of them.

### Difference between shipping cost calculations up to a selected day

(Code 1)

### Shipping cost factor

(Code 2)

### Measure 3 (?)
(Code 3 (?))

## Dashboards

Finally, to get answers for the initial questions, I created three main dashboard pages:

- Executive Summary
- Shipping Metrics
- Market Basket Analysis

## Executive Summary

As its name says, this dashboard summarizes the most general facts, focusing on the sales distribution by product, category and state. It also allows drilling into any of these aspects.

(summary)

The main findings here are that California, Texas and Florida are the states that generate the most revenue, while electronics, grooming and cleaning supplies are the most profit-generating categories, with 44.28, 35.29, and 28.16 percent, respectively.

## Shipping Metrics

Whiskique doesn't have an automatic shipping cost capture for each transaction, so there is a great probability that these expenses are not as optimized as they can be.
This dashboard page was created to compare the shipping cost estimation currently used with a new one created by the logistics team with the intent of looking for a saving opportunity.

It shows the average quantity ordered by category and the total shipping cost for each state. However, its main focus is on shipping costs, analyzing both an overall view and each product individually, along with the potential savings if shipments include a certain unit's quantity; it is convenient to review each case in a deeper way.

(Shipping)

The charts reveal that dispatching 10 or more units per shipment gives the biggest savings to the company, being these of $118,190 in a year.

## Market Basket Analysis

A way to increase sales is understanding the customers purchasing patterns. For this case, the marketing team has proposed the idea of creating special price bundles for products commonly purchased together. This dashboard page was created to help with that task, it displays not only the best-selling products but also, by selecting a description, it will show the most often purchased products along with that one.

(Market)

This dashboard shows that the best-selling products in terms of revenue are Taste of the Wild Dog Food, Memory Foam Pet Beds, and the Dog and Puppy Pads.

Furthermore, it also reveals that the best pairs of products to include in an offer are

- Taste of the Wild Dog Food with Memory Foam Pet Beds.
- Memory Foam Pet Beds with Purina ONE Smartblend.
- Dog and Puppy Pads with Earth Rated Dog Poop Bags.

## Conclusion

(text)

1. California, Texas and Florida are the states that give more revenue to the company; the categories with the highest profit are electronics, grooming and cleaning supplies, with percentages of 44.28, 35.29, and 28.16, respectively.
2. By making shipments with 10 or more units, Whiskique can save $118,190 in operating costs.
3. Special offers on products that are commonly purchased together are an opportunity to increase the company's sales. The best pairs to try this strategy on are Taste of the Wild Dog Food with Memory Foam Pet Beds, Memory Foam Pet Beds with Purina ONE Smartblend, and Dog and Puppy Pads with Earth Rated Dog Poop Bags.
