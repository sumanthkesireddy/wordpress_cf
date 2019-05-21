# wordpress_cf
creates HA wordpress site using cloud formation template

### Prerequisites:

- AWS account
- AWS CLI(optional)

### Running the template

- Go to AWS console and choose Cloudformation from list of services
- Choose create stack option and use the downloaded template as input and execute
- You can also use AWS CLI to execute the template (ref: https://docs.aws.amazon.com/cli/latest/reference/cloudformation/index.html)

### Note
There are still some of these features that can be added to the template:
- The solution works in 2 regions only(virginia and sydney) and uses ubuntu. If we add mappings in the template for all regions and image ids, it can run in any region
- For given IP addresses range, we can grant ssh access to the instances running the site 
- Display list of all allowed values for DB and Web instance types(default values are micro instances. User should provide the right instance type as input at the moment) 
- Use EFS for prod cluster
- enable HTTPS




