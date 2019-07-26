# Device Registry Serivice 

## Usage 

All responses will have the form 

'''json 
{
	"data": "Mixed type holding the content of the response"
	"messsage": "Description of what happend"
}
'''

Subsequent  response definitions will only detail the expecte value of the 'data field'

### List of all devices 
'Get /devices '

**Definition**

'GET /devices'

- '200 OK' on success 

'''json 
[
	{
		"identifier": "floor-lamp",
		"name": "Floor lamp",
		"device_type": "switch",
		"controller_gateway": "192.1.68.0.2"
	}
	{
		"identifier": "samsung-tv",
		"name": "Living Room tv",
		"device_type": "tv",
		"controller_gateway": "192.1.68.0.2"
	}
]

'''

**Definition**
'POST /devices'

**Arguments**

- '"identifier":string' a globally unique identifier for this device
- '"name":string' a friendly name for this device 
- '"device_type":string' the type of device as understood by the client 
- '"name":string' The IP adress of the device's controller

If a device with the given identifier already excist, the existing device will be overwritten

**Response**

- '201 Created ' on success 

'''json 
	{
		"identifier": "floor-lamp",
		"name": "Floor lamp",
		"device_type": "switch",
		"controller_gateway": "192.1.68.0.2"
	}

'''

## Lookup device details 

'GET /device/<identifier>'

**Response**
- '404 Not Found' if the device does not exist 
'200 OK' on success

'''json 
	{
		"identifier": "floor-lamp",
		"name": "Floor lamp",
		"device_type": "switch",
		"controller_gateway": "192.1.68.0.2"
	}

'''


