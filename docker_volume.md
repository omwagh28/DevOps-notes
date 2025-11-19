Docker Networking
Revision Notes
Overview

Docker networking ka kaam containers ko aapas me aur external world se connect karna hota hai. Jab multiple containers ek application ka part hote hain, tab unke beech proper communication zaroori hota hai. Docker networking is communication ko easy aur managed banata hai.

IP Address in Docker

IP address ek unique number hota hai jo network me kisi device ya container ko identify karta hai. Docker me har container ko apna IP address milta hai taaki wo dusre containers ya services se baat kar sake.

Simple words me, bina IP ke container network me pehchana nahi ja sakta.

Subnetting Concept

Subnetting ka matlab hota hai ek bade network ko chhote networks me divide karna. Isse network management easy ho jata hai. Docker networking me CIDR notation use hota hai jisme bataya jata hai kitne IP addresses available honge.

Example ke liye agar network ka prefix chhota hota hai to zyada IP addresses milte hain.

Network ID and Broadcast ID

Har subnet me do special IP addresses hote hain.
Network ID network ko represent karta hai aur kisi container ko assign nahi hota.
Broadcast ID sabse last address hota hai jo network ke sab devices ko ek saath data bhejne ke kaam aata hai.

Docker Zero Bridge

Docker install karne ke baad system me ek default bridge network create hota hai jise docker zero bridge kehte hain. Ye ek virtual switch ki tarah kaam karta hai.

Har container ke paas ek network interface hota hai jo docker zero bridge se connected hota hai. Is connection ke through containers aapas me communicate kar paate hain.

Default Docker Network

By default, jab bhi container run hota hai, wo docker zero network ke andar hi start hota hai. Is network ke andar containers IP address ke through ek dusre se baat kar sakte hain.

Custom Bridge Network

Docker me hum apna custom bridge network bhi bana sakte hain. Custom network use karne ka fayda ye hota hai ki hum subnet, gateway aur IP range ko control kar sakte hain.

Isse applications ko alag alag networks me isolate karna easy ho jata hai.

Container Communication

Jo containers same network me hote hain, wo easily ek dusre se communicate kar sakte hain. Docker automatically virtual bridges aur routes manage karta hai, isliye manually networking setup karne ki zaroorat kam hoti hai.

Practice Scenario

Class me example diya gaya tha jahan ek bade network ko chhote networks me divide kiya gaya. Jaise engineering, HR aur reception ke liye alag alag subnet banaye gaye. Isse har department ka traffic alag manage kiya ja sakta hai.

Troubleshooting Docker Networking

Agar networking issue aaye to container ke network details check karna zaroori hota hai. Docker inspect jaise tools se container ka IP address aur network configuration dekhi ja sakti hai.