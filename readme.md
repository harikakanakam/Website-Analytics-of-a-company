### Website Analytics of different websites of a company

#### Dataset Description:
The dataset captures daily website analytics for multiple sites of a company. It provides
valuable insights on various aspects including customer demographics, device preferences,
visitation patterns, sales metrics, and user engagement. Below are the columns of the dataset:
1. day: The calendar day when the data was recorded.
2. site: The company site visited by users.
3. new_customer: A binary variable where 0 represents returning customers, 1 represents new
customers, and null indicates neither status.
4. platform: The type of device used by a website visitor.
5. visits: The number of distinct website visits in which one session may have multiple visits.
6. distinct_sessions: The number of distinct website visitors. Again, multiple visits may occur
within a single session.
7. orders: The number of website orders made by visitors.
8. gross_sales: The total gross sales generated from website orders.
9. bounces: The number of visits in which a user viewed only one page on the website without
further interaction.
10. add_to_cart: The number of visits in which users added a product to their shopping cart.
11. product_page_views: The number of product pages viewed by users.
12. search_page_views: The number of search pages viewed by users. 

Below three columns are created from the existing columns:
1. conversion_rate: Rate of number of visits that led to order
2. bounce_rate: Rate of number of visits that user viewed only one page
3. add_to_cart_rate: Rate of number of visits that user added a product to cart.

The dataset allows for the analysis of visitor demographics (new vs. returning customers),
device preferences (platform), engagement (visits and distinct sessions), conversion rates
(orders and gross sales), and user behavior (bounces, add-to-cart, product page views, and
search page views). Analyzing this data can provide valuable insights into user behavior,
website performance, and potential areas for business improvement. 

#### Identifying significant features:
From the dataset description, it can be assumed that the features new_customer, visits,
bounces, add_to_cart, orders and gross sales might be significant features. To strengthen
this assumption, correlation graph has been plotted to know the relationship between the
columns. Below is the correlation plot for the features visits, new_customer, orders, distinct
sessions, gross_sales, product_page_views, search_page_views and Bounces

<img width="1088" alt="Correlation" src="https://github.com/harikakanakam/Website-Analytics-of-a-company/assets/113376852/6c72d5a6-9184-427a-b29a-7d3b4219eb1c">


The Observations from the scatterplot are as below:
- The column ‘visits’ is correlated with maximum number of columns. But it is highly
correlated with the columns ‘distinct_sessions’, ‘search_page_views’ and ‘bounces’
which is obvious that all the other columns are significantly dependent on the visits. This
infers that increase in number of visits, changes the logistics of other columns.
- Orders is highly correlated with ‘gross_sales’ which is again obvious that increase in
number of orders increases the gross sales of any platform.
- With distinct sessions, it can be observed that ‘search_page_views’ and ‘Bounces’ are
highly correlated indicating that there are more users who only visit one page with
distinct sessions.
- Though ‘search_page_views’ and ‘product_page_views’ are not completely correlant, it
looks like increase in one value, increases the count on other value.

The below dashboard shows the analytics of the significant features of each platform based on
sites. It can be observed that users are using windows platform more than any other platforms
and the site Acme is clearly the leading site.

<img width="1085" alt="Visits Vs Distinct Sessions Vs Bounces Sales" src="https://github.com/harikakanakam/Website-Analytics-of-a-company/assets/113376852/9718d955-1ad3-4fd2-871a-30a23fbdc5be">


Finally, it can be strongly inferred that there is not only one or two significant features of the
provided dataset, but there are a group of 4-5 columns making significant features of the
provided dataset. These columns likely play a key role in understanding and analyzing the data
for business insights and decision-making.

#### Discover underperforming demographic segments:

<img width="1087" alt="Platform's Average Rate" src="https://github.com/harikakanakam/Website-Analytics-of-a-company/assets/113376852/8cf8597d-72af-4ed8-9a20-e95a398c5c32">


<img width="1093" alt="Site's Average Rate" src="https://github.com/harikakanakam/Website-Analytics-of-a-company/assets/113376852/7572a428-7301-4d95-a3cc-8c3d4608387b">


The above 2 graphs help us to identify the underperforming demographic segments. To do this,
I have created calculated fields for percentage rate for all the additional columns that are
created in the initial stage. The percentages are calculated to have all the 3 columns on the
same scale. Then these three features are plotted as line graph based on platform and site. The
area graph is plotted based on the customer(returning or new customer) The inferences made
from the above 2 graphs are:
- From the first graph, it is clear that the bounce rate is more for the platforms
SymbianOS and blackberry for which the add_to_cart rate and conversion rates are
lower. It can be observed that, for the platforms that has lower bounce rate has the
higher add_to_cart rate and conversion rates.
- The same pattern can be found in the second graph as well where the bounce rate is
inversely proportional to the add_to_cart and conversion rates. Tabular site has the
lowest bounce rate where the add_to_cart rate is more.
- The platform ‘Acme’ which is used by most of the users, has similar values for all these 3
percentage rates.


#### Analyze the past and current trends:

<img width="996" alt="Dashboard 2" src="https://github.com/harikakanakam/Website-Analytics-of-a-company/assets/113376852/3ed16d62-ca10-4e1f-962c-4bdc47b8bafa">


From the day data it is clear that the data is from the year 2013 and there is no data for the
months of March, April and May. Above is the dashboard of three plots including gross sales,
average rates, and new customer analytics over time. The below observations can be made
from the dashboard:
- Though there are fluctuations for gross sales in the initial months, there is continuous
increase from the month of August. Finally, the month December has the highest gross
sales with $30,408,835.
- There isn’t much difference in the percentage change in the conversion rate, bounce
rate and add to cart rate over months based on customers (new or returning).
- But there is a change in total gross sales, total number of orders and visits over months
based on the type of customer.
- It is clear that visits, orders and gross sales of returning customers is higher than the old
customers in all the quarters.

#### Potential growth areas and strategies:
Based on the analysis, few changes/strategies can be implemented to see growth in the
sales and performance.
- It is clear that bounce rate for SymbianOS is higher resulting in zero add to cart rate and
zero conversion rate. So, the problem with the platform SymbianOS should be evaluated
in order to increase the sales. Same goes with the platforms Blackberry and
WindowsPhone.
- Other than the site Acme, all other sites are not performing well enough. One of the
reasons for this might be the user experience on the site is not so good for other sites.
So, other site’s UX design must be updated in order to give user a good experience.
- Also, it is observed that new customers are not ordering much compare with the
returning customers. So, there some deals can be given to the new customers to make
them active on the websites.
- It is important to note that number of visits of user is clearly affecting all other features.
So, it is important to make sure that user visits more often. One of the possibilities of
doing this can be sending relevant notifications to the user to make sure the user visits
the website irrespective of the platform.
