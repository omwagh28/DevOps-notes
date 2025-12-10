Revision Notes
1. Kubernetes Basics (Quick Recap)
API Server

API server Kubernetes ka central point hota hai.
Saari requests yahin aati hain, chahe wo Pod create karni ho, Service banana ho ya scaling karni ho.
Cluster ka poora data etcd me store hota hai, aur API server us data ke saath kaam karta hai.

Controllers

Controllers ka kaam hota hai ye check karna ki desired state aur actual state same hai ya nahi.
Agar mismatch hota hai to controller usse fix karta hai.
Jaise scheduler Pods ko nodes par assign karta hai aur kubelet un Pods ko run karwata hai.

Pods

Pod Kubernetes ka sabse chhota unit hota hai.
Ek Pod me ek ya zyada containers ho sakte hain.
Pod ke saare containers same network aur same storage share karte hain.

Nodes

Nodes wo machines hoti hain jahan Pods actually run hote hain.
Har node par kubelet, kube proxy aur container runtime chalta hai.

2. Kubernetes Networking Model (Core Rules)

Kubernetes networking kuch basic rules follow karta hai.

Har Pod bina NAT ke kisi bhi doosre Pod se baat kar sakta hai.
Har Node bina NAT ke kisi bhi Pod se baat kar sakta hai.
Pod ka IP address andar aur bahar same hota hai.

Isi wajah se Kubernetes ko networking ke kai levels handle karne padte hain.

3. Container to Container Networking (Inside a Pod)

Ek Pod ke andar saare containers same network namespace use karte hain.
Iska matlab hai
Sab containers same IP share karte hain
Same ports use karte hain
Aur localhost ke through ek dusre se baat kar sakte hain

Sidecar pattern isi concept par based hota hai.

4. Pod to Pod Networking

Har Pod ka apna alag network environment hota hai.
Isliye Kubernetes Pods ko aapas me connect karta hai.

Same Node par Pods

Agar do Pods same node par hain
To traffic virtual network ke through directly flow karta hai
Pods easily ek dusre se communicate kar pate hain.

Different Nodes par Pods

Agar Pods alag alag nodes par hain
To traffic node ke network ke through route hota hai
Network ko pata hota hai ki kaunsa Pod kis node par hai

Ye kaam CNI plugin handle karta hai.

CNI Plugins

CNI plugins Kubernetes networking ka main part hote hain.
Ye Pods ko IP address dete hain aur routing setup karte hain.

Common CNI examples
Calico
Flannel
Weave
AWS VPC CNI

Har CNI ka implementation alag hota hai, lekin goal same hota hai.

5. Pod to Service Networking

Pods permanent nahi hote, unke IP change hote rehte hain.
Service is problem ko solve karti hai.

Service kya karti hai
Ek fixed IP deti hai
Ek DNS name deti hai
Traffic ko multiple Pods me distribute karti hai

Pod Service ke IP ya DNS ko hit karta hai, aur Kubernetes automatically request kisi healthy Pod tak bhej deta hai.

Service Routing

Service ke traffic ko route karne ke liye kube proxy use hota hai.
Ye system ke network rules update karta hai taaki request sahi Pod tak pahuche.

DNS in Kubernetes

Har Service ko ek DNS name milta hai.
CoreDNS cluster ke andar DNS resolve karta hai.
Isse Pods ko IP yaad rakhne ki zarurat nahi hoti.

6. Internet to Service Networking
Outgoing Traffic (Pod to Internet)

Jab Pod internet se baat karta hai
To pehle traffic node ke IP se bahar jata hai
Phir cloud ya network gateway use internet tak bhej deta hai

Ye process automatically hota hai.

Incoming Traffic (Internet to Pods)

Internet se Kubernetes ke andar traffic laane ke do common ways hote hain.

LoadBalancer Service

Cloud environment me use hota hai
Automatically cloud ka load balancer create hota hai
Internet traffic Pods tak pahunchta hai

Ingress Controller

Ye advanced routing ke liye use hota hai.
Host name aur path ke basis par traffic route karta hai.
SSL termination aur rules handle karta hai.

Ingress hamesha Service ke through Pods tak traffic bhejta hai.

7. Kubernetes Networking in Short

Containers inside Pod localhost use karte hain
Pods aapas me directly baat kar sakte hain
Service stable IP aur load balancing provide karti hai
DNS service discovery easy banata hai
Ingress aur LoadBalancer internet traffic handle karte hain