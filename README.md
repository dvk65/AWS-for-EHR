# AWS-for-EHR
Secure Cloud Computing for NLP tasks involving private data from Electronic Health Records

This jupyter notebook has code blocks to interract with AWS services at different instances. The complete flow of the project was as follows:<br>
![project flow](https://github.com/dvk65/AWS-for-EHR/blob/main/FlowChart.png)
The project started by completing the "Data or Specimens Only Research" training from the Physionet CITI Program. The completion report received after this course was sent to our supervisor who then confirmed it with the Physionet team and we got access to the MIMIC-III data. <br>
The data was available in an S3 bucket on AWS in the form of 27 csv files. These files were merged to form one file. The merged csv was further filtered to contain only relevant columns that had text or descriptive data and rows with less than 10 NaN values. <br>
Each of these rows were converted into individual text files of patient records.<br>
We passed this data through AWS Comprehend Medical (which is a service that abides by the HIPAA guidelines) to get further insights into the data and saved these files. <br>
AWS Bedrock also abides by the HIPAA guidelines which is why it can be used on confidential data. Titan Text G1 – Express, Mistral 7B Instruct and Mixtral 8x7B Instruct models were compared on the output directly received from Physionet and the output after passing patient records to AWS Comprehend Medical.<br><br>
### Steps to run:
After getting access to the data, AWS cli command ("aws configure") can be used to store AWS credentials such as access key and secret access key.
These credentials will be used by the boto3 package to access the AWS services used.<br>
It is a python notebook. The repository can be cloned and the code blocks can be run as required to follow along with the project flow.
