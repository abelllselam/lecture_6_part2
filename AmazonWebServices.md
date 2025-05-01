**Amazon Web Services**

# What exactly is AWS?

- AWS provides on-demand cloud computing platforms with either free or paid tier subscriptions.
- Most option will provide you with operating system, CPUs, GPUs, RAM, hard-disk space, etc.
- AWS is hosted on different server farms around the world distributed systems, so no worries about servers going down.

# Alternate Options:

- main reason people opt out for the other competitors like google or azure is because of costs. If you website is busy it could be costly.

# AWS Breakdown:

- There are two main instances that we will focus on
  - Amazon EC2
  - Amazon S3

# Amazon EC2:

- This stands for for Elastic Compute Cloud.
- Amazon defines this as a web service that provide resizable compute capacity in the cloud.
  - What does this really mean: this means that this is usually where you would have your Node.js server, database, etc will live.
  - The "elastic" component will allow developers to scale. It is seen as more flexable but slower than S3.

# Amazon S3 (Simple Storage Service):

- Amazon defines this as minimally built providing the ability to read, write, and delete objects.
  - This means you usually would store static service content like S3. Since web servers are typically slow and file servers are fast.

# Separate Deployment:

- With large scale application you would normally deploy the front-end to S3 and back-end to EC2 for speed and efficiency.
- No connectivity issue because request like POST AND GET will be routed to the back-end API
- The only difference is that they will not be in the same directory like your typical local machine.

# Order of Operation:

● Using the AWS console, launch your instance
○ Then FTP/SCP your server code to the AWS IP address (OR)
■ If you are smart, you will store all of you server code in Git so all you will have to do is
ssh into your instance and git clone URL
○ Setup some solid CI/CD (continuous integration/continuous deployment):)
● Start the server
● Donezo
