Pod Notes
Kubernetes Revision Notes (Student Version)
1. What is a Pod

Pod Kubernetes ka sabse chhota deployable unit hota hai.
Ek Pod me ek ya usse zyada containers ho sakte hain jo hamesha saath me run karte hain.

Pod ke andar ke containers
same network share karte hain
same storage volumes use karte hain
same node par schedule hote hain

Isliye Pod ko containers ka logical group kaha jaata hai.

2. Control Plane and Data Plane Roles
Control Plane ka kaam

Control plane cluster ko manage karta hai aur decisions leta hai.

API Server sabhi requests ka entry point hota hai
etcd cluster ka data store karta hai
Scheduler decide karta hai ki Pod kis node par run hoga
Controller Manager ensure karta hai ki desired state aur actual state same rahe

Data Plane ka kaam

Data plane wo jagah hai jahan actual application run hoti hai.

Kubelet har node par run hota hai aur Pod ko chalata hai
Container runtime containers ko start karta hai
kube proxy networking rules manage karta hai

3. Pod Object Basics

Pod ek Kubernetes API object hota hai jo cluster ke data store me save hota hai.

Pod me mainly ye cheeze hoti hain
metadata jaise name aur namespace
spec jisme containers aur volumes define hote hain
status jisme Pod ka current state hota hai

Scheduler jab tak Pod ko node assign nahi karta, tab tak Pod pending state me hota hai.

4. Pod Creation Flow (Simple Steps)

Pod ka lifecycle normally is tarah hota hai

Step one
User kubectl command ke through Pod create karta hai

Step two
API server request verify karta hai aur Pod ka data store me save karta hai

Step three
Scheduler dekhta hai ki Pod kisi node par assign nahi hai aur best node select karta hai

Step four
Selected node ka kubelet Pod ko notice karta hai

Step five
Kubelet container runtime ko bolta hai ki containers start kare

Step six
Networking aur storage setup hota hai

Step seven
Pod running state me aa jaata hai

User ko manually kuch karna nahi padta, Kubernetes sab handle karta hai.

5. Kubelet ka Role in Pod

Kubelet node ka main agent hota hai.
Ye API server se Pod ka data leta hai aur ensure karta hai ki Pod sahi se run ho.

Kubelet ye kaam karta hai
containers start aur restart karta hai
Pod ka status update karta hai
health check karta hai

6. Pod Networking (Basic Idea)

Har Pod ko apna IP address milta hai.
Pod ke andar ke containers localhost ke through baat kar sakte hain.

CNI plugin Pod ko IP deta hai aur network setup karta hai.
kube proxy ensure karta hai ki services ke through traffic sahi Pod tak pahuche.

7. Pod Storage (Volumes)

Pod ke andar data temporary hota hai.
Agar Pod delete ho jaye to data chala jaata hai.

Isliye volumes use kiye jaate hain taaki data safe rahe.
Volumes Pod ke saath attach hote hain aur container ke andar mount hote hain.

8. Pod States

Pod kuch common states me hota hai
Pending jab Pod node ka wait kar raha ho
Running jab containers chal rahe ho
Succeeded jab kaam successfully complete ho
Failed jab error aa jaye

Conditions batati hain ki Pod ready hai ya nahi.

9. Pod Health Checks

Readiness check decide karta hai ki Pod traffic lene ke liye ready hai ya nahi.
Liveness check batata hai ki container healthy hai ya restart hona chahiye.

Ye checks application reliability ke liye important hote hain.

10. Pod Deletion and Restart

Jab Pod delete hota hai to Kubernetes pehle container ko safely stop karta hai.
Agar Pod kisi controller ke under ho jaise Deployment, to naya Pod automatically create ho jaata hai.

11. Best Practices (Exam Important)

Direct Pod create karne ke bajay Deployments use karo
Resource limits define karo
Health checks use karo
Volumes ka use karo jab data important ho