# Create users in bulk

## Import users using the admin portal

{!fragments/xxx!}

---

## Import users using SCIM
You can create users in bulk using a SCIM request as shown below. 

**Request**

```curl
curl -v -k --user [username]:[password] --data '{"failOnErrors": [value],"schemas":[],"Operations":[{"method": [request type],"path": [end point],"bulkId": [bulk id],"data": [input user details] }] }' --header "Content-Type:application/scim+json" https://localhost:9443/scim2/Bulk
```

Below is a sample request and its corresponding response using SCIM 2.0. 

```tab="Sample Request"
curl -v -k --user admin:admin --data '{"failOnErrors":1,"schemas":["urn:ietf:params:scim:api:messages:2.0:BulkRequest"],"Operations":[{"method": "POST","path": "/Users","bulkId": "qwerty","data":{"schemas":["urn:ietf:params:scim:schemas:core:2.0:User"],"userName": "Kris","password":"krispass"}},{"method": "POST","path": "/Users","bulkId":"ytrewq","data":{"schemas":["urn:ietf:params:scim:schemas:core:2.0:User","urn:ietf:params:scim:schemas:extension:enterprise:2.0:User"],"userName":"Jesse","password":"jessepass","urn:ietf:params:scim:schemas:extension:enterprise:2.0:User":{"employeeNumber": "11250","manager": {"value": "bulkId:qwerty"}}}}]}' --header "Content-Type:application/scim+json" https://localhost:9443/scim2/Bulk
```

```tab="Sample Response"
{"schemas":["urn:ietf:params:scim:api:messages:2.0:BulkResponse"],"Operations":[{"bulkId":"qwerty","method":"POST","location":"https://localhost:9443/scim2/Users/81cbba1b-c259-485d-8ba4-79afb03e5bd1","status":{"code":201}},{"bulkId":"ytrewq","method":"POST","location":"https://localhost:9443/scim2/Users/b489dacc-fc89-449c-89f6-7acc37422031","status":{"code":201}}]}
```