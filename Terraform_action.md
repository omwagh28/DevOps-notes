Class Revision Notes on AWS and Terraform
Introduction

Is class me humne AWS networking concepts aur Terraform ke use ke baare me padha. Focus tha ki AWS infrastructure ko Terraform ke through kaise design aur manage kiya jata hai.

Subnets and Their Dependencies

AWS me subnet ek IP address range hota hai jo VPC ke andar hota hai.

Private subnet wo hota hai jise directly internet se access nahi kiya ja sakta. Ye internet gateway se connected nahi hota.

Public subnet wo hota hai jo internet gateway se connected hota hai. Isme launch ki gayi resources internet se accessible hoti hain.

Terraform me dependencies automatically samajh li jaati hain.
Agar ek resource dusre resource ko reference karta hai, to Terraform khud decide karta hai ki pehle kya create hoga aur baad me kya.

VPC and Network Configuration

VPC ek virtual network hota hai jo AWS account ke liye dedicated hota hai.
Ye completely isolated hota hai aur iske andar hum apna network design karte hain.

CIDR block define karta hai ki VPC ka IP range kya hoga aur kitne IP addresses available honge.

Routing tables ye decide karti hain ki traffic kahan jayega.
Traffic destination IP ke basis par route hota hai.

Terraform Basics
State Management

Terraform ek state file maintain karta hai jisme infrastructure ki current condition store hoti hai.
Is file ka naam terraform tfstate hota hai.

Jab ek se zyada log same infrastructure par kaam karte hain, to local state risky ho jaata hai.
Isliye state ko S3 me store karna aur DynamoDB ke through lock karna best practice hoti hai.

Terraform File Structure

Main tf file generally core resources define karti hai.

Network tf file me VPC, subnet aur internet gateway jaise resources hote hain.

Compute tf file me EC2 instances aur security groups define hote hain.

Is tarah files ko separate rakhne se project organized rehta hai.

Types of IP Addresses in AWS

Private IP AWS resources ko VPC ke andar milta hai.
Ye sirf internal communication ke liye hota hai.

Public IP wo hota hai jo internet se access allow karta hai.

Elastic IP ek fixed public IP hota hai jo AWS account ke saath associated hota hai.
Isse instance change hone par bhi IP same rakha ja sakta hai.

Launching EC2 Instances

EC2 instance create karne ke liye AMI zaroori hoti hai.
AMI operating system aur base software provide karti hai.

AWS multiple AMIs deta hai jaise Linux aur Windows.

AMI ke bina EC2 launch nahi ho sakta.

Variable Management in Terraform

Terraform me variables ka use configuration ko flexible banane ke liye hota hai.

Input variables user se values lene ke liye hote hain.

Output variables important information ko display karne ke liye use hote hain jaise IP address.

Local variables sirf ek file ke andar limited hote hain aur readability improve karte hain.

Overall Understanding

Terraform ke through AWS infrastructure ko code ke form me define kiya ja sakta hai.

Dependencies automatically handle hoti hain.