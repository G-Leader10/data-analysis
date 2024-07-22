
# Electrical vehicles data analysis

About the dataset
This dataset is from the Kaggle website and contains 150482 rows and 17 columns. These are the different columns that we have: 
This dataset shows the Battery Electric Vehicles (BEVs) and Plug-in Hybrid Electric Vehicles (PHEVs) that are currently registered through the Washington State Department of Licensing (DOL). BEV sales during Q2 2023 grew over 50% YoY. One in every 10 cars sold during Q2 2023 was a pure battery electric vehicle (BEV). China remained the leader in global BEV sales followed by USA and Germany. BEV sales in the USA grew by almost 57% YoY, the highest among the top 3 EV markets

Brief Information About the Features of Dataset:

1. VIN: A Vehicle Identification Number (VIN) is the identifying code for a specific automobile.
2. Country: Country where it is Manufactured.
3. City: location of Company that manufactures Electric Cars.
4. state: This is the state where they are registered all of them are from Washington
5. Postal Code: Pin code is the post office numbering code system used by the postal service.
6. Model Year: a year in which the car was manufactured.
7. Make Name of Company.
8. Model: A vehicle identification number (VIN) is a unique, 17-digit code specific to every vehicle.
9. Electric Vehicle Type: When talking about EVs, we generally refer to three main types of electric 
10. vehicles: hybrid electric vehicles (HEV), plug-in hybrid electric vehicles (PHEV), and battery electric vehicles (BEV).
11. Clean Alternative Fuel Vehicle: Vegetable oils, such as palm, soybean, sunflower, peanut, and olive, as alternative fuels can be used for diesel engines. As an alternative fuel, vegetable oil is one of the renewable fuels.
12. Electric Range: All-electric vehicles can typically go between 110 and over 300 miles on a single charge. PHEVs can typically go 15â€“60 miles on battery power alone; the fuel tank capacity determines their overall range because the engine kicks in when the battery is depleted.
13. Base MSRP: Manufacturers set a base price for a car or vehicle without add-on products or features. The Manufacturer's Suggested Retail Price (MSRP) is the base price plus additional features.
14. Legislative District: While the Legislature of every State shall consist of the Governor and the State Legislature, in some of the States, the Legislature shall consist of two Houses, namely, the Legislative Assembly and the Legislative Council, while in the rest, there shall be only one House, namely the legislative assembly.
15. DOL Vehicle ID: DOL Vehicle ID. A unique identification number for each vehicle is present in the Transactions dataset. Transactions done on the same vehicle will have the same DOL Vehicle ID.
Vehicle Location: In cases where the vehicle was designed for electric motors, they are generally located at the front and/or rear between the wheels. Short half-shafts connect the output of the motors to the wheels.
16. Electric Utility: A corporation, person, agency, authority, or other legal entity or instrumentality aligned with distribution facilities for delivery of electric energy for use primarily by the public.
17. 2020 Census Tract: Census tracts are relatively permanent small-area geographic divisions of a county or statistically equivalent entity defined for the tabulation and presentation of data from the decennial census and selected other statistical programs

Problem statement

A. KPI'S Requirement 
1. Total Vehicles:
Understand the overall landscape of electric vehicles, encompassing both BEVs and PHEVs, to assess the market's size and growth.

2. Average Electric Range:
Determine the average electric range of the electric vehicles in the dataset to gauge the technological advancements and efficiency of the EVs.

3. Total BEV Vehicles and % of Total BEV Vehicles:
Identify and analyze the total number of Battery Electric Vehicles (BEVs) in the dataset.
Calculate the percentage of BEVs relative to the total number of electric vehicles, providing insights into the dominance of fully electric models.

4. Total PHEV Vehicles and % of Total PHEV Vehicles:
Identify and analyze the total number of Plug-in Hybrid Electric Vehicles (PHEVs) in the dataset.
Calculate the percentage of PHEVs relative to the total number of electric vehicles, offering insights into the market share of plug-in hybrid models.

B. charts requirements

1. Total Vehicles by Model Year (From 2010 Onwards):
Visualization: Line/ Area Chart
Description: This chart will illustrate the distribution of electric vehicles over the years, starting from 2010, providing insights into the growth pattern and adoption trends.

2. Total Vehicles by State:
Visualization: Map Chart 
Description: This chart will showcase the geographical distribution of electric vehicles across different states, allowing for the identification of regions with higher adoption rates.

3. Top 10 Total Vehicles by Make:
Visualization: Bar Chart 
Description: Highlight the top 10 electric vehicle manufacturers based on the total number of vehicles, providing insights into the market dominance of specific brands.

4. Total Vehicles by CAFV Eligibility:
Visualization: Pie Chart or Donut Chart
Description: Illustrate the proportion of electric vehicles that are eligible for Clean Alternative Fuel Vehicle (CAFV) incentives, aiding in understanding the impact of incentives on vehicle adoption.

5. Top 10 Total Vehicles by Model:
Visualization: Treemap
Description: Highlight the top 10 electric vehicle models based on the total number of vehicles, offering insights into consumer preferences and popular models in the market.

# steps followed

1. open the csv file in excel to check the dataset
2. import dataset CSV file (150483 rows and 17 columns) into Tableau
3. display the dataset into the Tableau: it displays 100 rows by default 
4. check if all the data have been updated successfully
# KPI'S requirements Problem statement resolutions
5. compute the total vehicle:
we created a new sheet named Total Vehicles, after that we had to count the number of vehicles and for that, we considered the DOL vehicle ID which represents the vehicle ID or primary key. we created a calculation field named total vehicles where we will use the COUNTD() function which counts each field by considering duplicate once: COUNTD(DOL Vehicle ID) then bring it to text. Results:150482 vehicles
after filtering from 2011 to 2024 the current year the value will be 150422

6. Compute Average Electric range
create a new sheet and name it Average Electric range. So here we will consider the Electric range row and compute the average by creating a new calculation field named AvgElectricRange by using the AVG() function:
AVG([Electric Range]) then add it to text to display the Results. Average of Electric range = 67.88 miles
we will add a filter to show the results from 2011 from all the results to ongoing years by choosing at least 2011 after filtering the value will be 67.83 miles

7. Total BEV Vehicles and % of Total BEV Vehicles
In a new sheet, we will create a new calculation field named TotalBEV Vehicles in which we will use this formula: 
COUNTD(
if[Electric Vehicle Type] = "Battery Electric vehicle (BEV)" 
THEN [DOL Vehicle ID]
END
)
Then add it to the text. Results = 116750
then to add the percentage, we will create a new calculation field named % of BEV Vehicles by using this formula [Total BEV Vehicles] / [Total Vehicles] then we add it to the text by clicking on the field then choosing default format numbers as percentages. 
% results = 77.6%

8. Total PHEV Vehicles and % of Total PHEV Vehicles
we create a new calculation field with the same name and then use this formula:
COUNTD(
if[Electric Vehicle Type] = "Plug-in Hybrid Electric Vehicle (PHEV)" 
THEN [DOL Vehicle ID]
END
)
Total results of PHEV = 33672
Then compute the average by using:
[Total PEHV Vehicles] / [Total Vehicles] 
% results = 22.4%

# KPI'S insights
1. Total vehicles is 150422
2. Average Electrical range for all the vehicles is 67.83 miles
3. From 150422 vehicles 116750 are Battery Electric Vehicles and it is occupying 77.6% of the vehicles markets
4. From 150422 vehicles 33672 are Plug-in Electric Vehicles taking 22.4% of the markets

# charts requirements
5. Total Vehicles by Model Year (From 2010 Onwards)
Here we added the model year in the columns and Total vehicles in rows then we edited the axis to fixed start from 2011. we used the dual axis by merging the line and area on each other which will have an average line. The trends show that the adoption of electrical vehicles is going higher year by the year 2023 has the highest 37.1k

6. Total Vehicles by State
In a new sheet, as we are dealing with the geographical map we need to use longitude as columns and latitude as rows then we add state into the details. Then double click into unknown then edit the locations by changing the country to USA. In size choose the shape then show me the change to shape map put the total vehicles into color then exclude some unwanted parts from the map. we added the total vehicles into the label from which we can see that 99% of vehicles are from Washington 150082 out of 150422

7. Top 10 Total Vehicles by Make
create a new sheet named "Top 10 total vehicles by make" In columns, we added total vehicles and in rows make then sorted it in descending order. To find out the top 10, we added make into filters, top by field then in top change the 10 into create a parameter name (TopN) it and then display format choose 10, current value 10 minimum 1, maximum 15 as fixed. Then we added the total vehicles as the label to convert it into a percentage click on the total vehicles label and click quick label calculation then the percentage of total then added the total vehicles again to show also the number.
The results show that:
- Tesla is leading with 52.70% which is 68943
- Nissan 10.32% which is 13497
- Chevrolet with 9.19% which is 12025
- Ford with 5.81% which is 7601
- BMW with 4.92% which is 6439
- KIA with 4.74% which is 6198
- TOYOTA with 3.99% which is 5220
- VOLKSWAGEN with 3.11% which is 4074
- VOLVO with 2.70% which is 3536
- JEEP with 2.52% which is 3292
Notice that the TopN can be modified from 1 to 15 as well as the title of the charts by inserting a parameter TopN we used 3 filters: make, state, and Electric vehicle Type  then made state and electric vehicle type as context filters and according to these the previous results can change

8. Total Vehicles by CAFV Eligibility
In a new sheet, we have to create a donut chart using a Pie chart with the help of some calculations. we added CAFV in colors to the Pie and total vehicles to the angle. to convert it to a donut chart we added AVG of 0 in rows twice after removing everything from one average, we made them dual axis then modified the size making the first bigger than the second then modified the background of the second to white then added total vehicle into labels then converted it into percentage and then to see the numbers we re-added the total vehicle into labels and to see names we added CAFV into labels then gave them alias. From this, we can have the following insights: 
- CAFV unknown: the research still going on these vehicles if they are eligible with government standards or not 46.33% which is 69697 vehicles
- CAFV eligible: These are eligible with government standard 41.81% which is 62887 vehicles
- CAFV not eligible: which do not qualify according to the government Eligibility 11.85% which is 17829 vehicles    

9. Top 10 Total Vehicles by Model
In a new sheet, we added model, make, and electric vehicle type into rows, and total vehicles into text and transformed it into percentages. Again, total vehicles are in numbers in the column measure name. Then sort it in descending order after editing Electrical vehicle names. We added total vehicles to the colors for design purposes. From this we can see the total vehicles by model:
- The BEV is the dominant occupying the first 6 places with make:  Tesla, Nissan, and Chevrolet
- Tesla is the leading 
- some have both BEV and PEHV 

