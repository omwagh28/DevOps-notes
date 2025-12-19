GitHub Actions
Revision Notes
What is GitHub Actions

GitHub Actions GitHub ka built-in automation tool hai.
Iska use code ko automatically build, test aur deploy karne ke liye hota hai.

Simple words me
Jab bhi code repository me push hota hai
GitHub Actions automatically kuch kaam kar deta hai
Jaise build run karna, tests chalana ya application deploy karna

Isse CI CD process easy ho jata hai.

Why GitHub Actions is Used

Manual build aur testing time consuming hoti hai.
GitHub Actions ye kaam automatically karta hai.

Iske fayde
Automation milta hai
Human errors kam hote hain
Fast feedback milta hai
Team collaboration better hota hai

Key Features

GitHub Actions ke through
Automatic workflows bana sakte hain
Custom workflows likh sakte hain
Linux, Windows aur Mac par jobs run kar sakte hain

Mostly Linux environment use hota hai kyunki wo fast aur compatible hota hai.

Setting Up a Git Repository

GitHub Actions use karne se pehle repository ready honi chahiye.

Basic steps
GitHub par nayi repository create karte hain
Repository ko local system par clone karte hain
Apna source code repository me rakhte hain

Jaise Java project ke liye pom xml file add hoti hai.

Introduction to GitHub Actions Workflow

GitHub Actions workflow ek YAML file hoti hai.
Ye file repository ke andar ek special folder me hoti hai.

Workflow file batati hai
Kab workflow run hoga
Kaunsa kaam karega
Kaunsa environment use hoga

Workflow Basic Structure

Workflow me generally ye cheeze hoti hain

Workflow ka naam
Trigger event jaise code push
Jobs
Steps

Job batata hai kaunsa kaam karna hai
Steps batate hain ek ek karke kya run hoga

Trigger Events

Workflow tab start hota hai jab koi event hota hai.
Sabse common event hota hai code push.

Example
Jaise hi main branch me code push hota hai
Workflow automatically run ho jata hai.

Jobs and Runs On

Har job kisi environment par run hoti hai.
Environment ho sakta hai Linux, Windows ya Mac.

Most cases me Ubuntu use hota hai kyunki fast aur free hai.

Actions

Actions ready made steps hote hain jo common kaam karte hain.
Jaise
Code checkout karna
Java setup karna
Environment configure karna

Ye actions GitHub marketplace me available hote hain.

Using Maven with GitHub Actions

Java projects ke liye Maven commonly use hota hai.

Workflow me
Java version set kiya jata hai
Maven command run hoti hai
Code compile hota hai
Tests run hote hain
Final package banta hai

Isse ensure hota hai ki code sahi tarah build ho raha hai.

Why Caching is Important

Maven dependencies baar baar download karna slow hota hai.
Caching se dependencies save ho jaati hain.

Iska benefit
Build fast hota hai
Time aur resources bachte hain

Managing Workflow Cost

GitHub Actions limited free minutes deta hai.
Agar workflows zyada heavy ho jaayein to cost badh sakti hai.

Cost control ke liye
Unnecessary workflows avoid karte hain
Jobs ko short rakhte hain
Unused workflows disable karte hain

Debugging and Troubleshooting

Kabhi kabhi workflow fail ho jata hai.
Iske liye logs check karna zaroori hota hai.

Common problems
YAML syntax galat hona
Wrong Java version select karna
Permission related issues

Logs se error ka reason easily samajh aa jata hai.

Important Points for Exam

GitHub Actions CI CD tool hai
Workflow YAML file se define hota hai
Triggers decide karte hain kab workflow chalega
Jobs environment par run hoti hain
Actions reusable steps hote hain