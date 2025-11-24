Kubernetes Introduction
Revision Notes
What is Kubernetes

Kubernetes ek open source platform hai jo containers ko manage karta hai. Jab application ke bahut saare containers hote hain, Kubernetes unko automatically handle karta hai.

Kubernetes ka kaam hota hai
containers deploy karna
unko scale karna
agar koi container fail ho jaye to usse automatically restart karna
containers ke beech networking manage karna
storage manage karna
updates ko gradually rollout karna

Simple words me, Kubernetes infrastructure ko automate karta hai aur ensure karta hai ki application hamesha expected state me rahe.

Kubernetes Architecture Overview

Kubernetes do main parts me divided hota hai
Control Plane
Worker Nodes

Control Plane decision leta hai
Worker Nodes actual application run karte hain

Control Plane Components
kube apiserver

Ye Kubernetes ka main entry point hota hai.
Har kubectl command sabse pehle yahin aati hai.

Iska kaam hota hai
request validate karna
permissions check karna
cluster ki state ko update karna

Ye component stateless hota hai isliye multiple copies run ho sakti hain.

etcd

etcd ek distributed key value store hota hai.
Isme Kubernetes ka pura data store hota hai jaise
cluster configuration
desired state
pod details
node information
secrets

Agar etcd ka data chala jaye to cluster ka data bhi chala jata hai. Isliye etcd backup bahut important hota hai.

kube scheduler

Scheduler decide karta hai ki kaunsa pod kaunsa worker node par run karega.

Decision lene ke time ye cheeze dekhta hai
CPU aur memory availability
node health
existing workload

Scheduler sirf decision leta hai, pod actually run nahi karta.

kube controller manager

Ye ek aisa component hai jo continuously check karta rehta hai ki actual state desired state ke barabar hai ya nahi.

Agar mismatch ho jaye to ye automatically fix karta hai.
Jaise agar pod delete ho jaye to naya pod create kar deta hai.

cloud controller manager

Ye cloud environments me use hota hai.
Iska kaam Kubernetes ko cloud provider ke saath integrate karna hota hai.

Ye load balancer, cloud storage aur networking resources manage karta hai.

Worker Node Components

Worker nodes wo machines hoti hain jahan actual application run hoti hai.

kubelet

Har worker node par kubelet run hota hai.
Ye API server se instructions leta hai aur ensure karta hai ki pods sahi tarike se run ho rahe hain.

Ye containers ko start karta hai
monitor karta hai
fail hone par restart karta hai

kube proxy

kube proxy networking handle karta hai.
Ye ensure karta hai ki service ke through traffic sahi pods tak pahuche.

Agar pods increase ya decrease ho jaayein, kube proxy automatically routing update kar deta hai.

Container Runtime

Kubernetes khud containers run nahi karta.
Ye container runtime ko use karta hai.

Common runtimes hain
containerd
CRI O

Runtime images pull karta hai aur containers start karta hai.

Additional Cluster Services
CNI

CNI networking ke liye responsible hota hai.
Ye har pod ko IP address deta hai aur pod to pod communication possible banata hai.

CSI

CSI storage handle karta hai.
Iske through pods dynamically storage request kar sakte hain jaise disks ya volumes.

How Everything Works Together

Jab hum kubectl apply command chalate hain
request API server ke paas jaati hai
API server desired state ko etcd me store karta hai
scheduler node choose karta hai
kubelet container start karta hai
networking setup hoti hai
controller ensure karta hai ki required pods hamesha running rahein

User ko manually kuch manage nahi karna padta.