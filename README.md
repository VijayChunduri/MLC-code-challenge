
##########
 API Name
##########

MissionMars API

###########################

API Capabilities 

############################

1) Near real time data from OpenWeatherMap API (https://openweathermap.org/forecast5) for the next 5 days (data includes for every 3 hours). </br>

2)Convert city name to city id to retrieve the information from openweathermap api. </br>

3)Retrieve information based on the city name or retrieve all cities information.</br>

4) Provide score based on the temperature, wind speed and wind direction. </br>

5) Filter the response based on the below checks. </br>
	Melbourne </br>
        Cloudiness MAX: 50% </br>
        Windspeed MAX: 20 m/second </br>
	
	Darwin </br>
	Cloudiness MAX: 40% </br>
	Windspeed MAX: 15 m/second </br>
	
	Hobart </br>
	Cloudiness MAX: 60% </br>
	Windspeed MAX: 10 m/second </br>
	
	Perth </br>
	Cloudiness MAX: 30% </br>
	Windspeed MAX: 5 m/second </br>
	
6) Sort response based on the derived score. </br>

7) Filter first 5 elements after sorting. </br>

8) Aggregate the response when fetching the information for all the cities. </br>

##########
 URL
##########

/api/getLaunchDetails

######################

Security

######################

OAuth2.0 </br>

following headers need to be added while testing through postman. </br>

client_id </br>

client_secret </br>

##########
 Method
##########

`GET`

###############  

Query Params

###############

Optional:

`cityName=[string]' 

possible values for this version of API are  </br>
		Melbourne  </br>
		Darwin  </br>
		Hobart  </br>
		Perth  </br>
		
		
####################
Success Response:
####################
  
Code: 200  </br>
Content:  </br>
	{  </br>
    "launchWindows": [  </br>
        {  </br>
            "location": "Perth", </br>
            "datetime": "2019-05-20 21:00:00", </br>
            "score2": 276.717  </br>
		}  </br>
	]  </br>
	}  </br>
	

################### 
Error Response:
###################
  
Code: 401 UNAUTHORIZED  </br>
Content:{ error : "Log in" }  </br>

        OR

Code: 403 FORBIDDEN  </br>
Content:{ error : "The request is valid, but the server is refusing to respond to it." }  </br>
  
        OR
  
Code: 404 FORBIDDEN  </br>
Content:{ error : "Backend Services is not configured or The requested resource could not be found." }  </br>
  
        OR

Code: 500 FORBIDDEN  </br>
Content:{ error : "Internal Server Error -given that when an unexpected condition was encountered and no more specific message is suitable." }  </br>

        OR

Code: 502 FORBIDDEN  </br>
Content:{ error : "The server was acting as a gateway or proxy and received an invalid response from the upstream server. Contact Middleware Services team." }  </br>

##########
URI :
##########

Launch details for all cities (Melbourne, Perth, Darwin, Hobart)  </br>
http://localhost:8081/api/getLaunchDetails  </br>

Launch details for individual city  </br>
http://localhost:8081/api/getLaunchDetails?cityName=Melbourne </br>
http://localhost:8081/api/getLaunchDetails?cityName=Perth  </br>
http://localhost:8081/api/getLaunchDetails?cityName=Darwin  </br>
http://localhost:8081/api/getLaunchDetails?cityName=Hobart  </br>

#################
Sample Response:**
#################

{  </br>
    "launchWindows": [  </br>
        { </br>
            "location": "Perth", </br>
            "datetime": "2019-05-20 21:00:00", </br>
            "score": 276.717  </br>
        }  </br>
    ]  </br>
}  </br>
