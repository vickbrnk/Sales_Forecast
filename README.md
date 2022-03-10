# Sales_Forecast
Repository containing all steps of the preparation, cleaning, transforming, and pre-processing in R of a historical Rossman dataset (1,000,000> observations) consisting of 1,115 stores. The aim was to predict six weeks of daily sales over the 01/08/2015 - 17/09/2015 period with a linear regression model. Since sales are influenced by a number of factors, backwards step selection was employed to identify the variables which affect sales significantly.



This report prepares and analyses a historical sales dataset of 1,115 stores of the large European drug store chain Rossman in Germany. The aim is to predict six weeks of daily sales over the 01/08/2015 - 17/09/2015 period with a linear regression model. Since sales are influenced by a number of factors, backwards step selection was employed to identify the variables which affect sales significantly.

1.1 Available Data
Three datasets were provided for the prediction of sales. These included:

1. Stores.csv
Dataset consisting of 1,115 observations of 10 variables. Contains detailed infor- mation about the Rossman stores such as their distance to the nearest competi- tion, when these opened, and promotions. The given variables and descriptions of these can be found in Table 1.2.

2. Train.csv
Dataset consisting of 1,017,209 observations of 9 variables. Contains information about the sales of the 1,115 stores between 01/01/2013 and 31/07/2015. The given variables and descriptions of these can be found in Table 1.1.

3. Test.csv
Dataset consisting of 41,088 observations of 9 variables. Consists of the same variables as the train dataset, but misses Sales and Customers values. Contains information about the stores between 01/08/2015 and 17/09/2015. The sales of this dataset will be predicted with the generated model. For details and descriptions of the variables, see Table 1.1.
 
Table 1.1
Variables:
1. Store - The anonymised store number
2. DayOfWeek - The day of the week: 1 = Monday, 2 = Tuesday, 3 = Wednesday, 4 = Thursday, 5 = Friday, 6 = Saturday, 7 = Sunday
3. Date - The given date in the dd/mm/yyyy format
4. Sales - The turnover on a given day
5. Customers - The number of customers on a given day
6. Open - An indicator for whether the store was open on that day with 0 = Closed, 1 = Open
7. Promo - Indicates whether a store is running a store-specific promo on that day
8. StateHoliday - Indicates a state holiday. Normally all stores, with few exceptions, are closed on state holidays. Note that all schools are closed on public      holidays and weekends. a = public holiday, b = Easter holiday, c = Christmas, 0 = None
9. SchoolHoliday - Indicates if the store on the day was affected by the closure of public schools



Table 1.2
1. Store - The anonymised store number
2. StoreType - 4 different store models: a, b, c, d
3. Assortment - An assortment level: a = basic, b = extra, c = extended
4. CompetitionDistance - Distance in meters to the nearest competitor store
5. CompetitionOpenSinceMonth - The approximate month of the time when the nearest competitor was opened
6. CompetitionOpenSinceYear - The approximate year of the time when the nearest competitor was opened
7. Promo2 - A continuing and consecutive promotion, e.g., a coupon based mailing campaign, for some stores: 0 = store is not participating, 1 = store
is participating
8. Promo2SinceWeek - The calendar week when the store started participating in Promo2
9. Promo2SinceYear - the year when the store started participating in Promo2
10. PromoInterval - The consecutive intervals in which Promo2 is re-started, naming the months the promotion is started anew. e.g., ”Feb,May,Aug,Nov” means each round of the coupon based mail- ing campaign starts in February, May, August, November of any given year for that store, as the coupons, mostly for a discount on certain products are usually valid for three months, and a new round of mail needs to be sent to customers just before those coupons have ex- pired
