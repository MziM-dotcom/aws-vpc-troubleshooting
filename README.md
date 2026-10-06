# aws-vpc-troubleshooting
Troubleshoot VPC instances - instance A cannot reach the internet, instance B can reach the internet

<h1>INSTANCE CONNECTION ISSUE</h1>
Hello, Cloud Support!        
We currently have one virtual private cloud (VPC) with a CIDR range of 10.0.0.0/16. In this VPC, we have two Amazon Elastic Compute Cloud (Amazon EC2) instances: instance A and instance B. Even though both are in the same subnet and have the same configurations with AWS resources, instance A cannot reach the internet, and instance B can reach the internet. I think it has something to do with the EC2 instances, but I'm not sure. I also had a question about using a public range of IP address such as 12.0.0.0/16 for a VPC that I would like to launch. Would that cause any issues? 

<h1>Navigate to AWS Console and check the IP Addresses of instances</h1>
Instance A IP address details
<img width="1630" height="532" alt="image" src="https://github.com/user-attachments/assets/e071a07b-125d-48be-b9a5-3fb074828a6a" />
Instance B IP Address details
<img width="1622" height="537" alt="image" src="https://github.com/user-attachments/assets/70ddc775-3198-4a4d-86b8-0ab103d78693" />

<h1>Connect to Instances using PowerShell</h1>
I can connect to instance B without any issues
<img width="966" height="452" alt="image" src="https://github.com/user-attachments/assets/78c487ea-eab6-432a-a1ad-0e9d14826f7d" />

<h1>I cannot connect to Instance A - Connection timed out</h1>
<img width="1098" height="188" alt="image" src="https://github.com/user-attachments/assets/4aafe35b-b488-46d1-a3b0-ed63446d3ea9" />

<h1>Navigate back AWS Console to update Instance A IP Addresses</h1>
Actions > Networking > Manage IP Address > Auto-Assign Public IP > Save
<img width="1911" height="862" alt="image" src="https://github.com/user-attachments/assets/662c6864-24ed-4535-91a6-b3f8298418c0" />
Confirm
<img width="682" height="303" alt="image" src="https://github.com/user-attachments/assets/aecca21c-c070-48df-b6da-bf1c6e7670e8" />

<h1>Instance A now has Public IP Address</h1>
<img width="1631" height="532" alt="image" src="https://github.com/user-attachments/assets/b5a7cf60-8d7e-4794-80d6-22b5d0d90e9a" />

<h1>Go back to PowerShell and connect to Instance A using the Public IP</h1>
<img width="1102" height="607" alt="image" src="https://github.com/user-attachments/assets/e3b19e80-cc1b-4b65-b3e5-a3e1f7c2dce3" />
Connection to the instance is now successful.




