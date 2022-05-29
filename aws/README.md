# AWS

### Billing Alarm 

Before a billing alarm can be created, must select to receive billing alerts in the Billing console. See https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/monitor_estimated_charges_with_cloudwatch.html 

Billing metric data is stored in us-east-1 (N.Virginia). 

Then proceed with Cloud Watch alarm. 

```
aws --region us-east-1 cloudformation deploy --template-file billing_alarm.yaml `
    --parameter-overrides AdminEmail=$env:ADMIN_EMAIL AlarmThreshold=$env:AlarmThreshold `
    --stack-name "billing-alarm-stack"
```