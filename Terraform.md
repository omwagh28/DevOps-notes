Revision Notes on Terraform and Infrastructure as Code
Introduction to Terraform

Terraform ek open source tool hai jiska use cloud infrastructure ko code ke through manage karne ke liye hota hai. Iska matlab ye hai ki servers, networks aur cloud resources manually create karne ke bajay hum unhe code likh kar automate kar sakte hain.

Terraform ka use AWS, Azure aur Google Cloud jaise multiple cloud platforms ke saath kiya ja sakta hai. Is wajah se ye tool flexible aur industry me widely used hai.

Infrastructure as Code Concept

Infrastructure as Code ka matlab hota hai infrastructure ko code ki tarah treat karna.
Jaise hum application code likhte hain, waise hi infrastructure ke liye configuration files likhte hain.

Iske fayde
Infrastructure repeatable hota hai
Manual mistakes kam hoti hain
Same setup har environment me milta hai
Changes easily track kiye ja sakte hain

Terraform Lifecycle Commands

Terraform ke kaam karne ka ek fixed lifecycle hota hai. Mostly chaar commands use hoti hain.

Terraform Init

Terraform init sabse pehla command hota hai.
Ye working directory ko initialize karta hai.

Iska kaam
Required providers download karna
Modules setup karna
Provider versions lock karna

Jab bhi naya Terraform project start karte ho, init command zaroori hota hai.

Terraform Plan

Terraform plan batata hai ki agar hum apply command chalayein to kya changes honge.

Ye command
Current infrastructure ko desired state se compare karta hai
Sirf preview dikhata hai
Koi actual change nahi karta

Isse galat changes hone se pehle hi pata chal jaata hai.

Terraform Apply

Terraform apply actual changes karta hai.
Ye command infrastructure create, update ya modify karta hai.

Apply karne se pehle usually plan dekha jata hai taaki confirm ho sake ki changes sahi hain.

Terraform Destroy

Terraform destroy ka use infrastructure delete karne ke liye hota hai.
Isse Terraform ke through banaya gaya pura setup clean ho jata hai.

Ye command carefully use karni chahiye.

Advantages of Using Terraform

Terraform ke kuch major benefits hain.

Automation ki wajah se infrastructure fast create hota hai
Manual configuration ki need kam ho jaati hai
Consistency maintain hoti hai
Terraform files Git jaise tools me store ho sakti hain

Isse rollback aur auditing easy ho jaati hai.

Supporting Tools and Concepts

Terraform infrastructure create karta hai, lekin software configuration ke liye dusre tools bhi use hote hain.

Configuration Management Tools

Ansible, Puppet aur Chef jaise tools servers ke andar software install aur configure karte hain.
Ye Terraform ke saath milkar kaam kar sakte hain.

Server and Environment Tools

Vagrant aur Docker ka use environments create karne ke liye hota hai.
Docker containers ke through applications ko easily run karne me help karta hai.

Practical Example from Class

Class me Terraform ka use karke EC2 instance create karna dikhaya gaya.

Basic flow
Terraform configuration file likhi jaati hai
Init command se setup hota hai
Plan command se changes dekhe jaate hain
Apply command se EC2 instance create hota hai

Terraform state file infrastructure ki current situation ko track karti hai.

Why Terraform is Important in DevOps

Terraform DevOps ka important part hai kyunki
Infrastructure automation milta hai
Multi cloud support hota hai
Manual errors kam hote hain
Infrastructure easily scale kiya ja sakta hai

Isliye real world projects me Terraform widely use hota hai.