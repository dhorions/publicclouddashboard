<a href="https://rapidapi.com/quodlibet/api/publiccloudwatchdashboard" target="_blank">
	<img src="https://storage.googleapis.com/code-snippets/connect-on-rapidapi-dark.png" width="107" alt="Connect on RapidAPI" style="float:right">
</a>

# Make your AWS Cloudwatch Dashboards available outside the AWS Console

With this API you can expose your AWS Cloudwatch dashboard to people that don't have an IAM user through a pre-signed private url.

## Sign Up
To signup for the API, get your API key on [RapidApi](https://rapidapi.com/quodlibet/api/publiccloudwatchdashboard).

## Parameters
### Required Parameters
#### role
To give the API access to your cloudwatch dashboard, an IAM role needs to be created that the API can use to read your dashboards.
The arn of this role should be passed to this parameter.
For more info on Providing access to AWS Accounts owned by Third Parties, see the [AWS documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_third-party.html)

```
example : arn:aws:iam::111111111111:role/cloudWatchDashAccess
```
#### externalid
When you grant our API access to your IAM role, an external ID is created that our API will use to assume the role.
For more info on using an External ID When Granting Access to Your AWS Resources to a Third Party see the [AWS documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-user_externalid.html).
The account ID that needs to be granted access to your role is 956353661285 .
```
example : A1b11ABBAaB
```
#### region
The region in which the dashboard that you want to expose is defined in.
```
example : us-east-1
```
#### dashboard
The name of the Cloudwatch Dashboard that you want to expose.
```
example : ELBDashboard
```
#### updatefrequencyunit
The unit for the update frequency.
Valid values are : month, week, day, hour, minute
Whenever a request is made to the api for a specific dashboard, a check is done if the last update of the dashboard was longer than ( updatefrequency * updatefrequencyunit ) ago.  If so, the dashboard is refreshed.

```
example : hour
```
#### updatefrequency
The update frequency.
The number of units specified in the parameter updatefrequencyunit that determine if the dashboard should be refreshed.

```
example : 1
```


### Optional Parameters
#### forceupdate
If this parameter is set to true, an update of the dashboard is done, independent of the updatefrequency and updatefrequencyunit.
```
example : true
```
#### companyname
The name of the company to be displayed on the Dashboard
```
example : ACME Inc
```
#### companyurl
The link to be used when clicking the company on the Dashboard
```
example : https://rapidapi.com/quodlibet/api/publiccloudwatchdashboard
```
#### infolinktext
The text to be used for the info link on the dashboard
```
example : more info
```
#### infolink
The link to be used when clicking the info text on the dashboard
```
example : https://rapidapi.com/quodlibet/api/publiccloudwatchdashboard
```
#### periodone
The first of the three time periods each metric on the dashboard is displayed for.
Valid values are : hour, day, week, month
Default value : hour
```
example : hour
```
![periods example](/periods.png)
#### periodtwo
The second of the three time periods each metric on the dashboard is displayed for.
Valid values are : hour, day, week, month
Default value : day
```
example : hour
```
#### periodthree
The second of the three time periods each metric on the dashboard is displayed for.
Valid values are : hour, day, week, month
Default value : week
```
example : hour
```

