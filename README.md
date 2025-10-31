
LIVE DEMO: https://livedemo.dvbqgmw7hph4l.amplifyapp.com/

This project is a cloud based web hosting and monitoring system that uses AWS services to deploy, manage and secure a static website. The main goal of the architecture is to make the website always available to users while automatically monitoring all activities and sending alerts if anything suspicious occurs. The workflow is made up of differect phases.

PHASE 1: WEBSITE DEPLOYMENT AND HOSTING
   This project begins with AWS Amplify, a fully managed service that simplifies web applications. It uploads the sites' static files to an Amazon S3 bucket where they are safely stored. 
   
   Amplify-> S3: Amplify deploys and stores the files in s3 bucket
   
   S3-> Amplify: When a user visits the site from their browser, Amplify fetches those files from the S3 bucket and serves them to the user.
     S3 is the storage layer while Amplify is the deployment and delivery layer.

PHASE 2: ACTIVITY TRACKING
   AWS Cloudtrail is used to record every action that occurs in this website. It makes an audit trail and keeps track of every user or resource action.

PHASE 3: LOGGING AND MONITORING
   All the activity logs recorded by cloudtrail are sent to Amazon Cloudwatch logs, where they are stored and can be analyzed. Cloudwatch monitors app performance, detect anomalies and visualize metrics. Metric filter is used to look for specific patterns or keywords in logs. When such pattern is detected, it triggers an alarm.

PHASE 4: ALERTING
   Alarm is triggered but since this will only occur in your AWS console and if you are not active, you will miss it. Amazon SNS is used to deliver alerts to your email.

PHASE 5: ADMIN NOTIFICATION
   The final step is email notification. Whenever a suspicious event occurs, the admin instantly receives an email alert, allowing them to take quick action. 
