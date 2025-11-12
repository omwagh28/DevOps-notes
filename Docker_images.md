Docker Class Revision Notes
Introduction to Docker

Docker ek platform hai jo developers ko applications ko easily deploy, manage aur run karne me help karta hai. Class me Docker ke basics par focus tha jaise images banana, Dockerfile samajhna aur containers ko commands ke through manage karna.

Docker ka main goal ye hai ki application har system par same tarike se run kare.

Docker Images and Containers
Docker Image

Docker image ko hum ek packaged environment bol sakte hain. Isme application ke saath saari required cheeze hoti hain jaise libraries aur dependencies. Image directly run nahi hoti, balki isi se container banta hai.

Simple words me, image ek ready template hota hai jisme application band hoti hai.

Docker Container

Docker container wo actual running environment hota hai jahan image chalti hai. Container thoda virtual machine jaisa hota hai lekin zyada lightweight hota hai kyunki ye host system ka kernel use karta hai. Isi wajah se containers fast aur efficient hote hain.

Basic Docker Commands and Usage
Docker Build

Docker build command ka use Dockerfile se image banane ke liye hota hai. Build ke time image ko naam diya jata hai jise tag kehte hain. Tags hamesha lowercase me likhe jaate hain.

Docker Run

Docker run command image se container start karta hai. Isme options use karke container ko background me chalaya ja sakta hai aur ports ko connect kiya ja sakta hai.

Ye command mostly application ko test aur run karne ke liye use hoti hai.

Dockerfile Essentials

Dockerfile ek file hoti hai jisme instructions likhi hoti hain ki image kaise banegi. Dockerfile ko step by step read karta hai.

FROM command batata hai ki base image kaunsi hogi.
RUN command image banate time commands execute karta hai. Har RUN instruction ek naya layer banata hai.
CMD aur ENTRYPOINT container start hone par kaunsa command chalega ye define karte hain. CMD ko override kiya ja sakta hai, ENTRYPOINT ko nahi.

Advanced Concepts
Multi Stage Builds

Multi stage build ka use image ka size kam karne ke liye hota hai. Isme pehle stage me application build hoti hai aur final stage me sirf required files rakhi jaati hain. Isse final image lightweight ho jati hai.

Copy On Write Mechanism

Copy on Write ka matlab ye hai ki Docker sirf wahi files load karta hai jo actually use hoti hain. Isse memory aur performance better hoti hai.

Performance Optimization
Reducing Layers

Kam layers wali image zyada efficient hoti hai. Isliye unnecessary RUN commands avoid ki jaati hain aur multiple commands ko ek saath likha jata hai.

Base Image Optimization

Base image ka selection bahut important hota hai. Jaise Java application ke liye production me JDK ki jagah JRE use karna better hota hai kyunki JRE ka size chhota hota hai.

Practical Example from Class

Class me Java application ke liye Docker image banayi gayi. Pehle JDK use karke application build ki gayi aur phir final stage me JRE use karke optimized image banayi gayi.

Is example se multi stage build ka practical use samjha.

Tools and Environment

Session me Docker environment setup karna, containers banana aur applications deploy karna sikhaya gaya. Students ko commands khud run karne ko bola gaya taaki real understanding develop