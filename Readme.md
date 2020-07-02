# Ecommerce Customer Analysis

## About Data

The data for this project can be downloaded for this [kaggle](https://www.kaggle.com/mkechinov/ecommerce-events-history-in-cosmetics-shop). This file contains behavior data for a one month (December 2019) from a large multi-category online store. 


Each row in the file represents an event. All events are related to products and users. There are different types of events.

*File structure*
- event_time: Time when event happened at (in UTC).

- event_type : can be:
view - a user viewed a product
cart - a user added a product to shopping cart
removefromcart - a user removed a product from shopping cart
purchase - a user purchased a product
Typical funnel: view => cart => purchase.

- product_id: ID of a product

- category_id: Product's category ID

- category_code

- Product's category taxonomy (code name) if it was possible to make it. Usually present for meaningful categories and skipped for different kinds of accessories.

- brand: Downcased string of brand name. Can be missed.

- price: Float price of a product. Present.

- user_id: Permanent user ID.

- user_session: Temporary user's session ID. Same for each user's session. Is changed every time user come back to online store from a long pause.

- Multiple purchases per session: A session can have multiple purchase events. It's ok, because it's a single order.


## Team members

- [Nibesh Khadka](https://github.com/nibukdk)
- [Ngoc Hoang(Hannah)](https://github.com/htmn88)
- [Bao Pham](https://www.kaggle.com/baoph153)


## Images and Analysis

### Dask and Visualization
![img](https://github.com/htmn88/ecommerce-analysis/blob/master/Imgs/dask_visualize.png)

Due to constant kernel crash only one file 2019-December.csv was used for analysis.

### Null Values Viz


![img](https://github.com/htmn88/ecommerce-analysis/blob/master/Imgs/missing.png)

There are three null columns: *category_code, user_session  and brand*. They all are nominal-qualitative variables. Due to lack of correlation measure for nominal variables we'll skip the correlation measurement steps.

## Customer Behaivour Portions

![img](https://github.com/htmn88/ecommerce-analysis/blob/master/Imgs/Customer_Behavior.png)


Observations:
- Customer purchased only 6% of items while viewd about 48% of items in online store. 
- The items added to cart were around 26% and removed are arpund 18%. 
- It is noticeable that almost 69% of the products added in cart was removed (3 979 679/5 768 333)

In ecommerce, the conversion rate represents the percentage of visitors that make a purchase. In this case it is 6.21% which is really high compare to the average conversion rate in general in ecommerce


## Visits Per Day

![img](https://github.com/htmn88/ecommerce-analysis/blob/master/Imgs/visits_everyday.png)

In figure,there is a significant decrease in the amount of visitors on as we approach the end of the month. This may be becuase of the holiday season which is typically from 24th of December. People may travel and celebrate instead of shopping online.

The week # 2 has most visitors, with Monday Dec 9 gaining 10.98k visitors, while last week sees the least customers with 31st December having 3.3k visitors which is the least amount.

Whats more theres always decrease in the customer number as the weekend approaches and rises again from Monday.


## Band Appearance Frequency

![img](https://github.com/htmn88/ecommerce-analysis/blob/master/Imgs/Brand.png)

93.9% of mentioned brands are refered under 10000 times while the brand with top apprearance is mentioned up to 80000 times, almost 8 times more than regular brand. As a result, we will do more analysis how 6.1% (15 brands) of all brands make a diffirent to be mentioned/considered more during purchase decision process. 


From above tabletable of sample dataset, total of items added to cart is about 53.6% of total item viewed, however, only 22.9% of added-to-cart items was purchased, equivalent to 12.8% of viewed items of those 15 most-popular brands.

Funel graph below will show propotion of each brands in this process.


## Top 15 Brands


![img](https://github.com/htmn88/ecommerce-analysis/blob/master/Imgs/top_brands.png)

As illustrusted in above graph, 15 most popular brand has performance rate (add-to-cart/view and purchase/view) better than average dataset performance (add-to-cart/view = 53.6% and purchase/view = 12.8%). 

Among the top 15 most-popular brands, some brands are not performing as good as average dataset with purchase/view rate lower than average are grattol (9.9%), estel (8.9%), kapous(7.3%), jessnail (5.4%) and concept (7.6%). 


## Hourly Traffic By Behaviour

![img](https://github.com/htmn88/ecommerce-analysis/blob/master/Imgs/hourly_traffic.png)

As expected late nights and early mornings are traffic free. The lunch rush hours starts from 9 until 14. While the peak hour is 19:00 hrs.
    

## Acitivity By Time Spent

![img](https://github.com/htmn88/ecommerce-analysis/blob/master/Imgs/avg_activity.png)

The graph suggests that, the behaviour of users gets more negative for product as time increases. As shown in graph user, removes the product more as the time progresses. However, as we go from left to right in graph it the gap in dropping item and purchasing in closing. It suggest, user is more likely to buy product if he/she spends less time browsing the product.


(*Note: Most of the visualization were done using plotly and cuffilinks.*)

