# Healthcare-Dashboard

### Dashboard Link :https://app.powerbi.com/groups/me/reports/b304a06e-eb97-4e8e-a5d0-6a133e02c471/16429a85c10647c2741d

## Problem Statement

Adequate healthcare facilities and easy access to them is key in achieving universal healthcare coverage. This dashboard helps the government and the stakeholders understand distribution, efficiency, and access to healthcare facilities across rural and urban regions in Africa. 
It also provides better insihgts into the availability of healthworkforce across rural and urban regions in Africa. Therefore, a treemap visual describes distribution of facilities across regions.
On average, the ratio of facilities to population is low for both regions. Although the health facilities to population ratio is low for both regions,urban regions in particular require more focus to address their growing population. Since by using this dashboard this problem has been identified, they can further work on increasing the number of healthcare facilities for both regions, particularly the urban regions for better access. 


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is an excel file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present.
- Step 5 : A new custom column was added based on a specified condition, grouping regions into rural or urban.

            If (population) < 5000 then “Rural” else “Urban”.

- Step 6 : The new custom column was changed to a text data format.
- Step 7 : The dataset was loaded to the Power BI editor interface. 
- Step 8 : The funding recieved column was changed to the dollar currency format in the Table View of Power BI.Visual.
- Step 9 : New measures were created with the following DAX expression and viewed with card visuals.

  (a) Urban region total population.
	Total_population_urban = CALCULATE(SUM('Healthcare data W'[Population]), 'Healthcare data W'[Region Classification] = "Urban").
	
	![Image](https://github.com/user-attachments/assets/c8154def-ee42-4dbf-8d2b-15ccffa8d761)
  
  (b) Rural region total population
	Total_population_rural = CALCULATE(SUM('Healthcare data W'[Population]), 'Healthcare data W'[Region Classification] = "Rural").

	![Image](https://github.com/user-attachments/assets/f10a8a92-2da0-4ac9-a311-ead3361fda24)

  (c) Total urban facility.
	Total_facility_urban = CALCULATE(COUNT('Healthcare data W'[Facility Name]), 'Healthcare data W'[Region Classification] = "Urban").

	![Image](https://github.com/user-attachments/assets/741ec021-b08d-4e3d-8faa-44aaf783b9d0)

  (d) Total rural facility.
	Total_facility_rural = CALCULATE(COUNT('Healthcare data W'[Facility Name]), 'Healthcare data W'[Region Classification] = "Rural").

	![Image](https://github.com/user-attachments/assets/cb6d7c1b-f72e-4f0f-8b8c-a1f4bf964621)

  (e) Average rural emergency response time.
	Avg_emergencytime_rural = CALCULATE(AVERAGE('Healthcare data W'[Emergency Response Time (minutes)]), 'Healthcare data W'[Region Classification] = "Rural").

	![Image](https://github.com/user-attachments/assets/113e32fa-d6fe-4e3b-9009-9412c79d9dc3)

  (f) Average urban emergency response time.
	Avg_emergencytime_urban = CALCULATE(AVERAGE('Healthcare data W'[Emergency Response Time (minutes)]), 'Healthcare data W'[Region Classification] = "Urban").

	![Image](https://github.com/user-attachments/assets/624e21c5-b179-40cd-b02c-ac4d14f4f7cf)

- Step 10 : A treemap visual was added to the report design area representing the number of facility and total population by regions.

	![Image](https://github.com/user-attachments/assets/d1dd0b9b-bac4-447b-af3b-b137015f77bd)
        
- Step 11: New measure was created to find total count of healthcare workers.

Following DAX expression was written,
        
        Total_Healthcare_workers= 'Healthcare data W'[Number of Doctors] + 'Healthcare data W'[Number of Nurses]
        
A pie chart was used to represent total count of healthworkers by regions.

	![Image](https://github.com/user-attachments/assets/565211b1-972b-4a13-9ad9-c6b61dcae770)
        
 
 - Step 12 : Average distance to facility (km) by regions was visualized with a donut chart.
 
	![Image](https://github.com/user-attachments/assets/2a4e6294-339e-46e1-96af-22245cabf732)

 - Step 12 : Sum of funding (USD) received by regions was visualized with a clustered bar chart

	![Image](https://github.com/user-attachments/assets/65af6e07-ccd8-41dd-94db-112d76654fd7)

- Step 13: Count of electricity and internet availability were visualized with clustered column charts.

	![Image](https://github.com/user-attachments/assets/b9279a8f-afcc-4b65-b436-4835e241ca6c)


	![Image](https://github.com/user-attachments/assets/32c0c7d9-f2c0-4d2a-b947-b34efdddde11)

- Step 14:A slicer of the ten regions where data was collected in Africa was added and connected to all the visuals

	![Image](https://github.com/user-attachments/assets/452cb740-2bff-4557-ba1d-8326a9a9425e)

- Step 15: The report was then published to Power BI Service.
 
 # Snapshot of Dashboard (Power BI Service)

![Image](https://github.com/user-attachments/assets/e8111e1b-ca2a-495e-bdc9-92fa28c4ad4f)
 
 # Report Snapshot (Power BI DESKTOP)

 
![Image](https://github.com/user-attachments/assets/60b0bfbd-5533-4908-980b-b2927fe8af1e)

# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] Total population of rural regions = 3,000000 and Total population of Urban regions = 8,000000

   Total rural health facility = 931 and Total urban facility = 1069

   Average rural regions emergency response time(minute) = 32.27 and Average urban regions emergency response time(minute) = 32.53

           thus, for both rural and urban regions, the ratio of facility to population is low. Also, the average response time to an emergency case is much.
           
### [2] Total healthcare workers (doctors + nurses)
	
	Rural regions = 35,384

	Urban regions = 40,372
		
		thus, for both regions, the ratio of total healthcare workers to population is low and much lower for urban regions.
   
  ### [3] Electricity availability

	Rural regions: 448 facilities have electricity while 443 have no electricity

	Urban regions: 530 facilities have electricity while 539 have no electricity

		thus, there is no electricity in about half or more than half of healthcare facilities in both regions 
  
      
 ### [4] Average distance (km) to facility

	Rural regions: 10.50

	Urban regions: 10.66

		thus, the average distance for both regions is good enough and should encourage patients to visit healthcare facilities.
 
 ### [5] Sum of funding(USD) received.

	Rural regions = $99,462,667

	Urban regions = $113,633,611

		thus,lack of electricity and internet in about half of the total facilities in rural and urban regions suggests that funding is not enough or some healthcare facilities are not receiving enough funding.
