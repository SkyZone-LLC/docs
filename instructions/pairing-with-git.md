## Pairing with git <!-- {docsify-ignore} -->

## Getting started 
You and your partner should follow these instructions together. "PartnerA" will assume the role of "driver" first, and "PartnerB" will assume the role of "navigator" first - decide now who those will be. You should switch these roles every 15 minutes (use a timer to keep track).

The steps below will help you establish a workflow for sharing your work with each other using Git. Note that for this to work, it is very important that only one partner works on the project at a time - you must stick to the driver/navigator roles.

- Both partners should fork the repo and clone their fork to their respective machines.
- **PartnerA**: Copy the url for your fork's github page from your browser's url bar (it will be something like `https://github.com/<PartnerA_username>/<PairExercise>`) and send that url to PartnerB via Slack
- **PartnerB**: Copy the url that PartnerA sent you, `cd` into your local clone on your machine and execute this command using that url:

Note: No need to include the "<" ">" listed below

```bash
git remote add partnerA <partnerA_github_url>
```
- Repeat the two steps above, swapping PartnerA and PartnerB
- Both partners should read the `README.md` of the project (separately)
- Once both partners have read the `README.md`, **start the pairing timer** and complete the workshop steps in order

## When it's time to switch roles 
- PartnerA should commit all of their work and push it to their master branch of the project directory:
```bash
git add -A
git commit -m "Meaningul commit message"
git push origin main
```
- PartnerB should then **pull** from **their partner's remote** (NOT from their own origin) in their project directory:
```bash
git pull partnerA main
```
- Once PartnerB completes the pull, they will have all of PartnerB's work, and you will both be ready to continue with roles reversed. When the time comes to switch again, you simply perform the same process (with roles reversed).



---

# EXTRA 

---


## Some Scenaiors And Soluions (Optional Reading)


####  How to Work Together ? 

 … Without killing each other

![fighting](../_media/fight.png)


#### Why is it hard to work in a pair?


In SkyZone, we will be doing mostly pair programming exercises
Necessary skill for the Interview Setting
Even some companies deploy the pair programming technique 
Learning to work together in pairs starts to flex the working together muscle for end of bootcamp -- and beyond!

####  Now, let’s discuss & roleplay 4 common Scenarios


1. **Wires Crossed**

> During a pair programming session, two pair partners are having trouble communicating ideas effectively. One person seems to have a good grasp of the goal and how to get there but cannot effectively communicate it — their ideas are coming out jumbled. The other person is trying really hard to understand. The dynamic alternates between silence and frustration.

- How would you respond when this happens?
- How would you respond if this happened multiple times?

> Communication goes two-ways: everybody here has the technical ability
If you can't communicate something well, it may be because you yourself don't understand something about it
Be aware of your natural biases—it can be easy to blame miscommunication on language barrier or accent, when really that's a red herring, we're all learning to improve our technical vocab
Takeaway: be upfront with your partner if you don't understand them, so that you can try to address it
"show instead of tell"
diagrams, writing it out, coding it out
using similar examples, pointing them out in docs / wherever
Go to another team member or “supervisor” for help


2. **Cutting Corners** 

> My partner isn’t willing to embrace the “productive struggle” with me. They will open up the hints before we even spend time talking through the problem, or even submit a help-ticket too quickly. I’ll make suggestions, but they seem to go unheard. Once, they even proposed the same idea as if they just thought of it themselves! 

- How can I assert my preference to work through the material together?
- How can I ensure my ideas are heard? 


> The bootcamp is stressful sometimes, it’s just easier mentally to look at hints or just give up and ask for help quickly
This could very well mean that your partner is tired or going through something
Be empathetic but also try to communicate firmly and politely of the dynamic that is desired
Takeaways
Ask them if they are feeling okay and if they want to take a break
Be upfront to your partner about the dynamic you want
Go to another team member or “supervisor” for help


3. **Speedy Driver**

> My partner is Driving the code way too quickly! I’ve been feeling a little overwhelmed by today’s content, and they’re just writing their own code. It seems to be working, but I don't always understand why and I feel embarrassed having to ask for explanations. I'm sure we will complete the workshop, but I'm worried I won’t retain much understanding of the concepts at hand. 

- How can I keep my Driver out of the speed lane?
- Where do you think the Speedy Driver’s mindset is coming from, and what habits can they establish for themselves so they remember to slow down? 


> Communicate with your partner about how you feel.
The Speedy Driver could just be very enthusiastic
The Speedy Driver also could be feeling anxious about finishing the workshop. Many students feel uncomfortable not finishing a workshop. It’s normal to feel like we want to finish things fully but the goal is not to finish but to work together and retain information and build programming mental models. 
Takeaways
Ask them politely to slow down
Teaching the concept to someone else will help solidify their understanding
Focus on the goals
After a few lines of code, slow down and have a discussion to walkthrough what is going on
Go to another team member or “supervisor” for help


4. **Lala Land**

> My partner has been in the navigator role for a while and keeps checking their phone. I don’t mind it happening once - maybe twice-, but it’s started to feel like they’re looking at their phone more than they’re engaged in our workshop. At this point I’m feeling pretty annoyed and frustrated with their lack of focus and contribution. 

- How can you re-engage your partner and get them back on track? 
- What would you do if it happens again?


> We don’t know what’s going on with our pair programming partner. They could be going through some personal issues.
They could be tired or hungry which can decrease engagement
Sometimes talking about code the entire time is exhausting
Takeaways
Ask them if they are doing okay
Ask them if they want to take a 5-10 minute break
Have a conversation about something completely different for a bit
Go to another team member or “supervisor” for help


## Does git as a group confuse you?

No worries, we are here to settle this confusion once and for all.

Let's consider this, Paul, Sergio, and Dave are all working on a project together.
We each have our own branches (for this example they are just our names).

Dave has finished a feature and puts up a pull request.  Sergio reviews it--everything is great!--and he approves it.

So now the master is updated with new stuff that both Sergio and Paul do not have.  They are going to want to do the following steps:

1. Add, commit, and push all their current changes to their branch! (You don't want to lose any of your work--so make sure github has been updated)
2. Switch to the master branch (in terminal type `git checkout master`)
3. Do a `git pull`.  (The pull request is approved so all members of group need to do git pull)
4. Switch back to your branch. (in terminal type `git checkout <branchname>`)
5. Merge master into your branch (type `git merge master`)
6. Add, commit, and push the merged madness to github.
7. At any point their may be merge conflicts--if these happen (and they will) make sure you go through each conflict, 1 at a time, with whoever did the latest pull request.  Either accept incoming change, keep your code, or combine both on each of the conflicting files.

Follow these steps and your conflicts should be minimized and your

