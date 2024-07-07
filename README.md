# FUNCTIONAL AND TECHNICAL WORKING OF REPORT  

- # FUNCTIONAL WORKING :
The given dashboard tells you about sales analysis of awesome chocolate factory 
here you can easily access the infoormation of 

1. Total sales made by the company or the the total sales made according to specific product
2. How much boxes been sold of different products
3. Here we can easily get to know about the shipment count
4. There is also calculation of LBS(LOW BOX SHIPMENT) and LBS%

### GRAPHS USED FOR :
1. To get to know about the sales trend of different months
2. To get to know about sales of produts according to geographical location 

### TABLE USED FOR :
--> Displaying the top 10 salesman of oour company according to total boxes of products sold by them , total sales they made and what is status of lbs%

##   IMPORTANT DASHBOARD FEATURE :
1. The given dashboard is flexible as it can show sales analysis of different products used in company.
2. The queries are parameterized and show the parameter values on the Power BI report


 
- # TECHNICAL WORKING :

1. ## USE OF MYSQL
   --> [DOWNLOAD FROM HERE](https://www.mysql.com/)

   - After complating the download stage u need some data to be used in mysql, so i have uploaded database dump on this repository.
  
   - Import the given data in mysql workbench by following the steps in  image below:
  

  (![SNAG-2243](https://github.com/hardikty/sales-analysis-pt2/assets/174869730/4ca0a52a-30a0-47dd-83e0-215ede45e8ea)

  - At the end of these steps, your MySQL should have the awesome chocolates database. Congratulations
    You can see this from “Schemas” tab on the workbench

  - So the given data is been succesfully imported on your local host now its time to visualize the data in power bi and do some analysis by executing queries


2. ## USE OF MICROSOFT POWER BI
   --> [DOWNLOAD FROM HERE](https://www.microsoft.com/en-us/power-platform/products/power-bi/downloads)
   - After succesfully downloading power bi go to GET DATA to import the dataset ur mysql database contains , follow the images given below :
  
      (![getdata](https://github.com/hardikty/sales-analysis-pt2/assets/174869730/b2f6cfaa-7b91-4b3a-a438-3ceecd523732)

      (![host](https://github.com/hardikty/sales-analysis-pt2/assets/174869730/58d24a3f-bac8-4424-a976-32eda510fdb2)
     fill the server and database info.

     (![last](https://github.com/hardikty/sales-analysis-pt2/assets/174869730/7538670e-df93-40da-a2fd-df2c2a9c8bd2)
     click on connect

   - Finally the schemas in your mysql will be fetched in power bi app and will be shown lke this

      (![queries](https://github.com/hardikty/sales-analysis-pt2/assets/174869730/de8f5cf1-7011-43c6-ac5f-c61393b208b2)

   - Now its time to excute queries in order to get
     1. Total sales
     2. Total boxes
     3. Low box shipment
     4. LBS%

### DATA ANALYSIS

include some codes worked with :

```sql
Total Sales = SUM(sales[Amount]);
```

```sql
Total Boxes = SUM(sales[Boxes]);
```

```sql
low box shipments = CALCULATE([Shipment Count], sales[Boxes]<50);
```

```sql
LBS% = DIVIDE([low box shipments],[Shipment Count]);
```
## for managing parameters the following query is excuted 

 ```sql
= MySQL.Database("localhost:3306", "awesome chocolates", [ReturnSingleDatabase=true, Query="select * from sales #(lf)where PID = '"& #"product code" & "'"]);
```


- after executing the above queries we can easily design a dashboard and work with schemas using  data , buid and format provided by the power bi .

## In  given dashboard the sales analysis of different products are carried out by the steps shown in images :

   (![Screenshot (60)](https://github.com/hardikty/sales-analysis-pt2/assets/174869730/542ecd0e-e3ff-4182-a150-0750ee1e673a)

   (![Screenshot (62)](https://github.com/hardikty/sales-analysis-pt2/assets/174869730/48a41298-0965-4e05-8d91-9fd0e1552d60)

   (![Screenshot (65)](https://github.com/hardikty/sales-analysis-pt2/assets/174869730/646cc516-171b-4804-ad50-6f7777318972)


   go to qurry 1 , click on edit permission

   (![Screenshot (66)](https://github.com/hardikty/sales-analysis-pt2/assets/174869730/4f25baa9-47dc-4582-896d-fdc60a52bf2d)

   the data related only to product 12 will be displayed

   (![Screenshot (68)](https://github.com/hardikty/sales-analysis-pt2/assets/174869730/5922a1c8-12d1-46c2-8308-f4d9bb642c75)

   click on (close and apply)

   it  will automatically  display  sales analysis  related to product 12 of amazing chocolate company:

   (![image](https://github.com/hardikty/sales-analysis-pt2/assets/174869730/585ad6ec-f9e0-4c81-9679-5adf3acedeb1)








     

   


     


