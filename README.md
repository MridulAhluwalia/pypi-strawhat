# pypi-strawhat
My own python module with useful functions

# StrawHat module contains wrapper for aws boto3

This module makes interacting with aws services quite simple. It is built on top of AWS' boto3 module

## Key Features

> - Module has inbuit handling of `LastEvaluatedKey` while calling scan and query operations
> - Module will convert `float` to `Decimal` while calling put and update operations
> - Module will convert `Decimal` to `float` while calling scan and query operations

## How to use

Below snippet contains a basic guide to use access dynamodb

```python
# imports
from strawhat.aws import AWS, Dynamodb

# constants
access_key = '***'
secret_key = '***'
region = 'ap-south-1'
table_name = 'my_table'

# initialising aws instance
aws = AWS(access_key, secret_key, region) # default region is 'ap-south-1'
db_resource = aws.resource('dynamodb')

# initialise dynamodb
db = Dynamodb(db_resource)
db.create_table(table_name)

# executing a scan operation
conditions = {} # put the condtions for scan in the dictionary
responses = db.scan_table(table_name, conditions)
```

## Supported Functions

> #### Dynamodb
- scan_table(table_name, conditions)
- put_data(table_name, data)
- batch_write(table_name, data_list)

> #### S3
- read_object(bucket_name, bucket_object)

## User Note

The module is still a work in progress
