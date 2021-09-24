# Creation of a Private Blockchain
Proof of Authority Development Chain

1. First I navigated to the Blockchain Tools Folder where my Ethereum Tools are saved on my desktop.  Then I created my first node name “homeworknode1” using the code below.  
./geth –datadir homeworknode1 account new
Public address of the key:   0x1E389AD5026d18F755E20997940AF6A772bBbedf
Path of the secret key file: homeworknode1\keystore\UTC--2021-09-11T15-11-29.331442100Z--1e389ad5026d18f755e20997940af6a772bbbedf

![image](https://user-images.githubusercontent.com/80648280/134603421-f6c53987-dfb5-4940-a9c8-98f36958a6c1.png)

2.  Next I set up my next node using the code with the name “two” and making note of the public key to use later. 
./geth –datadir homeworknode2 account new

Public address of the key:   0xF6Aafd36c2058Ec01Bb963B1E59b9a9084BEa7E8
Path of the secret key file: homeworknode2\keystore\UTC--2021-09-11T15-25-48.501995900Z--f6aafd36c2058ec01bb963b1e59b9a9084bea7e8

![image](https://user-images.githubusercontent.com/80648280/134603494-f5b114f9-2c80-45d2-a7db-0c0aca815670.png)

3.  Next initiate puppeth with the command below 
./puppeth
4.  Next create a network name “Paul”.  I then went through the prompts to configure and create a new genesis from scratch.  Based on the instructions I used selected proof of assignment for this activity.  With just 2 nodes I selected a short time of just 4 seconds. 

![image](https://user-images.githubusercontent.com/80648280/134603529-194ff94f-0a8b-4767-ab96-46ce10e62768.png)

5.  Next I attached the public address for my 2 nodes “homeworknode1” and “homeworknode2” in order to seal them.  They were also the accounts selected to be prefunded.  Per the instructions I did not prefund with 1 wei.  I selected the network ID to be 369.  Following that I exported the genesis configurations so I could use the three.json later. 

![image](https://user-images.githubusercontent.com/80648280/134603587-daeb0486-4358-4f77-a5fb-a213b254b7e9.png)

6.  At this time I initiated the nodes by opening 2 gitbash terminals and ran the following commands 1 in each window. This command was run in first gitbash terminal for the first node “homeworknode1”
./geth –datadir homeworknode1 init paul.json

![image](https://user-images.githubusercontent.com/80648280/134603638-eb421a18-5715-4c24-8c97-ff198c757f59.png)

7.  This command was run in second gitbash terminal for the second node “homeworknode2”
./geth –datadir homeworknode2 init paul.json

![image](https://user-images.githubusercontent.com/80648280/134603709-8f51eca2-72f0-4222-b5f7-3e37c69f9867.png)

8.  At this time start “homeworknode1” using the following code:
./geth --datadir homeworknode1 --unlock "0x1E389AD5026d18F755E20997940AF6A772bBbedf" --mine --rpc --allow-insecure-unlock

9. The code below was used to mine and create an environment where the 2 nodes “homeworknode1” and “homeworknode2” could find each other, use the following code:
./geth --datadir homeworknode2 --unlock "0xF6Aafd36c2058Ec01Bb963B1E59b9a9084BEa7E8" --mine --port 30304 --bootnodes "enode://db40977555952e4f2d4ff55539c2cc49e7631a08310e3f74844154e77da760a21f64d2941ebfb0581de55c82d8a454c50b1aa709fc9b993befaa568c3df9f77d@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock

![image](https://user-images.githubusercontent.com/80648280/134603779-b3752279-7676-4e02-b4f3-4f0a67ec22c9.png)

![image](https://user-images.githubusercontent.com/80648280/134603798-9cf81713-9a06-44da-a292-6ccddf24c083.png)

