Kubernetes Services
Revision Notes
Why Services Are Needed

Kubernetes me Pods permanent nahi hote.
Pods restart hote hain
Pods recreate hote hain
Pods scale up aur down hote rehte hain

Is wajah se Pod ka IP change hota rehta hai.
Agar hum direct Pod ke IP se communicate karein, to application break ho jaati hai.

Isi problem ko solve karne ke liye Service use hota hai.

What is a Kubernetes Service

Service ek abstraction hai jo Pods ke upar ek stable layer provide karta hai.

Service ye provide karta hai
Ek fixed IP address
Ek fixed DNS name
Multiple Pods ke beech load balancing
Reliable communication

Client ko ye farak nahi padta ki backend me kitne Pods hain ya kaunse Pod down ho gaye.

How a Service Works (Simple Flow)

Sabse pehle Service create hoti hai jisme Pod selector hota hai.
Selector batata hai ki kaunse Pods is Service ke backend hain.

Service ko ek stable IP milta hai.
kube proxy node level par networking rules create karta hai.

Jab koi Pod ya user Service ke IP ya DNS ko hit karta hai
Traffic automatically kisi healthy Pod tak pahunch jaata hai.

Types of Kubernetes Services

Kubernetes me mainly teen service types use hote hain.

ClusterIP Service

Ye default aur sabse common service type hai.
ClusterIP sirf cluster ke andar accessible hoti hai.

Use cases
Microservices ke beech communication
Frontend se backend call
Backend se database call
Internal APIs

Is service ko internet se access nahi kiya ja sakta.

Cluster ke andar service ko DNS name se access kiya jata hai.

NodePort Service

NodePort service har worker node par ek fixed port open kar deti hai.

Traffic flow aisa hota hai
External user node ke IP aur port ko hit karta hai
Traffic service tak jaata hai
Service traffic Pods me distribute kar deti hai

NodePort mostly testing aur non cloud environments me use hota hai.

Limitations
Har node par service expose hoti hai
High port range use hoti hai
Security ke liye ideal nahi hoti
Production ke liye recommended nahi hoti

LoadBalancer Service

LoadBalancer service cloud environments me use hoti hai.
Ye automatically cloud provider ka load balancer create karti hai.

Traffic flow
Internet se traffic cloud load balancer par aata hai
Wahan se Kubernetes service ko jata hai
Service traffic Pods me distribute kar deti hai

User ko directly ek public IP milta hai.

Ye production me external access ke liye best option hai.

Headless Services

Headless service me Service ka IP assign nahi hota.
Iska use mainly StatefulSets aur databases ke saath hota hai.

Isme DNS directly Pods ke IPs return karta hai.
Load balancing DNS level par hoti hai.

Multi Port Services

Ek hi Service multiple ports expose kar sakti hai.
Ye useful hota hai jab application alag alag ports par kaam karti ho.

Example
HTTP ke liye ek port
HTTPS ke liye doosra port

Service DNS

Har Service ko automatically ek DNS name milta hai.
Format hota hai
service name
namespace
svc
cluster local

Is DNS ke through Pods easily ek dusre se baat kar sakte hain.

ExternalName Service

ExternalName service ka use tab hota hai jab Kubernetes ke bahar kisi service ko access karna ho.
Is case me Service sirf DNS mapping karti hai.

Example
Kubernetes ke andar se external database ko access karna.

Which Service Type to Use

Agar service sirf cluster ke andar chahiye
ClusterIP use karo

Agar local ya testing ke liye bahar se access chahiye
NodePort use karo

Agar production me internet se access chahiye
LoadBalancer use karo

Agar database ya StatefulSet hai
Headless service use karo