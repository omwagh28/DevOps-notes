Docker and Containerization
Class Revision Notes
Introduction to Docker and Containers
What is Docker

Docker ek open platform hai jiska use applications ko develop, ship aur run karne ke liye hota hai. Docker ka main idea ye hai ki application aur infrastructure ko alag rakha ja sake. Isse software fast aur easily deliver ho jata hai. Docker ke through hum application ko waise hi manage kar sakte hain jaise hum code ko manage karte hain.

Running Applications in Containers

Container ek tarika hai jisme application ke saath uski saari required cheeze jaise libraries aur dependencies ek saath pack kar di jaati hain. Is wajah se application har jagah same tarike se run hoti hai chahe system ya environment alag ho.

Simple words me, container bolta hai ki agar code yahan chal raha hai to wahan bhi chalega.

Basic Docker Commands
Running a Container

docker run command ka use karke naya container start kiya jata hai.
Example ke liye docker run it ubuntu bash use karne se Ubuntu ka ek container start hota hai aur uska terminal mil jata hai.

Is command ka use mostly testing aur practice ke liye hota hai.

Entering an Existing Container

docker exec command running container ke andar command chalane ke liye use hota hai.
Agar container already chal raha hai aur uske andar terminal chahiye to docker exec use kiya jata hai.

Inspecting Docker Containers

docker ps command running containers ki list dikhata hai.
docker container inspect command container ke detailed information ke liye use hota hai jaise IP address, configuration aur network details.

Working with Docker Images
Creating and Managing Images

Docker images ek base image se banti hain. Pehle container ke andar changes kiye jaate hain aur phir un changes ko save karke naya image banaya jata hai.

docker images command system me available images dikhata hai.
docker commit command container se naya image banane ke liye use hota hai.

Pushing Images to Docker Hub

Docker Hub ek online repository hai jahan images store hoti hain.
docker push command ka use karke image Docker Hub par upload ki jaati hai.

Image ka naam Docker Hub username se start hona zaroori hota hai.

Networking and Container Communication

Kabhi kabhi ek container ko doosre container se baat karni hoti hai. Iske liye container ka IP address jaanna zaroori hota hai.
docker container inspect command se container ka IP mil jata hai.

IP address ke through curl jaise tools ka use karke container se communication ki ja sakti hai.

Dockerfile and Image Layers

Docker images mostly Dockerfile se banayi jaati hain. Dockerfile ek step by step process hota hai jisme har instruction ek naya layer banata hai.

Layers ka concept samajhna important hai kyunki Docker caching isi par depend karti hai. Agar layer change nahi hoti to Docker usse reuse kar leta hai.

Detached and Attached Mode

docker run d command container ko background me chalata hai jise detached mode kehte hain.
Attached mode me container terminal se connected hota hai.

Importance of Layered File System

Docker image layers ka use karta hai. Jab hum changes karke image commit karte hain to ek naya layer add hota hai. Purane layers same rehte hain.

Isse Docker lightweight aur fast ban jata hai.

Docker vs Virtual Machines

Virtual machines ke comparison me Docker zyada efficient hota hai. VM apna full operating system carry karta hai jabki Docker host system ka kernel use karta hai. Is wajah se Docker kam resource consume karta hai.

Architecture Related Issues

Kabhi kabhi architecture mismatch jaise ARM aur AMD ke wajah se issues aate hain. Isliye image banate waqt aur deploy karte waqt same architecture use karna important hota hai.