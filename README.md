# PowerBI_practice

They key thing to understand is that this is practice.  With kaggle data sets, or data I found on the internet, there isn't a business problem to solve.  

The point here is to show I know how to use the tools.


I'm very fond of female Kpop groups, and in recent years they've gone from relative obscurity to worldwide phenomenons. I used search data to create a table in sql and then imported it into PowerBI.  Since it was data I input, there was no cleaning involved.

Insights:

From this image, you can see that the surge of Kpop female groups started at around 2010 and has grown exponentially since.

I was suprised to see that each Record Label or Studio only had a few highly successful groups.

Lastly it surprised me only half the groups that started are still permorming. Popularity appears to be fleeting.

![Kpop_Girl_Group_Debut](https://github.com/BradleyColson/PowerBI_practice/assets/132014177/a7d5bdf6-87eb-494d-b85f-04207494dcbb)

****

As I study and practice more, I've learned some better technique.

I wanted to improve the debut year chart, I found it ugly. I also realized I'd left duplicates in the csv file.

With some help from google gemini I wrote a query to clean up the data.

DELETE FROM practice.kpop_DEBUT
WHERE artist IN (
  SELECT artist
  FROM (
    SELECT artist, ROW_NUMBER() OVER (PARTITION BY artist) AS row_num
    FROM practice.kpop_debut
  ) AS ranked_data
  WHERE row_num > 1
);

They again with a little AI help I improved upon the debut year count.

SELECT YEAR(debut) AS year, COUNT(*) AS debut_count
FROM practice.kpop_girl_group
GROUP BY YEAR(debut)
order by year desc

The result being this much better looking dashboard.

![KPop_Debut_PowerBI](https://github.com/BradleyColson/PowerBI_practice/assets/132014177/1f0c94dd-3bf4-48d5-9010-59c0b04083ef)

