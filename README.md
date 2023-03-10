![bitburner-title](https://user-images.githubusercontent.com/61264144/211128393-33965112-eefd-4c48-83b8-056762ca86a6.png)

Bitburner is a javascript based programming game that focuses on incrementation and automation. In this cyberpunk city you play as a hacker. Your goal is to steal as much money as possible from the various servers of the world. This is done by gaining root access to servers and running viruses on them, which helps you hack more servers, and so on.

There are built in methods to help you write your scripts. Each method costs an amount of memory to run and each server has a max amount of memory on it. 'Scan' is a method, which takes one parameter - a server's name - and returns an array filled with all servers directly connected to the passed argument. With scan you can build a map of the city network and start cracking servers. There are over 100 methods that can help you fine tune your scripts.

These are my scripts I've written so far. The main.js module finds all the servers on the network and cracks each one that it is able to crack. The grow.js, weaken.js, and hack.js scripts are then loaded on each cracked server. A target is then chosen to be hacked by all vulerable servers on the network, as well the purchased servers (from the purchased-servers.js script). Variables to consider when picking a target are max money and hacking level required, among others.

The script then calculates how many threads are needed for each attack, and how many threads are available on which servers. A specific number of servers are then chosen to run each script the calculated amount of times, at a specified time. Each attack takes a different amount of time to complete after execution based on the target server's stats. After all scripts are executed the process is started over again.

I'm currently working on timing the attacks better and recursively calling the attack function with predictions of future variables and arguments. Theoretically you should be able to get the attacks to trigger within a very small window and have each cycle trigger in sequence, infinitly - only limited by available memory. On some servers weakening can take 1 hour, growth around 50 mins and hacking 35 mins. Getting all attacks to trigger in the right order with the most efficient amount of threads is quite the challenge.

![bitburner-ss](https://user-images.githubusercontent.com/61264144/211128262-1568946b-c6bb-4d15-bde0-000079cb39d1.png)
