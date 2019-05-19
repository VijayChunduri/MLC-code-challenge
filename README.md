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
