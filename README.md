# wordpress_cf
creates HA wordpress site using cloud formation template

### Prerequisites:

- AWS account
- AWS Keypair in corresponding regions to create instances
- AWS CLI(optional)

### Running the template

- Go to AWS console and choose CloudFormation from list of services
- From the CloudFormation console, choose create stack option and use the file wp_template.yml as input 
- Fill input parameters. Each input has its corresponding description in the console. (NOTE: you need an existing keypair for creating your instances. keypair cannot be created using a template)
- Based on environment provided as input(prod or dev), your site will be deployed in HA or minimal mode. HA mode(prod): multi AZ RDS and autoscaled EC2, Minimal mode(dev): single AZ RDS and single EC2 instance.
- Execute stack. It takes some time to create all the resources(RDS takes time). Once your stack is created, you can click on url of your site in the output.
- You can also use AWS CLI to create stack (ref: https://docs.aws.amazon.com/cli/latest/reference/cloudformation/index.html)

### Note
There are still some of these features that could be added to the template:
- The solution works in 2 regions only(virginia and sydney) and uses ubuntu. If we add mappings in the template for all regions and image ids, it can run in any region
- For given IP addresses range, we can grant ssh access to the instances running the site 
- Display list of all allowed values for DB and Web instance types(default values are micro instances. User should provide the right instance type as input at the moment) 
- Use EFS for prod cluster
- enable HTTPS




