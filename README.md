##########
 API Name
##########

MissionMars API
  
##########
 URL
##########

/api/getLaunchDetails

##########
 Method:
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
  
Code: 200
Content: 
	{
    "launchWindows": [
        {
            "location": "Perth",
            "datetime": "2019-05-20 21:00:00",
            "score2": 276.717
		}
	]
	}
	

################### 
Error Response:
###################
  
Code: 401 UNAUTHORIZED
Content:{ error : "Log in" }

        OR

Code: 403 FORBIDDEN
Content:{ error : "The request is valid, but the server is refusing to respond to it." }
  
        OR
  
Code: 404 FORBIDDEN
Content:{ error : "Backend Services is not configured or The requested resource could not be found." }
  
        OR

Code: 500 FORBIDDEN
Content:{ error : "Internal Server Error -given that when an unexpected condition was encountered and no more specific message is suitable." }

        OR

Code: 502 FORBIDDEN
Content:{ error : "The server was acting as a gateway or proxy and received an invalid response from the upstream server. Contact Middleware Services team." }

##########
URI :
##########

Launch details for all cities (Melbourne, Perth, Darwin, Hobart)
http://localhost:8081/api/getLaunchDetails

Launch details for individual city  </br>
http://localhost:8081/api/getLaunchDetails?cityName=Melbourne </br>
http://localhost:8081/api/getLaunchDetails?cityName=Perth  </br>
http://localhost:8081/api/getLaunchDetails?cityName=Darwin  </br>
http://localhost:8081/api/getLaunchDetails?cityName=Hobart  </br>

#################
Sample Response:**
#################

{
    "launchWindows": [
        {
            "location": "Perth",
            "datetime": "2019-05-20 21:00:00",
            "score": 276.717
        }
    ]
}
