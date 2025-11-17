Docker Volumes
Revision Notes
Introduction to Docker Volumes

Docker volumes ka use containers ke data ko permanently store karne ke liye hota hai. Normally container delete hone par uske andar ka data bhi delete ho jata hai, lekin volume use karne se data safe rehta hai. Volume container ke lifecycle se independent hota hai, isliye container remove hone ke baad bhi data available rehta hai.

Volumes ka ek aur fayda ye hai ki same data ko multiple containers ke saath share kiya ja sakta hai.

Importance of Volumes

Kuch applications jaise databases me data loss allowed nahi hota. Agar container crash ho jaye ya dobara create ho, tab bhi data rehna chahiye. Docker volumes is problem ko solve karte hain. Volumes application aur storage ko alag rakhte hain, jisse management easy ho jata hai.

Ephemeral Nature of Containers

Containers temporary hote hain. Ye task complete hone ke baad stop ho sakte hain ya delete ho sakte hain. Agar volume use nahi kiya gaya ho, to container ke andar ka data lost ho jata hai. Isi wajah se important data ke liye volumes ka use zaroori hota hai.

Writable Layer in Containers

Har container ka apna ek writable layer hota hai jahan file system changes store hote hain. Jab tak container exist karta hai, tab tak ye data available rehta hai. Lekin agar container remove ho jaye, to writable layer ke saath data bhi chala jata hai. Volume is writable layer se bahar data store karta hai.

Types of Docker Volumes
Named Volumes

Named volumes Docker ke through manage kiye jaate hain aur inka ek naam hota hai. Ye volumes easily reuse kiye ja sakte hain aur generally host system par ek fixed location par store hote hain. Ye most commonly used volume type hai.

Anonymous Volumes

Anonymous volumes ka naam user define nahi karta. Docker automatically ye volume create karta hai jab storage chahiye hoti hai. Ye temporary hote hain aur reuse ke liye prefer nahi kiye jaate.

Bind Mounts

Bind mounts directly host machine ke file system ke saath connect hote hain. Isme user ko exact host path specify karna hota hai. Ye zyada flexible hote hain lekin permissions aur file management ki responsibility user par hoti hai.

Use Cases and Practical Applications
Database Persistence

Database container ke case me volume use karna bahut important hota hai. Agar container crash ho jaye ya delete ho jaye, tab bhi database ka data volume me safe rehta hai.

Shared Storage Among Containers

Kabhi kabhi multiple containers ko same data access karna hota hai. Volume ke through same data ko multiple containers ke saath share kiya ja sakta hai bina data duplicate kiye.

Volume Management
Creating a Volume

Docker volume manually create kiya ja sakta hai. Ye volume Docker ke control me hota hai aur future containers ke liye reuse ho sakta hai.

Inspecting a Volume

Volume inspect karne se uska storage location aur details mil jaati hain. Ye debugging aur management ke liye useful hota hai.

Attaching a Volume to a Container

Container start karte waqt volume attach kiya ja sakta hai. Isse container volume ke andar data read aur write kar sakta hai.

Read Only Volumes

Kuch cases me container ko sirf data read karna hota hai, write nahi. Aise cases me volume ko read only mode me mount kiya jaata hai taaki data safe rahe.