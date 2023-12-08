# Spring Boot H2 Database with Validation Token

- this API with DB H2, and validation token with parameter of validate Date Now

# H2 Config

- Url Console H2 http://localhost:8080/h2-ui/
- Config param (JDBC URL =jdbc:h2:mem:/test) in Console H2

# How test

1._ Genereta Token in https://jwt.io/

	token example : eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJmZWNoYVRva2VuIjoiMjAyMy0xMS0yNCJ9.D_CTNND7odd0Q6cMt6ZkdQ73R8aEpGgYbVk0zFDVVDo

     with payload :  "fechaToken": "2023-04-02",  date is a example
	 
	 the Api Validate Token with Date Now
	 
2._ Import Collection Postman , in your Postman local By test This API
	 
	{
	"info": {
		"_postman_id": "92c0d68a-0063-4fbc-b2f3-97af68c82754",
		"name": "testBackendApi",
		"schema": "https://schema.getpostman.com/json/collection/v2.0.0/collection.json",
		"_exporter_id": "13007971"
	},
	"item": [
		{
			"name": "CreatedUser",
			"request": {
				"auth": {
					"type": "bearer",
					"bearer": {
						"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJmZWNoYVRva2VuIjoiMjAyMy0wNC0wNCJ9.q3thtbOYWpAYp2C4TWzDotoptmW1S8NAOvaXR7Zltn0"
					}
				},
				"method": "POST",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "{\r\n    \"name\": \"Test Prueba\",\r\n    \"email\": \"testn@com.cl\",\r\n    \"password\": \"22Abcfgt\",\r\n    \"phones\": [\r\n                {\r\n                    \"number\": \"44444\",\r\n                    \"citycode\": \"55\",\r\n                    \"contrycode\": \"345\"\r\n                }\r\n            ]\r\n}",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": "localhost:8080/api/addUser"
			},
			"response": []
		},
		{
			"name": "getUsers",
			"request": {
				"auth": {
					"type": "bearer",
					"bearer": {
						"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJmZWNoYVRva2VuIjoiMjAyMy0wNC0wNCJ9.q3thtbOYWpAYp2C4TWzDotoptmW1S8NAOvaXR7Zltn0"
					}
				},
				"method": "GET",
				"header": [],
				"url": "localhost:8080/api/getUsers"
			},
			"response": []
		},
		{
			"name": "UpdatedUserByName",
			"request": {
				"method": "GET",
				"header": []
			},
			"response": []
		},
		{
			"name": "DeleteAll",
			"request": {
				"auth": {
					"type": "bearer",
					"bearer": {
						"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJmZWNoYVRva2VuIjoiMjAyMy0wNC0wNCJ9.q3thtbOYWpAYp2C4TWzDotoptmW1S8NAOvaXR7Zltn0"
					}
				},
				"method": "DELETE",
				"header": [],
				"url": "localhost:8080/api/deleteAll"
			},
			"response": []
		}
	]
}
	
3._ EndPoints:
	
	CreatedUser -> creation New User
	
	getUsers -> Get All Users save in BD
	
	UpdatedUserByName -> Updated  User exist in BD
	
	DeleteAll -> Delete all Rows in BD
	 


