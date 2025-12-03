ReplicaSet
Kubernetes Revision Notes
What is a ReplicaSet

ReplicaSet ek Kubernetes controller hota hai jo ye ensure karta hai ki hamesha fixed number me Pods running rahein.

Agar aap bolo ki mujhe teen Pods chahiye, to ReplicaSet ka kaam hota hai ye check karna ki
actual me teen Pods chal rahe hain ya nahi

Agar kam ho gaye to naye Pods bana deta hai
Agar zyada ho gaye to extra Pods delete kar deta hai
Agar koi Pod fail ho jaye to uska replacement bana deta hai

ReplicaSet khud Pod run nahi karta, wo sirf manage karta hai.

ReplicaSet YAML ka Basic Idea

ReplicaSet ki YAML file me mainly teen important cheeze hoti hain

replicas batata hai kitne Pods chahiye
selector batata hai kaunse Pods is ReplicaSet ke under aayenge
template batata hai Pod ka structure kaisa hoga

Template ke andar container ka image aur configuration hota hai.

ReplicaSet Create Karne Par Kya Hota Hai
Step one

User kubectl command ke through ReplicaSet create karta hai

Step two

API server request ko check karta hai aur ReplicaSet ka data cluster ke store me save karta hai

Step three

ReplicaSet controller notice karta hai ki naya ReplicaSet aaya hai

Wo check karta hai
desired Pods three
current Pods zero

Mismatch hone ki wajah se wo teen naye Pods create karta hai.

Pod Creation ke Baad

Naye Pods create hote hi unki initial state pending hoti hai
Abhi tak kisi node par assign nahi hote

ReplicaSet sirf Pod object create karta hai, node choose nahi karta.

Scheduler ka Role

Scheduler dekhta hai ki kaunse Pods abhi node ke bina hain
Har Pod ke liye best node choose karta hai
Pod ko kisi worker node par assign kar deta hai

Iske baad Pod scheduled state me aa jata hai.

Kubelet ka Role

Har worker node par kubelet chalta hai
Jab kubelet dekhta hai ki koi Pod us node par assign hua hai

Toh wo
image pull karta hai
container start karta hai
Pod ko running state me le aata hai

Phir Pod ka updated status API server ko bhej deta hai.

Continuous Monitoring by ReplicaSet

ReplicaSet hamesha loop me kaam karta rehta hai

Wo bar bar ye check karta hai
kitne Pods chal rahe hain
kitne Pods chahiye

Agar dono equal ho jaate hain to wo kuch nahi karta.

Failure Scenarios
Agar Pod crash ho jaye

ReplicaSet dekhta hai ki running Pods kam ho gaye
Wo turant ek naya Pod create karta hai

Agar Node down ho jaye

Node ke Pods unavailable ho jaate hain
ReplicaSet un Pods ko replace karne ke liye naye Pods create karta hai

Agar aap manually Pod delete kar do

ReplicaSet phir se Pod count check karta hai
Aur missing Pod ko recreate kar deta hai

Agar ReplicaSet Delete Kar Diya Jaye

Jab ReplicaSet delete hota hai
Toh uske under ke saare Pods bhi delete ho jaate hain

ReplicaSet aur Pods ke beech ownership relation hota hai.

ReplicaSet ka Overall Role

ReplicaSet ka kaam sirf ek cheez hai
ensure karna ki required number of Pods hamesha available rahein

Ye cheeze ReplicaSet khud nahi karta
containers run nahi karta
nodes manage nahi karta

Ye kaam doosre components karte hain jaise scheduler aur kubelet.