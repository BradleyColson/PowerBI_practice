# PowerBI_practice

They key thing to understand is that this is practice.  With kaggle data sets, or data I found on the internet, there isn't a business problem to solve.  

The point here is to show I know how to use the tools.


Bike Data Project

Stakeholder request:

Real World code along example.

Hourly revenue analysis, Profit and revenue trends, Seasonal revenue, Rider demographics

SQL query:

with cte as (
select *
from dbo.bike_share_yr_0
union
select *
from dbo.bike_share_yr_1)

select 
	dteday, season, a.yr,weekday, hr, rider_type, riders, price, COGS, 
	riders * price as revenue,
	riders * price - COGS as profit
from cte a
left join cost_table b
	on a.yr = b.yr

Please provide a recommendation on price increase.

![image](https://github.com/BradleyColson/PowerBI_practice/assets/132014177/c2ece381-9329-48b5-917a-0918fe25a94a)

Analysis:

![image](https://github.com/BradleyColson/PowerBI_practice/assets/132014177/48e2b88c-e4b9-48a9-b9cf-7a5e71862c58)


Example recommendation:

Conservative Increase: Considering the substantial increase last year, a more conservative increase might be safer to avoid hitting a price ceiling where demand starts to drop.  An increase in the range of 10-15% could test the market response without risking a significant customer loss.

Price setting: 


If the price in 2022 was $4.99, a 10% increase would make the new price $5.49
A 15% increase would set the price at $5.47

Segmented Pricing Strategy: Consider different pricing for casual versus registered users as they might have different price sensitivies.
Monitor and Adjust: Implement the new prices but be ready to adjust based on immediate customer feedback and sales data.

********************

Stakeholder requirement.

Total number of calls: We need to track and display the total number of calls received by our call center reverse specified period.

Total collaboration in hours: It is crucial to understand the total amount of time our call center staff spends on calls in hours, which can help us in resource allocation and capacity planning.

Total alteration in minutes: similar to the total call duration in hours, this KPI provides the total call time but in minutes, offering a more granular view of call directions.

Average call duration in minutes: to assess the efficiency of our agents, we need to calculate and display the average call duration in minutes. This metric can help identify trends and call handling.

Response time percentage. response time is a critical factor in customer service. This KPI should display the percentage of calls answered within a predefined time frame, helping us gauge our ability to provide good service.


![CallerCenter](https://github.com/BradleyColson/PowerBI_practice/assets/132014177/49beb91a-bd38-4bbd-8ee8-79484f1a10f4)



