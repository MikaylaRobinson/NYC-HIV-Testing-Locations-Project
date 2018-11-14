# How many testing locations are in each borough?
```SQL 
SELECT COUNT(Site_ID) FROM hiv_testing_locations 
	WHERE Borough = 'Brooklyn'; 
SELECT COUNT(Site_ID) FROM hiv_testing_locations 
	WHERE Borough = 'Bronx'; 
SELECT COUNT(Site_ID) FROM hiv_testing_locations 
	WHERE Borough = 'Staten Island'; 
SELECT COUNT(Site_ID) FROM hiv_testing_locations 
	WHERE Borough = 'Manhattan'; 
SELECT COUNT(Site_ID) FROM hiv_testing_locations 
	WHERE Borough = 'Queens';
```
# With varying size of boroughs, how many testing locations per square mile? (using square mileage data from wikipedia)
```SQL
(SELECT COUNT(Site_ID) / 70.82FROM hiv_testing_locations 
	WHERE Borough = 'Brooklyn'); 
SELECT COUNT(Site_ID) / 42.10 FROM hiv_testing_locations 
	WHERE Borough = 'Bronx'; 
SELECT COUNT(Site_ID) / 58.37 FROM hiv_testing_locations 
	WHERE Borough = 'Staten Island'; 
SELECT COUNT(Site_ID) / 22.83 FROM hiv_testing_locations 
	WHERE Borough = 'Manhattan'; 
SELECT COUNT(Site_ID) / 108.53 FROM hiv_testing_locations 
	WHERE Borough = 'Queens'; 
```
# Where are there low cost testing locations?
```SQL
SELECT Site_Name, Borough FROM hiv_testing_locations
	WHERE Low_Cost = 'TRUE';
```
# Which locations provide free HIV testing?
```SQL
SELECT Site_Name, Borough  FROM hiv_testing_locations
    WHERE Free = 'TRUE'
    ORDER BY Borough;
```
# Where can you walk in for a free HIV test? 
```SQL
SELECT Site_Name, Borough FROM hiv_testing_locations
	WHERE Free = 'TRUE' and Intake = 'Walk-ins welcome'
    ORDER BY Borough;
``` 
# What type of documentation do you need to bring for your test at Community Healthcare Network?
```SQL
SELECT Required_Documents from hiv_testing_locations
	WHERE Agency_ID = 'Community Healthcare Network'; 
```