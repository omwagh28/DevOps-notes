Pod
Basic Workload Unit in Kubernetes

Pod Kubernetes ka sabse chhota unit hota hai jisme application run hoti hai.
Ek Pod ke andar usually ek hi container hota hai, lekin multiple containers bhi ho sakte hain.

Pod ki main features
Pod ek ya zyada containers run karta hai
Sab containers same network aur storage share karte hain
Pod ka ek hi IP address hota hai

Pod self healing nahi hota.
Agar Pod crash ho jaye ya node down ho jaye, to Pod automatically wapas nahi aata.

Isliye production me normally direct Pod use nahi kiya jata.

Pods Are Ephemeral

Pods temporary nature ke hote hain.
Agar Pod delete ho gaya ya crash ho gaya, to wo permanently chala jata hai.

Kubernetes standalone Pod ko khud se recreate nahi karta.
Isi problem ko solve karne ke liye ReplicaSet use hota hai.

ReplicaSet
Pod Count Maintain Karne Wala Controller

ReplicaSet ka kaam hota hai ye ensure karna ki hamesha fixed number me Pods chal rahe ho.

Agar aap bolo ki mujhe teen Pods chahiye
Aur ek Pod mar gaya
To ReplicaSet turant naya Pod bana deta hai

Agar zyada Pods ho jaayein
To ReplicaSet extra Pods delete kar deta hai

ReplicaSet sirf Pod count maintain karta hai.
Ye rolling updates ya version rollback handle nahi karta.

Isliye engineers usually ReplicaSet directly create nahi karte.

Deployment
Kubernetes ka Master Controller

Deployment Kubernetes me stateless applications manage karne ka best aur recommended way hai.

Deployment kya karta hai
ReplicaSet create aur manage karta hai
Rolling updates handle karta hai
Old version par rollback allow karta hai
Updates ko pause aur resume kar sakta hai
Self healing provide karta hai

Deployment internally ReplicaSet ka use karta hai, lekin user ko direct ReplicaSet manage karne ki zarurat nahi hoti.

Simple Deployment Ka Matlab

Agar aap Deployment me likhte ho
replicas three

To Deployment ensure karta hai
Hamesha teen Pods running rahein

Jab aap image update karte ho
To ek naya ReplicaSet create hota hai
Old ReplicaSet ko dheere dheere scale down kiya jata hai
Purana ReplicaSet rollback ke liye preserved rehta hai

Deployment Workflow
Jab aap Deployment Apply Karte Ho

Step one
kubectl ke through Deployment submit hota hai

Step two
API server YAML ko validate karta hai aur save karta hai

Step three
Deployment controller check karta hai ki existing ReplicaSet hai ya nahi

Step four
Agar naya version hai to naya ReplicaSet create hota hai

Step five
ReplicaSet required number me Pods create karta hai

Step six
Scheduler Pods ko nodes par assign karta hai

Step seven
Kubelet containers start karta hai

User ko manually kuch handle nahi karna padta.

Deployment Rollout Strategy

Kubernetes do rollout strategies support karta hai.

Rolling update
Old Pods dheere dheere replace hote hain
Application downtime nahi hota
Ye default strategy hoti hai

Recreate
Pehle saare old Pods delete hote hain
Phir naye Pods create hote hain
Ye stateful ya special applications ke liye use hoti hai

Updating a Deployment

Jab aap application ka image update karte ho
To Kubernetes automatically
Naya ReplicaSet create karta hai
Old ReplicaSet ko scale down karta hai
Naye Pods gradually start karta hai

Agar kuch galat ho jaye
To aap easily previous version par rollback kar sakte ho.

Scaling a Deployment

Agar traffic badh jaye
To replicas count badha sakte ho

Deployment update hota hai
ReplicaSet extra Pods create karta hai
Scheduler unhe nodes par distribute karta hai

Deleting a Deployment

Jab Deployment delete hota hai
To uske saath ReplicaSet delete hota hai
Aur uske saare Pods bhi delete ho jaate hain