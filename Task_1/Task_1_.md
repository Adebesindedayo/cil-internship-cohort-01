{
    "AWSTemplateFormatVersion": "2010-09-09",
    "Description": "A template is for creating lambda ",
    "Resources": {
        "LambdaFunResource": {
            "Type": "AWS::Lambda::Function",
            "Properties": {
                "FunctionName": "DayoCFT",
                
                "Code": {
                    "ZipFile": {
                        "Fn::Join": [
                            "\n",
                            [
                                
                                "def lambda_handler(event, context):",
                                "    print('THIS IS LAMBDA CREATED FROM CloudFormation')",
                                "    return 'success'"
                            ]
                        ]
                    }
                },
                "Description": "Used to run job",
                "Handler": "index.lambda_handler",
                "Role": "arn:aws:iam::13015229333333455024:role/lambda_basic_execution",
                "Runtime": "python3.6",
                "Timeout": 120
            }
        }
  }
}

------------------- Template Using  lambda python code file stored S3 Bucket ---------------------

{
    "AWSTemplateFormatVersion": "2010-09-09",
    "Description": "A template is for creating lambda from s3 buckets",
    "Resources": {
        "LambdaFunResource": {
            "Type": "AWS::Lambda::Function",
            "Properties": {
                "FunctionName": "dayoCFT",
                
                "Code": {
        "S3Bucket" : "dayo",
        "S3Key" : "index.zip"
      },
                "Description": "Used to run job",
                "Handler": "index.lambda_handler",
                "Role": "arn:aws:iam::13015229333333455024:role/lambda_basic_execution",
                "Runtime": "python3.6",
                "Timeout": 120
            }
        }
  }
}