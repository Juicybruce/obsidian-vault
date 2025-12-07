Is the CloudWatch log group  `tas-alert-staging-jobs-runner` the generic logger for all lambda activity (incl. the database swapper)?

The lambda failover DNS rewrite is triggered  by the failover event from RDS (from event bridge), there is ALSO a lambda function that does the same thing as part of the **automatic** failover. The DNS change basically occurs twice
- Should this chain of alarms be documented? CW Metric - CW Alarm - Route53 alarms - Route 53 aggregate alarm - CW alarm - SNS Topic - LAMBDA TRIGGER
ebaf9f2ba4d74760ab671b84487ca3dd
