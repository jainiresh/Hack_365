# TOPIC
My FIRST bash Scripting

# OVERVIEW
A small talk about myself, and my present progress.

# TALK
Its been around 2 months since i started hacking.
I started to learn ethical hacking @ bug bounty, at July __,2022.

When i first started in this field, i was quite convinced that it is not an easy job to get a bounty nor finding a bug.
I was unclear about the working of an website, i was good at coding, but soon i realised coding and programming 
alone could not help you to find a vulnerability in a wesite.

If you are a beginner, reading this, and you are a person who is still doubtful whether to start a career on ethical hacking,
I would say go for it.
I could do it, y cant you !

The progress is abrupt, you would never know or realise that you are improving, but when u look back, you would have
been in a far better position compared to yourself a week back.

A lot of self learning, and a lot of help from resources shared by my fellow hackers helped me to develop.
Im yet a noob, i havent still recieved a bounty, and i have submitted around 15 reports but none got me a bounty.

Yet, here i am ! Consitency in which i believe !

Happy Hacking !

# BASH_SCRIPTING

A lot of reconnaissance does the trick of finding juicy things.
Proper recon, could aid you with chaining bugs together to bring up even an Account takeover.

There are a lot of tools for a lot of things like
- ip lookup
- reverse ip lookup
- subdomain enumeration
- active subdomains checker
- status checking for urls
- dns 
- cname 
and lots more, but this is a lot interesting on the beginning stage, but as days goes by as you develop, you start feeling
bored and hectic to do all these enumerations one by one , storing them and copy pasting them.

There fore i started learning Bash Scripting side by side.

It is a type of scripting language for Linux Command LIne, which could execute a series of commands.

# MY FIRST BASH SCRIPT

For subdomain enumeration => subfinder
For status checker => httpx
I know this script is just a combination of 2 or more tools, but i felt like posting it as this was my first script in ethical hacking !

# SCRIPT
```
#! /bin/bash

DIR="$HOME/../home/jai/Documents/exploits"

read -p "Enter your domain : " domain

echo "Starting Magma scan on the domain : $domain "

if [ -d "$DIR/$domain" ]; then
        DIR="$DIR/$domain"
        echo "Already present, so travelling there !"
else
        mkdir "$DIR/$domain"
        DIR="$DIR/$domain"
        echo "Created a new dir, and travelling there !"
fi

subfinder -d "$domain" -silent -o "$DIR/subs.txt"  

echo "\n"
echo "----------------------------------------------------------------------------------------------------------"
echo "Subdomain enumerated and created subs.txt file"
echo "----------------------------------------------------------------------------------------------------------"
echo "\n"
httpx -sc -list "$DIR/subs.txt" -silent | sed -r "s/\x1B\[([0-9]{1,2}(;[0-9]{1,2})?)?[m|K]//g" | tee "$DIR/subsStatus.txt"
echo "\n"
echo "\n"
echo "----------------------------------------------------------------------------------------------------------"
echo "Subdomains status done and created subsStatus.txt file"
echo "----------------------------------------------------------------------------------------------------------"

```
