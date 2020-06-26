
Snowflake External Function using AWS Lambda and AWS API Gateway  - A “Hello World” example

See attached Word document (Snowflake External Function using AWS Lambda.docx) for the screenshots of each step  from AWS Console & Snowflake UI

 
 Reference : https://docs.snowflake.com/en/sql-reference/external-functions-creating-aws.html

1.	Create AWS Lamda function

import json

def lambda_handler(event, context):

    # TODO implement
    array_of_rows_to_return = [ ]
    output_value = ["Hello", "IntegritD"]
    row_to_return = [0, output_value]
    array_of_rows_to_return.append(row_to_return)
    json_compatible_string_to_return = json.dumps({"data" : array_of_rows_to_return})
    return {
        'statusCode': 200,
        'body': json_compatible_string_to_return
    }

Note: External function expects JSON Array from Lambda function. So return a JSON Array. This function does not take input parameters, return  {“Hello” , “IntegritD”} 

 
 
2.	Test it in Lambda console
 

 
3.	Create an IAM Role name  “MyHelloWorldRole” with Administrator Access 
 



4.	Create REST API to call Lambda function
 
 
 
5.	Create Resource Policy 
6.	Deploy API
7.	Create Integration Object in Snowflake
 
8.	Setup the “Trusted Relationship” between Snowflake and IAM
 
 
9.	Create External Function
 
            
10.	Call External Function
 
