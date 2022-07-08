---
title: I passed the OSCP with 100 points
date: 2022-07-01 14:22:00 -0600
categories: [OSCP]
tags: [OSCP]
---

# I passed the OSCP with 100 points w/o lab report.

[Youtube Version]()

This post and video share parts from eachother. 


## Whoami
My name is Beau and I am a web app pentester for a company.
And recently passed the OSCP with 100 points without the lab report. 

My post on linkedin got some traction so I decided to make a blog post

![LinkedInPost](/assets/img/LinkedIn_Post.png){: width="250" }

## Disclaimer
Everything I talk about is in generalities and not specific to my exam. Everyone gets different boxes. This is just my experience. 
Everyone also comes from different starting points. So how I studied and what it took for me to pass will be different from what it will take for other people to pass. This is why it is important to talk about… my background. So you can see where I’m coming from.

## Background
I barely graduated high school. 2.5-ish GPA. No college. I genuinely don't consider myself a smart person (just obsessed about pentest/red team topics). If I can pass this exam then so can you. 
I do have a lot of experience in IT. About 10 years actually. And currently I am a Web app pentester. I got lucky and my company took a chance on me without any previous security experience and no relevant certs. 

I get asked a lot if you need dev or IT experience? I’d say yes or at a bare minimum it will make your life a lot easier. If you don’t, I would recommend doing some of the beginner paths on TryHackMe. I believe that Offensive Security is also trying to address this with the level 100 courses that they now offer. 


## So why get OSCP if I already have a job
ADD + midlife crisis. 
I was at this public event. Crying. That I can’t seem to accomplish any of my goals. I have too many things I want to do. Too many things that are interesting. Too many things I want to learn. And I just can’t focus. On anything. I have 10 raspberry pis. All with projects assigned to them. Unfinished. I have over 450 Udemy courses:

![udemy](/assets/img/Udemy.png)

I’m also on pluralsight, linkedin learning, INE pentesterlab pro. I have active subscriptions to all of those. You can just imagine what my playlists look like. 

The OSCP gave me something. Something hard. To work towards. I decided with my wife that this is what I wanted to do. I’m going to spend the next bit of my life working towards this goal. 

I signed up for HTB that day. Then later on in November I saw that the Learn One went on sale for 2k I signed up. 

## Overall Journey once I made the decision to start

Started streaming myself practicing on Hackthebox about 9-10 months ago. Sometime in September 2021

Actually sign up for PWK
Nov 4, 2021

Changed exam to include AD announced.
December 1st? 2021

First exam attempt (No AD)
Mid December 2021

I didn’t study much until 1.5 months before second exam started. I spent my time doing extra practice on Windows and AD because of the new exam format. If I hadn’t studied the AD portion of the PWK PDF, I probably wouldn’t have passed. 

I started my exam on 5/31/2022

I got the email that I passed my exam on 6/3/2022

## Stats

The closest measurable metric that we have to determine if someone is ready for the exam. I wish there was a better way to tell if someone is ready but I can’t think of anything better so here we are. 

35 HTB boxes from TJNulls list

45 Proving Grounds boxes. All easy boxes and a lot of medium boxes a few hard.

~10 boxes in the PWK lab

Signed up for pwk on Nov 4 2021, Failed first exam mid December with 65 points. 

Passed new exam format on June 3rd 2022

## Timeline of actual exam

![OSCP-Timeline](/assets/img/timeline.png)

## My study process

What I did will not work for everyone. I was already a web pentester. I had already been a windows sysadmin and a network engineer. I wasn’t great at those things but it still helped a lot. 
I’m glad I streamed on [twitch](https://www.twitch.tv/beauknowstech). I learned so much from the people in my chat. Not everyone can do this. But I had fun, made some friends and learned a lot. It also kept me accountable.


The second thing I did well was I learned by doing. I made notes along the way. 
Any time I got stuck on either a foothold or a privesc for more than 1.5 hours (I would set a timer). I would look at a writeup or a hint just for that part, not the whole box. Why didn’t I see this before? What check/or methodology step can I add to my notes to make sure I don’t get stuck next time. 
I feel like doing it this way did two things. 
It prepared my mind for the approximate timing I was looking for on the exam. It became a race. An hour and a half. 
I didn’t spend too much time banging my head against the wall and not learning anything. It was a balance of challenging and productive learning.

Some people semi-disagree:
<https://robertscocca.medium.com/avoiding-common-oscp-pitfalls-d2dd929fdb03#:~:text=commands%20for%20hours.-,Hints%20and%20Write%2Dups,-The%20largest%20mistake>

I actually mostly agree with the blog post. OVER-reliance is bad. But don’t feel bad if you have to look. This is how you learn.

I looked at walkthroughs even if I pwned the machine myself. Several times I found the unintended privesc. And many times I did do the right foothold or privesc but in a different way. It helps to know how to do the same things in a few different ways or with different tools. For example, ASREP roast-ing and kerberoast-ing can both be done from kali using impacket tools. Or they can be done from windows using Rubeus/powershell scripts.

I also did practice exams. So on some of the weekends leading up to the exam I did 5- boxes a day like on here:
<https://github.com/ajdumanhug/oscp-practice>
(This needs to be updated but its hard to find AD practice machines)

For me the key to my style of studying is to actually do. Meaning you can read the PDF, read every blog/reddit post. Watch every youtube video. But it's not going to stick in your head until you get hands on the keyboard and actually hack stuff. I call it getting your feet wet and your hands dirty. 

## Why did I fail my first exam

I didn’t do my lab report. 65 points. So close.. It was honestly worse than if I failed by a lot. Or at least that is how it felt at the time.

I relied too heavily on enum/recon tools and didn’t do enough manual recon.


The only additional study that I did between exam attempts was Active Directory and some more windows machines. I actually took a long break for about 3 months right after I failed my first exam. 

![flag](/assets/img/oneflag.png)

## Advice for if you are brand new. 

If you really don’t know where to start, do [tryhackme](https://tryhackme.com/) first starting with the pre-security path. This will introduce you to how computers and networking works. As well as the windows and linux basics. Then [HTB](https://hackthebox.com) (5 easy windows machines and 5 easy linux machines). Follow along with [ippsec](https://www.youtube.com/channel/UCa6eh7gCkpPo5XXUDfygQQA) for those first 10 or so boxes so you can get the basic methodology down. Next do a bunch of boxes from [TJNull’s famous list](https://docs.google.com/spreadsheets/d/1dwSMIAPIam0PuRBkCiDI88pU3yzrqqHkDtBngUHNCw8/edit#gid=0). Then sign up for PWK and do the lab for a few months. Saving proving grounds for the last 2-3 months before the exam as they seem to be the closest to the exam machines. 


Everyone wants to be as efficient as possible. But I do think that there is a good reason to get the Learn One. One year. Two exam attempts. I think it's great. If you can… get your work to pay for it. If you are in a dev, IT or security role, they should. That is nothing for most education budgets at most companies.


Exercises/Lab report. I still don’t know if I would do it or not if I was starting over. On one hand, I WOULD HAVE PASSED THE FIRST TIME IF I HAD DONE THE LAB REPORT. But how long would it have taken me? People are saying that their lab report is over 300 pages with the training exercises. I just don’t know if it would have been worth it for me. 


I am very excited to see what the Offsec live stuff will look like, so if you are new I would check that out:
<https://www.offensive-security.com/offsec/offsec-live/>


I did very few boxes in the PWK lab. Mostly just the two AD sets. 
I didn’t spend a lot of time in the lab. It was
 too much fun. Meaning I spend time doing things that weren’t going to help me on the exam. 
I couldn’t target specific things I was trying to learn. Other than AD, that part was great.

## Random TIPS

This section may be updated periodically as I think of things

### Expect to learn, not to be taught. 
I almost failed out of highschool. I graduated with a 2.5 gpa or something like that. I really really suck at being taught. I am ok at learning when it comes to things that are interesting. Luckily hacking is fun. I do it for work and I do it in my free time. I probably should be better at it than I am.
The PDF/videos and other training material is good. But its not like a math textbook or something. You have to apply what you are learning and adapt to each situation. They are teaching you the hacker mindset. 

### Backup your kali VM a lot

### Know when you work best and when you will want or need a break. 
On both my exams I started in the morning, knowing that I wouldn’t be able to sleep unless I had enough points to pass. I wish I had the coolness/level headed-ness to start in the afternoon without freaking out all morning before the exam started, and be able to rest at a reasonable hour if I didn’t have enough points. 

### Review the PDF/OSCP training to make sure you cover any knowledge gaps 
I would have failed my second exam if I didn’t go through the AD portion of the PDF. I didn’t read much of the rest of the PDF other than checking the index to make sure I covered everything in my own studies. I don’t learn well from that kind of format. I learn best from working on machines, making mistakes, looking at hints and walkthroughs, then taking extensive notes. I built a methodology for myself for each step. 

Which is exactly how I studied. TJnull’s list on HTB first. To get my methodology down. I streamed this for a few months on twitch and got help from all you and bunch of other people who were far more advanced than myself. I do like hackthebox but like everyone says, Proving Grounds boxes are closer to the OSCP. I saved those for last for this purpose. 

In each case even if I successfully got root/admin I would look at as many walkthroughs as I could to see how other people did it. If they did something differently and it was something I felt was valuable, I would add it to my notes/methodology

### Watch these people on twitch/youtube
https://infosecstreams.github.io/

### My Notes
Right now all my notes are on onenote, which is great for auto backup. But I wish I had found a markdown setup that I like. I tried them all…. joplin/obsidian/notion all the things. I might share my notes if I ever get the time to spend 12 hours converting them all to markdown. But to be honest I don’t think it would help anyone because building your own methodology and your own notes is invaluable. That is how you learn and grow. 

### Read the instructions carefully
Reset the box when something that should work isn’t working.



### Know your tools:
Know when and how to use all the tools.
Read the blog post
<https://www.offensive-security.com/offsec/understanding-pentest-tools-scripts/>

<https://github.com/carlospolop/PEASS-ng/issues/125>

Understand what each of your tools do. They make some good points in the blog post.


## Don’t rely too hard on helper tools:

I love these tools but I think one reason I failed my first exam was my reliance on these tools. And I know for sure that I only passed my second attempt because of my balanced use of these tools in addition to my manual enumeration/recon.


<https://github.com/Tib3rius/AutoRecon>

<https://github.com/21y4d/nmapAutomator>

<https://github.com/diego-treitos/linux-smart-enumeration>

<https://github.com/carlospolop/PEASS-ng>

<https://github.com/itm4n/PrivescCheck>

<https://github.com/GhostPack/Seatbelt>


Some people heavily advise against any auto tools on reddit because they give you TOO much information. 

<https://old.reddit.com/r/oscp/comments/n1w87b/passed_oscp_this_week_a_big_thank_you_and_some/#:~:text=While%20I%20understand%20the%20reasoning%20behind%20tools%20like%20AutoRecon%20and%20NmapAutomator%20I%20would%20advice%20against%20using%20them%20on%20your%20exam.%20Just%20go%20through%20the%20machines%20manually%20and%20inspect%20the%20results%20at%20each%20stage.>

Usually what I do is I have a set of manual tests that I do first and if those checks don’t find anything obvious then I run the auto tools. My manual checklist grows almost every time I have to use auto tools. I add to it whenever I can. 



## OSCP is just the beginning, not an end
You might get job offers, a promotion or something but this cert is entry level. A starting point. Any cyber position, red or blue, is always evolving. You gotta learn every day. 


<https://www.youtube.com/watch?v=rpm_V_88wds>

I personally don’t think that pentesting is for everyone. But if you are passionate about it, go for it. If I can get a job and pass OSCP, then so can you.

## Am I a hacker now?

Well yes and no. Yes because just the fact that you wanted the OSCP and we're curious enough to even figure that out, you are a hacker. You are a hacker for wanting to be a hacker. Go read atomic habits. And no because The OSCP is just the beginning... Plus a hacker is never done learning. And honestly that's the best part

The OSCP is practical. And you will learn basic technical pentest skills. But I think more of what you learn is the hacker mindset + hacker methodology. I really think that is what they are teaching in the pen-200 course and exam and the cool technical skills you will use for a real pentest job, will come in their higher 300 level and up courses. (Personal opinion)


Some helpful links:

<https://docs.google.com/spreadsheets/d/1dwSMIAPIam0PuRBkCiDI88pU3yzrqqHkDtBngUHNCw8/edit#gid=0>

<https://lukasec.ch/posts.html>

<https://www.offensive-security.com/offsec/my-philosophical-approach-to-oscp/>

<https://old.reddit.com/r/oscp/comments/itkyik/passed_oscp_my_experience/>

<https://old.reddit.com/r/oscp/comments/te9tk3/passed_in_6_hours_heres_my_rambling/>

<https://infosecwriteups.com/how-i-passed-oscp-with-100-points-in-12-hours-without-metasploit-in-my-first-attempt-dc8d03366f33>
