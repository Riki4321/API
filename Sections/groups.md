## Get All Project or Resource Groups

```
GET /projectgroup
```
This documentation page will cover Project Groups, but for resource groups just replace project with resoruce

e.g.

```
GET /resourcegroup
```

Server Response example below for 1 projectGroup returned within an array. 

```
[{  _id: '53a168304cc0f1bb16a898ca',
    name: '788',
    projects: {["53a168304cc0f1bb16a898ca", "53a168304cc0f1bb16a898ca"]}
    metadata: '' 
}]
```

Property | Type | Description
--- | --- | ---
_id | *string* | id of the group
name | *string* | Group name
projects | *Array* | Array of Project Id's in Group
metadata | *string* | Custom Field (255 Characters)


## Get Specific Project
Use the following command to get a specific project by `id`.
```
GET /projectgroup/12345678
```
Will return projectGroup with the id `12345678`

A successful projectGroup will return a `200` Ok response status from the server.

## Create a Group
Create a new projectGroup.
```
POST /projectgroup
```
An example of a projectGroup

```
{
	"name": "My Developer Group"
}
```
The server will return the full projectGroup object once created including the newly created projectGroup ID `_id`

A successful create will return a `201` Ok response status from the server.

## Update a projectGroup
Update an existing project.
```
PUT /projectgroup/123456789
```
will update the projectGroup with the id 123456789. You must pass in the entire projectGroup object in the body. 

A successful update will return a `200` Ok response status from the server.

## Delete a projectGroup
Use the following command to delete a specific projectGroup by `id`.
```
DELETE /projectgroup/12345678
```
Will delete projectGroup with the id `12345678`

A successful delete will return a `200` Ok response status from the server.

## Add a Project to a ProjectGroup
Add a Project to a ProjectGroup
```
POST projectgroup/addProjectsToGroup/123456
Accept: application/json
Content-Type: application/json

{"projectIds":["654654365436543634","654365436543654365436"]}
```
A successful add will return a `200` Ok response status from the server.

## Add a Resource to a ResourceGroup
Add a Resource to a ResourceGroup
```
POST resourcegroup/addResourcesToGroup/123456
Accept: application/json
Content-Type: application/json

{"resourceIds":["654654365436543634","654365436543654365436"]}
```
A successful add will return a `200` Ok response status from the server.

## Remove a Project from a ProjectGroup
Remove a Project from a ProjectGroup
```
POST projectgroup/removeProjectFromGroups/123456
Accept: application/json
Content-Type: application/json

'{"groupIds":["654654365436543634","654365436543654365436"]}'
```
A successful add will return a `200` Ok response status from the server.

## Remove a Resource from a ResourceGroup
Remove a Resource from a ResourceGroup
```
POST resourcegroup/removeResourceFromGroups/123456
Accept: application/json
Content-Type: application/json

{"groupIds":["654654365436543634","654365436543654365436"]}
```
A successful add will return a `200` Ok response status from the server.

