Revision Notes
What is HPA

Horizontal Pod Autoscaler, ya HPA, Kubernetes ka ek feature hai jo automatically Pods ki number badhata ya ghataata hai.
Ye scaling system ke load ke basis par hoti hai.

Is tutorial me hum CPU based autoscaling samajhte hain.
Agar CPU usage zyada ho jaaye to Pods badh jaate hain.
Agar load kam ho jaaye to Pods kam ho jaate hain.

HPA sirf Pods ki count change karta hai, Pod ke size ko nahi.

Why HPA is Needed

User traffic hamesha same nahi hota.
Kabhi traffic kam hota hai, kabhi achanak zyada ho jata hai.

Agar fixed number ke Pods ho
To high load me application slow ho jaati hai.

HPA automatically ye handle karta hai
High load par Pods badhata hai
Low load par Pods kam karta hai

Isse performance aur cost dono balance rehte hain.

High Level Flow

User traffic aata hai
Service ke through Pods tak pahunchta hai
Pods CPU use karte hain
Metrics Server CPU data collect karta hai
HPA controller decision leta hai
Replica count scale up ya down hota hai

Step 1: Metrics Server
Why Metrics Server is Mandatory

HPA ko real time CPU ya memory data chahiye hota hai.
Ye data Metrics Server provide karta hai.

Agar Metrics Server nahi hoga
To HPA ko CPU usage dikhega hi nahi
Aur scaling kaam nahi karegi

Isliye Metrics Server HPA ke liye compulsory hai.

Metrics Server install hone ke baad
kubectl top nodes aur kubectl top pods kaam karne lagte hain.

Step 2: Deployment Creation
Purpose of Deployment

Deployment ek simple application run karta hai jiska CPU usage increase kiya ja sakta hai.
HPA isi Deployment ke Pods ko scale karta hai.

Deployment me CPU requests define karna bahut important hota hai.

Why CPU Requests Are Important

HPA CPU utilization calculate karta hai is formula se

CPU usage divided by CPU request

Agar CPU request define nahi hai
To HPA ka calculation fail ho jaata hai
Aur scaling nahi hoti

Isliye har HPA setup me CPU request zaroor likhna chahiye.

Step 3: Service Creation

Service ka kaam hota hai Pods ke liye ek stable endpoint dena.
Load generate karne ke liye Service ka use hota hai.

Service ke bina Pods ko directly hit karna reliable nahi hota.

Step 4: Creating the HPA

HPA me hum define karte hain

Kaunsa Deployment scale hoga
Minimum aur maximum Pods kitne ho sakte hain
CPU threshold kya hoga

Is example me
Minimum Pods ek
Maximum Pods das
Target CPU utilization fifty percent

HPA continuously CPU monitor karta rehta hai.

Step 5: Generate Load

Load generate karne ke liye ek simple tool use hota hai jo bar bar service ko hit karta hai.
Isse Pods ka CPU usage badhta hai.

Jaise hi CPU fifty percent cross karta hai
HPA scale up start kar deta hai.

What Happens Internally

CPU usage badhta hai
Metrics Server data report karta hai
HPA controller calculate karta hai
Replica count badh jaata hai
Naye Pods create hote hain

User ko manually kuch karna nahi padta.

Step 6: Monitoring

Scaling observe karne ke liye
Deployment ke replica count ko check kiya jata hai
HPA ka current status dekha jata hai
Events me scaling related messages dikhte hain

Isse confirm hota hai ki HPA kaam kar raha hai.

Step 7: Scale Down

Jab load generator stop kar dete ho
CPU usage kam ho jaata hai

HPA immediately scale down nahi karta
Thoda wait karta hai
Phir dheere dheere Pods kam karta hai

Isse frequent up down se system unstable nahi hota.

Common Problems and Fixes

Agar CPU zero percent dikh raha ho
To Metrics Server missing hota hai

Agar scaling nahi ho rahi
To CPU requests missing hoti hain

Agar HPA Deployment ko target nahi kar raha
To labels ya selector galat hote hain

Key Takeaways

HPA automatic scaling provide karta hai
Metrics Server compulsory hota hai
CPU requests define karna zaroori hai
Scaling gradual aur safe hoti hai
HPA average pod CPU usage par kaam karta hai