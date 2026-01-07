Class Revision Notes on CI CD with Kubernetes
Introduction

Is class me humne applications ko Kubernetes cluster me deploy karna seekha. Iske saath saath Continuous Integration aur Continuous Deployment ke concepts cover kiye gaye, jo aaj ke DevOps environment ka core part hain.

Continuous Integration and Continuous Deployment
Continuous Integration

Continuous Integration ka matlab hota hai ki developers apna code frequently main codebase me merge karte hain.
Is process me automated build aur testing hoti hai taaki ye ensure ho sake ki code hamesha deployable state me rahe.

CI ka main focus hota hai
Frequent code merge
Automated testing
Early bug detection

Continuous Deployment

Continuous Deployment CI ka next step hota hai.
Isme tested code automatically production ya target environment me deploy ho jata hai.

CD ka focus hota hai
Automation of deployment
Infrastructure configuration
Downtime ke bina application updates

Setting Up Kubernetes Environment
Creating a Virtual Machine

Kubernetes ke liye kam se kam ek node ka cluster chahiye hota hai.
Ye VirtualBox aur Vagrant jaise tools ke through easily setup kiya ja sakta hai.

Vagrant scripts ka use karke VM creation automate ho jata hai.
Isme mostly sirf script copy paste karke environment ready ho jata hai.

Deploying Kubernetes

Kubernetes pehle se installed VM use karna time save karta hai.
Jaise cloud platforms par aise images available hote hain jisme Kubernetes already installed hota hai.

Isse manual installation ka effort kam ho jata hai.

GitHub Actions and Custom Runners
GitHub Actions

GitHub Actions ek automation tool hai jo directly GitHub repository ke saath integrate hota hai.
Iska use build, test aur deployment pipelines banane ke liye hota hai.

Custom Runners

Normally GitHub apne runners provide karta hai.
Lekin hum apna khud ka system bhi runner ke roop me configure kar sakte hain, jise self hosted runner kehte hain.

Linux machines generally prefer ki jaati hain.
Runner ko GitHub ke saath register karna hota hai aur phir workflows us machine par run hote hain.

Runner Configuration

Runner setup ke liye configuration script use hoti hai.
Isme runner ka naam, labels aur security settings define ki jaati hain.

Proper configuration se runner safely aur efficiently kaam karta hai.

Project Demonstration and Teamwork

Class me teams banayi jaati hain aur har team ek project present karti hai.
Project ka main focus CI CD pipeline implement karna hota hai.

Team me kaam distributed hota hai
Lekin har student ko apna individual contribution samajhna zaroori hota hai
Presentation ke time questions individual se pooche jaate hain.

Testing and Quality Assurance

Testing CI CD ka important part hai.
Different testing stages use ki jaati hain jaise
System integration testing
Performance testing
Security testing

Testing ko automate kiya jata hai taaki human errors kam ho aur coverage zyada ho.

Practical Considerations

Well structured environments me CI aur CD alag pipelines hote hain.
Isse responsibilities clear rehti hain aur debugging easy hoti hai.

Har application ke liye pipeline configuration alag ho sakti hai
Kyuki infrastructure aur requirements different hoti hain.