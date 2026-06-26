
When it comes to vulnerabilities, especially on linux, i tend to see the same reaction: Blind Panic, especially among new users. 

This tends to stem from a lack of understanding about what is actually going on. New users tend to not stay up to date with official news channels for everything they use, which means they tend to become aware of new vulnerabilities not through something like a news post but primarily through social media, which means primarily small, sensational snippets that only tell you there is a problem, but give you no info on what the problem is.


In this guide, we'll go over what you as a non-technical user can do to better understand what's going on when a vulnerability is discovered. 


# Step 0: becoming aware of the vulnerability

this is part of where "security isn't something you do once, it has to live rent-free in the back of your head" comes from. You simply cannot respond to a vulnerability if you do not know it exists. 

At least for the bigger pieces of software, make sure to follow at least some good news sources. It's fine if this is a collection of youtube channels you follow or an IRC feed, all that matters at this step is that when a relevant vulnerability occurs, you end up being made aware of it. 


# Step 1: understanding the attack vector

the attack vector is *how* the vulnerability is exploited. Read up on the basics of it to understand if it applies to you. If a vulnerability for example requires physical access to the device, then your home PC is safe. 

this is also where you figure out what you can do immediately to mitigate the attack vector. If the attack vector utilizes an open SSH port, block it off with your firewall. If the attack has infected packages in a repository you use, don't update until more info is known. 

after you read up on the attack vector, you should do a first-response pass, this is about short-term fixes/changes you can apply yourself now to prevent being attacked. This can also frequently be done by imposing rules on yourself (for example, do an update freeze for two weeks.)

# Step 2: Understanding the spreading mechanism

this only applies if malware exists for this vulnerability.

most malware has a spreading mechanism, so that from an infected PC, it can continue infecting more PCs without the person who initially released the malware having to constantly manually infect new PCs. this also means that even when the initial source is gone, the malware may still linger.

It is important to understand *how* a piece of malware spreads, this information will generally come a bit later which is why you should have done your first-response pass before this step. 

if you know how the malware spreads, you can then assess whether the attack vector might change in the future, for example, a piece of malware may currently be spreading through unmaintained packages, but has a spreading mechanism to infect github repositories on the local device, so in the future, it could be accidentally shipped by a dev on an updated, maintained repository. 


# Step 3: understanding the payload

the payload is the actual thing the attacker is trying to do. the attack vector and spreading mechanism are how they get the payload onto your device, the payload is effectively the goal. 

understanding the payload is primarily important for the upcoming steps. This information is generally known pretty quickly. usually it's either a randsomware or an infostealer. anything that makes money off of you (so by making you pay them or by stealing your data). infostealers can also be part of the spreading mechanism (for example, the humble discord hack spreads itself by stealing someones info, using their account to message a bunch of people with a fake discord sign-in link and then using that to steal those people's info to repeat the cycle)


# Step 4: understanding the strategy

with basic knowledge of what the payload is, how the malware spreads (if it is malware) and what the attack vector is, you can piece together the strategies that (potential) attackers may have for exploiting the vulnerability. 


# Step 5: understanding the scope and targets

with basic ideas of what attackers may do or are doing to exploit a vulnerability, you can get a rough idea of the kind of scope, this is mostly for malware. something that spreads more easily and rapidly generally has a broader scope.

then, based on the scope and strategy, you can get a basic understanding of what groups of people are the likely targets. 

this is important, because it helps inform how many preventative measures you should take. if you are explicitly a target, especially for something relatively small-scope, then you should take maximum measures. if you are not a target and it's something small-scope, you can relax. if you're not a target but the scope is large, you should still be vigilant because while you may not be the target, you may still end up as collateral damage.


# Step 6: make a mitigation plan

this step *can* wait if you don't have enough information yet. do not rush to this step. 

once you have all the above information and *hopefully* some official guidance has come out on how to mitigate. start planning how you're going to implement those changes. decide whether or not you are at risk based on the information you have, and how much at risk you are based on the scope and target. 

if you've gotten all the way to this step without going "actually, it looks like this vulnerability doesn't affect me", it is worth doing properly. take the time to make the proper changes, read up on the topics you're working with. you don't need to understand the low-level stuff, but get at least a basic understanding of every component that goes into what is going on. ask questions, but be specific. don't blindly panic. 

this is why it is so important to do a proper first-response after checking the attack vector, that first response is your couch pushed up against the door giving you time to formulate a proper strategy. 

this mitigation plan does *not* have to just be configuration changes, it can also be habitual changes. For example, if malware is spreading through suspicious links, your mitigation may just be "im not stupid enough to click on these links now that i know what to look for", or as with the recent AUR hack, checking if the package maintainer has recently changed. this is something you can figure out without understanding the in-depth mechanics of the attack, as long as you know the basics. 


# some other things


firstly, and this is very important: help eachother. Helping does *not* mean posting fear-mongering comments, nor does it mean going "haha, distro X has a vulnerability, my distro is better than yours, nana nana boo boo."

helping means posting your findings, talking with other users about the issue, and giving properly researched advice. you will frequently find yourself relying on the work that more experienced users have done, and as you become more experienced yourself, you should start paying that forward. you don't have to be an expert on a topic to help, if someone else doesn't know something and you do, pay that knowledge forward. 


second, know your limits. Security is a serious subject, this is NOT the time to "yolo" it or pretend to be the expert. I won't say nobody is going to judge you for "being new", but anyone who does should be entirely disregarded. Be honest with yourself about what you can and cannot do (yet). 


Third, common sense. a *lot* of security is down to common sense. Don't install software you cannot say with certainty you can trust. For user-based repositories, verify who maintains the package. for github, check if the repository has some amount of popularity, issues, requests etc. 

