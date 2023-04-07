<!-- SQL QUESTIONS PART -->
# SQL QUESTIONS PART
This part explores the world of Formula 1 racing using SQL queries on a collection of data in CSV format. The dataset includes information on drivers, constructors, races, results, lap times, qualifying times, pit stops, and more. The goal of this project is to gain insights into the performance of drivers and constructors over time, as well as the factors that contribute to success in F1 racing.

## GETTING STARTED
To run the SQL queries in this project, you will need to have a SQLite database set up on your machine. You can create a new database using the SQLite command-line interface (CLI), or you can use a tool like DB Browser for SQLite, which provides a graphical interface for managing databases.

Once you have a database set up, you can use Python and the sqlite3 module to execute SQL queries on the data. The project includes a Jupyter notebook (F1-Questions-SQL.ipynb) that demonstrates how to connect to a SQLite database and run SQL queries using Python.

## DATA DICTIONARY

### <p align="center"> circuits.csv </p>
| <span style="color:red" > Column Name </span>   | <span style="color:red" > Description  </span>|
| --- | --- |
| circuitId | Unique identifier for each circuit (numeric) |
| circuitRef | Unique reference code for each circuit (alphanumeric) |
| name | Name of the circuit (text) |
| Location | Name of the city or locality where the circuit is located (text) |
| country | Name of the country where the circuit is located (text) | 
| lat | Latitude coordinate of the circuit (numeric) |
| lng | Longitude coordinate of the circuit (numeric) |
| alt | Altitude of the circuit in meters (numeric) |
| url | URL of the Wikipedia page for the circuit (text) | 
<br> 


### <p align="center">constructor_results.csv</p>
| <span style="color:red" > Column Name </span>   | <span style="color:red" > Description  </span>|
| --- | --- |
| constructorResultsId | Unique identifier for each constructor result (numeric) |
| raceId | Unique identifier for the race (numeric) |
| constructorId | Unique identifier for the constructor (numeric) |
| points | Points scored by the constructor in the race (numeric) |
| status | Status of the constructor's result in the race (text). If the value is "\N", it means the status is not available. | 
<br> 


### <p align="center">constructors.csv</p>
| <span style="color:red" > Column Name </span>   | <span style="color:red" > Description  </span>|
| --- | --- |
| constructorId | A unique identifier for the constructor (numeric) |
| constructorRef | A short name for the constructor (text) |
| name | The full name of the constructor (text) |
| nationality | The nationality of the constructor (text) |
| url | A link to the constructor's website |
<br> 


### <p align="center">constructor_standings.csv</p>
| <span style="color:red" > Column Name </span>   | <span style="color:red" > Description  </span>|
| --- | --- |
| constructorResultsId | A unique identifier for the constructor results (numeric) |
| raceId | A unique identifier for the race (numeric) |
| constructorId |  unique identifier for the constructor (numeric) |
| points | The number of points the constructor scored in the race (numeric) |
| status | The status of the constructor's result in the race |
<br> 
 

### <p align="center">constructor_results.csv</p>
| <span style="color:red" > Column Name </span>   | <span style="color:red" > Description  </span>|
| --- | --- |
| constructorResultsId | Unique identifier for each constructor result (numeric) |
| raceId | Unique identifier for the race (numeric) |
| constructorId | Unique identifier for the constructor (numeric) |
| points | Points scored by the constructor in the race (numeric) |
| status | Status of the constructor's result in the race (text). If the value is "\N", it means the status is not available. |   
<br> 
 

### <p align="center">driver_standings.csv</p>
| <span style="color:red" > Column Name </span>   | <span style="color:red" > Description  </span>|
| --- | --- |
| driverStandingsId | Unique identifier for each driver standing (numeric) |
| raceId | Unique identifier for the race (numeric) |
| driverId | Unique identifier for the driver (numeric) |
| points | NPoints scored by the driver in the race (numeric) |
| position | Position of the driver in the race (numeric)| 
| positionText | Position of the driver in text format (text)|
| wins | Number of race wins by the driver (numeric)|
| alt | Altitude of the circuit in meters (numeric) |
| url | URL of the Wikipedia page for the circuit (text) |
<br> 
 
### <p align="center">drivers.csv</p>
| <span style="color:red" > Column Name </span>   | <span style="color:red" > Description  </span>|
| --- | --- |
| driverId | Unique identifier for each driver (numeric) |
| driverRef | Short reference name for the driver (text) |
| number | Race number assigned to the driver (numeric) |
| code | Three-letter code assigned to the driver (text) |
| forename | First name of the driver (text) | 
| surname | Last name of the driver (text) |
| dob | Date of birth of the driver (YYYY-MM-DD) |
| nationality | Nationality of the driver (text) |
| url | URL for the Wikipedia page of the driver (text) |  
<br> 


### <p align="center">lap_times.csv</p>
| <span style="color:red" > Column Name </span>   | <span style="color:red" > Description  </span>|
| --- | --- |
| raceId | Unique identifier for the race (numeric) |
| driverId | Unique identifier for the driver (numeric) |
| lap | Lap number (numeric) |
| position | Position of the driver in the lap (numeric) |
| time | Lap time in minutes:seconds.milliseconds format (text) | 
| milliseconds | Lap time in milliseconds (numeric) |  
<br> 
 

### <p align="center">pit_stops.csv</p>
| <span style="color:red" > Column Name </span>   | <span style="color:red" > Description  </span>|
| --- | --- |
| raceId | Unique identifier for the race (numeric) |
| driverId | Unique identifier for the driver (numeric) |
| stop | Pit stop number (numeric) |
| lap | Lap number on which the pit stop occurred (numeric) |
| time | Time at which the pit stop occurred in hh:mm:ss format (text) | 
| duration | Duration of the pit stop in minutes.seconds format (text) |
| milliseconds | Duration of the pit stop in milliseconds (numeric) |  
<br> 
 

### <p align="center">qualifying.csv  </p>
| <span style="color:red" > Column Name </span>   | <span style="color:red" > Description  </span>|
| --- | --- |
| raceId | Unique identifier for the race (numeric) |
| driverId | Unique identifier for the driver (numeric) |
| stop | Pit stop number (numeric) |
| lap | Lap number on which the pit stop occurred (numeric) |
| time | Time at which the pit stop occurred in hh:mm:ss format (text) | 
| duration | Duration of the pit stop in minutes.seconds format (text) |
| milliseconds | Duration of the pit stop in milliseconds (numeric) |  
<br> 


### <p align="center">races.csv  </p>
| <span style="color:red" > Column Name </span>   | <span style="color:red" > Description  </span>|
| --- | --- |
| raceId | Unique identifier for the race (numeric) |
| year | Year in which the race took place (numeric) |
| round | Round number of the race in the given year (numeric) |
| circuitId | Unique identifier for the circuit where the race took place (numeric) |
| name | Name of the race (text) | 
| date | Date on which the race took place in yyyy-mm-dd format (text) |
| time | Time at which the race started in hh:mm:ss format (text) |  
| circuitId | Unique identifier for the circuit where the race took place (numeric) |
| url | URL of the race's Wikipedia page (text) | 
| fp1_date | Date on which the first practice session took place in yyyy-mm-dd format (text) |
| fp1_time | Time at which the first practice session started in hh:mm:ss format (text) | 
| fp2_date | Date on which the second practice session took place in yyyy-mm-dd format (text) | 
| fp2_time | Time at which the second practice session started in hh:mm:ss format (text) |
| fp3_date | Date on which the third practice session took place in yyyy-mm-dd format (text) | 
| fp3_time | Time at which the third practice session started in hh:mm:ss format (text) | 
| quali_date | Date on which the qualifying session took place in yyyy-mm-dd format (text) |
| quali_time | Time at which the qualifying session started in hh:mm:ss format (text) | 
| sprint_date | Date on which the sprint qualifying session took place in yyyy-mm-dd format (text) |
| sprint_time | Time at which the sprint qualifying session started in hh:mm:ss format (text) | 
<br> 

### <p align="center">results.csv  </p>
| <span style="color:red" > Column Name </span>   | <span style="color:red" > Description  </span>|
| --- | --- |
| resultId | Unique identifier for the race result (numeric) |
| raceId | Unique identifier for the race (numeric) |
| driverId | Unique identifier for the driver (numeric) |
| constructorId | Unique identifier for the constructor (numeric) |
| number | Driver's race number (numeric) | 
| grid | Driver's starting position on the grid (numeric) |
| position | Finishing position of the driver (numeric) |  
| positionText | UFinishing position of the driver in text format (e.g. "1st", "2nd", etc.) |
| positionOrder | Finishing position of the driver as a number (e.g. 1, 2, etc.) | 
| points | Number of championship points awarded for the race result (numeric) |
| laps | Number of laps completed by the driver in the race (numeric) | 
| time | Total time taken by the driver to complete the race (text) | 
| milliseconds | Total time taken by the driver to complete the race in milliseconds (numeric) |
| fastestLap | Lap on which the driver set the fastest lap (numeric) | 
| rank | Driver's rank in the fastest lap (numeric) | 
| fastestLapTime | Time taken by the driver to complete the fastest lap in "mm:ss.sss" format (text) |
| fastestLapSpeed | Speed achieved by the driver during the fastest lap in kph (text) | 
| statusId | Unique identifier for the driver's race status (numeric) |
<br> 


### <p align="center">sprint_results.csv  </p>
| <span style="color:red" > Column Name </span>   | <span style="color:red" > Description  </span>|
| --- | --- |
| resultId | Unique identifier for the race result (numeric) |
| raceId | Unique identifier for the race (numeric) |
| driverId | Unique identifier for the driver (numeric) |
| constructorId | Unique identifier for the constructor (numeric) |
| number | Driver's race number (numeric) | 
| grid | Driver's starting position on the grid (numeric) |
| position | Finishing position of the driver (numeric) |  
| positionText | UFinishing position of the driver in text format (e.g. "1st", "2nd", etc.) |
| positionOrder | Finishing position of the driver as a number (e.g. 1, 2, etc.) | 
| points | Number of championship points awarded for the sprint race result (numeric) |
| laps | Number of laps completed by the driver in the sprint race (numeric) | 
| time | Total time taken by the driver to complete the sprint race (text) | 
| milliseconds | Total time taken by the driver to complete the sprint race in milliseconds (numeric) |
| fastestLap | Lap on which the driver set the fastest lap in the sprint race (numeric) | 
| fastestLapTime | Time taken by the driver to complete the fastest lap in the sprint race in "mm:ss.sss" format (text) |
| statusId | Unique identifier for the driver's sprint race status (numeric) |
<br> 

### <p align="center">sprint_results.csv  </p>
| <span style="color:red" > Column Name </span>   | <span style="color:red" > Description  </span>|
| --- | --- |
| statusId | Unique identifier for the status (numeric) |
| status | Text description of the status |

## SQL QUESTIONS
### **Question 1**: What is the total number of drivers in the drivers dataset?  
```
SELECT COUNT(*) 
FROM drivers;
```  

**output**  
Total number of drivers: 857

### **Question 2**: Which constructor has won the most races?  
```
SELECT constructors.name, COUNT(*) AS wins
FROM results
JOIN constructors ON results.constructorId = constructors.constructorId
WHERE results.position = 1
GROUP BY constructors.name
ORDER BY wins DESC;
```  

**output**  
Ferrari 243  
McLaren 179  
Mercedes 125  
Williams 114  
Red Bull 92  
Team Lotus 45  
Renault 35  
Benetton 27  
Tyrrell 23  
Brabham 23  
Lotus-Climax 22  
BRM 17  
Cooper-Climax 12  
Lotus-Ford 11  
Alfa Romeo 11  
Vanwall 10  
Matra-Ford 9  
Maserati 9  
Ligier 9  
Brawn 8  
Brabham-Repco 8  
Kurtis Kraft 5  
McLaren-Ford 4  
Jordan 4  
Wolf 3  

### **Question 3**: Which drivers have the most podiums? 
```
SELECT drivers.surname || ' ' || drivers.forename AS driver_name, 
COUNT(*) AS podiums
FROM results
JOIN drivers ON results.driverId = drivers.driverId
WHERE results.position IN (1, 2, 3)
GROUP BY driver_name
ORDER BY podiums DESC
LIMIT 5;
```  

**output**    
Hamilton Lewis 191  
Schumacher Michael 155  
Vettel Sebastian 122  
Prost Alain 106  
Räikkönen Kimi 103  


### **Question 4**: Which constructorst have the maximum points in each year? 
```
SELECT r.year, c.name AS constructor_name, MAX(cs.points) AS max_points
FROM constructor_standings cs
JOIN races r ON cs.raceId = r.raceId
JOIN constructors c ON cs.constructorId = c.constructorId
GROUP BY r.year
ORDER BY r.year DESC;
```  

**output**   
2023 Alfa Romeo 0    
2022 Alpine F1 Team 99  
2021 Alpine F1 Team 95  
2020 Renault 99  
2019 Ferrari 99  
2018 Haas F1 Team 93  
2017 Mercedes 99  
2016 Williams 96  
2015 Red Bull 96  
2014 Red Bull 99  
2013 McLaren 95  
2012 Force India 99  
2011 Mercedes 98  
2010 Renault 96  
2009 Red Bull 98.5  
2008 Ferrari 96  
2007 BMW Sauber 94  
2006 McLaren 97  
2005 Ferrari 98  
2004 Renault 96  
2003 Ferrari 95  
2002 Williams 92  
2001 McLaren 95  
2000 McLaren 98  
1999 Ferrari 97    

### **Question 5**: Which constructors have the most consecutive wins? ( That is, has at least 1 winning race at that year
```
SELECT c.name AS constructor_name, COUNT(DISTINCT r.year) AS consecutive_wins
FROM constructor_standings cs1
JOIN constructors c ON cs1.constructorId = c.constructorId
JOIN races r ON cs1.raceId = r.raceId
WHERE cs1.position = 1
AND NOT EXISTS (
    SELECT 1
    FROM constructor_standings cs2
    WHERE cs2.constructorId = cs1.constructorId
    AND cs2.position != 1
    AND cs2.raceId = cs1.raceId + 1
)
GROUP BY c.name
ORDER BY consecutive_wins DESC;
```  

**output**  
Ferrari 25  
McLaren 22  
Williams 11  
Mercedes 8  
Red Bull 6  
Team Lotus 5  
Renault 5  
Lotus-Climax 3  
BRM 3  
Tyrrell 2  
Cooper-Climax 2  
Brabham-Repco 2  
Benetton 2  
Vanwall 1  
Matra-Ford 1  
March 1  
Lotus-Ford 1  
Ligier 1  
Cooper 1  
Brawn 1  
Brabham 1  
Alfa Romeo 1  

### **Question 6**: What is the average lap time of all drivers during the 2018 Monaco Grand Prix?
```
SELECT AVG(lap_time) AS average_lap_time
FROM (
    SELECT AVG(milliseconds) AS lap_time
    FROM lap_times lt
    JOIN races r ON lt.raceId = r.raceId
    WHERE r.year = 2018 AND r.name = 'Monaco Grand Prix'
    GROUP BY lt.driverId, lt.lap
) AS subquery;
```  

**output**  
[(79857.7495042961,)]