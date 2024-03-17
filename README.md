# Cloud-project-3-tier-web-application-on-AWS-

As a first conception we come up with a version of a version that aims more on the security neglecting the other aspects when it comes to for example the multi-region availability :


![image](https://github.com/GuiguiSalma/Cloud-project-3-tier-web-application-on-AWS-/assets/132245605/ba0a25aa-8e09-4940-96bc-43696d798c2d)

Then for more freedome when working with **AWS learner lab** we went with the below schema as a lot of services were not available ( the IAM roles as example):


![image](https://github.com/GuiguiSalma/Cloud-project-3-tier-web-application-on-AWS-/assets/132245605/7cac019a-6d33-4cba-8eea-d91957072d31)

"*" Scalability:
Given our project ,'Smart education platform', wich will see a growth of 90%  we useed a VPC with a  /16 CIDR block.We added of course the **internet gateway** for connectivity with the INTERNET and **NAT gateways** for for the outbound trafic for the two regions (having multiple regions will help in time of crisis so you can find a backup):

![imag](https://myoctocat.com/assets/images/base-octocat.svg](https://github.com/GuiguiSalma/Cloud-project-3-tier-web-application-on-AWS-/assets/132245605/b3d94d79-bdcb-46d7-8ad6-df0b6d64cfd))


"*" Autoscaling:
This will allow our instances to perform based on the demand, for example not a lot of traffic on our platform? turn-off the by-standers instances( as i like to call them :) ) , a lot of traffic is comming our way? No problem, more computing power will be added as more instances will be created.Exemple below to show that sometimes it can be specified.

![image](https://github.com/GuiguiSalma/Cloud-project-3-tier-web-application-on-AWS-/assets/132245605/7ff41d70-438c-4c0d-b110-80367d092342)

But numerous time you got to create an auto-scaling group as we did:

![pp](https://github.com/GuiguiSalma/Cloud-project-3-tier-web-application-on-AWS-/assets/132245605/a0eb2ee0-56fb-4b6e-b2fd-425d98b514b3)

"*" Security:
Security was applied in our project  through:
##### secutity groups first :
  Each Tier had it's own security group and route table to manage inboud and outbound trafic and who can access them. Specially the Database tier
##### Encryption:
  Encryption of the Data in our Database
##### AWS WAF:
  For the prevention of the DDOS atacks as exemple

"*" Additional informations:
-For some services/instances we took **snapshots** specially as we had two availibilty zones. It lets you replicate the instances as it is, with the same configurations.
-We added a **CloudWatch alarm** in our Apptier for when the https requests exceeds an amount.
-We of course created the internal and external **load balencers** to ensure equality between our servers :)
-The **S3 bucket** was used for the deployment of the app.
-the presentation is not detailed and doesn't go through the whole process.

