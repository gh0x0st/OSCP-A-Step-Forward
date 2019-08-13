# OSCP Journey
![Alt text](https://github.com/gh0x0st/OSCP_Journey/blob/master/offsec-student-certified-emblem-rgb-oscp.png?raw=true "OSCP Logo")

This August, I've successfully completed the Penetration Testing with Kali (PWK) course and passed the Offensive Security Certified Professional (OSCP) exam. This has been one of the most rewarding course experiences that I've had in my entire career. You go into the labs to build a foundation and you leave the exam feeling like you've built a house. 

I wanted to take some time and give back to the OffSec community and share some tips and my experiences that led up to my first and successful exam attempt in the hopes it helps pave the way into someone else's success story. 

### Shoot outs

There are so many great online resources out there, but I wanted to drop some lines on these three. The Facebook group alone is a great place with like-minded individuals, along with Michael and Bunne Flacs. Check them out when you have some time. 

* Facebook OSCP Study Group - https://www.facebook.com/groups/oscpsg/
* Michael with Digital Offensive - https://www.youtube.com/user/genxweb
* Bunne Flacs - https://www.youtube.com/channel/UCmE_COhIyRc1Naf67uAFKrA


### Path to Success
1. Prerequisites 
2. Course Material
3. Lab Network
4. Exam Strategy

### 1. Prerequisites:

I would like to talk about things for you to do, or think about, before you sign up for the PWK course. Very frequently you'll see people ask how to prepare for the OSCP. I could argue that PWK prepares you enough, but you must understand your own limitations.

**Do I understand how to use Kali Linux?**

I mean specifically how to use the operating system, not executing the tools. If you're not comfortable with the basics of Linux, then you may find that you'll struggle a bit. There is a course and a free PDF called Kali Linux Revealed (https://www.kali.org/download-kali-linux-revealed-book/), created by the Offensive Security Team that will take care of this for you. 

This book is like killing two birds with one stone. It's a book on how to basically use Linux, within Kali. What better way to help learn general Linux concepts within the OS the course is built around? With it being free, you can't go wrong with this.

**Can I perform an actual pen test?**

You need to understand your own limitations. This is a hard pill for people to swallow, especially publicly on the internet. Truthfully it comes with the territory in our field. If you are completely new to pen testing, do you feel you can you comfortably follow the courseware and pen test in their labs? What about if you take away the courseware, can you continue your own?

Then go ahead and jump in. If you want a precursor to the PWK Course, then dive right into Hack the Box (HTB) or look at EC Council's ECSA. I know EC Council is a touchy subject, but this all falls back on knowing your skillset. With ECSA, the exam itself, when I took it, was a written exam and 5 machine practical test that you had to provide a report for. Its difficulty was nowhere near the OSCP, but it's a good introduction into whether you can follow an ordered methodology without getting hints online.

ECSA - https://www.eccouncil.org/programs/certified-security-analyst-ecsa/

I find that CTFs are actually a great way to practice for the OSCP. They force you to enumerate meticulously and thoroughly, which is where most people tend to freeze. Look at this list from NetSecFocus, for the ones that retired, it's worth spending the money on to practice. 

![Alt text](https://www.netsecfocus.com/assets/img/posts/TJNulls_Preparation_Guide_for_PWK/hackthebox.png "HTB Table")

**Which Linux operating system do I use?**

When it comes down to it, the entire course, and as the name implies, is built around Kali Linux. However, they provide you a student VM, along with other tools, on a specific build of Kali. If you don't want to use Kali and want to use Parrot or something else, then that is up to you. You're not going to have any advantage, or disadvantage by using any other OS, except maybe with some of the exercises. 

Kali Student VM - https://support.offensive-security.com/pwk-kali-vm/

**What host system should I use?**

This is just my personal preference, but I used a hardened version of Windows 10 as my host OS and had VMWare Workstation Pro to serve up my Kali VM. You must run screen recording software on your host machine and web cam software on either the same machine or a different machine. Regardless of the host OS you're using, be prepared that if you run into a technical issue with either of the technical proctoring components that you cannot resolve in a timely manner, they will fail you.

**How will I stay organized?**

**_Backups:_**

You need some sort of backup solution for your notes. The last position you want to be is in your exam and suddenly, your VM crashes and you can't get any files from it. I really enjoy OneDrive, I have it set on my Windows 10 Machine, and shared the directory with my Kali VM. This way I dump all scan results, scripts, etc, to the shared directory and they instantly sync to my windows machine and the cloud. 

On the night before my exam, I setup two different virtual machines. One I called Kali-Exam and one called Kali-Exam-Backup. Both machines were setup and configured and ready to go at any time. There were times during my lab time where my virtual machine just died. I didn't run any updates or change anything fancy, it just wouldn't boot or take accept snapshots. Be prepared for this.

**_Notes:_**

I have no objections to using CherryTree, Dradis, etc, but I've always used OneNote and stuck to what I was comfortable with. Most importantly, make sure your solution is backed up somehow.  You don't have to get overly fancy or verbose with how you take notes. Just keep it easy enough so if you wanted to revisit a machine, you understand the steps you took to get you to wherever you left off. I like to treat machine notes and scan results as two different things. With machine notes, I kept them as brief narratives about where I left off or how I accomplished a foothold. If I needed the more technical details, I would add them in my formal write up while referencing what I needed in my scan results. 

![Alt text](https://github.com/gh0x0st/OSCP_Journey/blob/master/OneNote_Snippet.png?raw=true "OneNote Snippet")

**_Terminal:_**

TMUX is a life saver, enough said. This is a solution that will help your terminal stay organized very easily. I've never used another solution other than Tmux, but it works for me. I use it in a few different ways. One way is to keep each step of the exploitation process on its own tab. If I need to reference anything, I can just go to the next tab. Granted we should always output our scans to our backup directory '*awkward glare*', but sometimes when you're in the zone you just want to look at a terminal.

![Alt text](https://github.com/gh0x0st/OSCP_Journey/blob/master/TMUX_Snippet.png?raw=true "Tmux Snippet")

The other reason why I use a terminal organizer is when I’m trying to catch shells. I like being able to split a shell so I can attempt my command and see if I catch it all in one view without going back and forth. 

![Alt text](https://github.com/gh0x0st/OSCP_Journey/blob/master/TMUX_REV_SHELL.png?raw=true "Tmux Snippet 2")

### 2. Course Material:

The courseware and the videos go hand in hand. What I would recommend you to do is read a section and then watch the corresponding video. The great thing about the courseware is that you'll be finding and attacking machines in the lab depending on the chapter. It will not go through every machine, but it will teach you how to find low hanging fruit.

Keep in mind that if you want those 5 extra points, you'll need to document your course exercises. Most of them you can answer with a screenshot so if you document the exercises in OneNote it'll be easy to port them over to lab report. 

### 3. Lab Network:

The lab network was probably the most fun I had in the entire course. This is where all your prep work and studying comes out to shine. If I could stress anything about the lab it would be down to two talking points, security and strategy.

**_Security_**

You are connected to a lab network with hackers; some are ethical, some likely not. Offensive Security puts in a lot of work to vet their applicants before they are even accepted into the course. Once they're in, they put in controls to help lower the likelihood of students being able to attack each other, but you should still be cautious. Whilst you can attack the lab targets, students on those targets could leverage this. Just always be cognizant of what you're doing. 

* Make your root password complex and only turn on SSH when you need it
* Restrict your listeners to only the expected hosts. This is straight from an exercise and is a good overall idea. The example here drops all traffic to port 4444 unless it's from ip 10.10.10.10.
iptables -A INPUT  -p tcp --destination-port 4444 ! -d 10.10.10.10 -j DROP
* Kill your listeners until you’re ready to use them
* If you drop a payload on a target, then go away for a few hours and the machine hasn't been reverted, either review what you dropped or just generate it again before you decide to execute it

in Kali Linux Revealed, grab the free PDF and look at chapter 7, Securing and Monitoring Kali Linux. You will read some great resources on securing Kali.

**_Strategy:_**

This is where it gets fun, and truthfully will determine how much you're willing to discipline yourself in the PWK Labs. Here are some simple guidelines to work by:

1. Only use EternalBlue and DirtyCow once and after the fact exploit them the intended way. You can own quite a few machines using EB. But in the end do you really think you'll be able to use it in the exam? There's absolute merit in using it in the field because most organizations have a poor patching strategy, but the OffSec admins are not clueless. Do not rely on these; if you get stuck on a machine, just move to a different target and come back.

2. Do not use automated enumeration tools...yet

There are only two times to use automated scripts: To save time and to reverse engineer. When you are in the labs, you really need to learn how to enumerate the machines manually. Sounds simple? It really is, but people tend to be a little lazy at this step. Here's a rough methodology that I follow with every machine:

1. Find open TCP/UDP ports
2. Identify the services on those ports
3. For each service you find, identify their version and write them down. For example:
   - 22/tcp ssh OpenSSH 6.6.1p1 Ubuntu 2ubuntu2.13 (Ubuntu Linux; protocol 2.0)
   - 80/tcp http Apache httpd 2.4.7 ((Ubuntu))
4. For each service you have identified, one service at a time, use the Nmap NSE scripts against them. You should really get into the habit of exhausting Nmap and its scripting engine before you touch any other tool.
5. Use targeted enumeration tools, such as Nikto for web or enum4linux for SMB 
6. Now if you have a web server, spend about 20 minutes going over some general checks for file inclusions, injections or other possible attack vectors. This isn't the OSWE course, if there's a web attack vector in OSCP, it's not going to be that difficult to find.

At this point, you should have a decent attack plan. If you train yourself to pause before looking for exploits, you'll learn to enumerate thoroughly. This is important. That last thing you want to do is try to launch an exploit at the first service you find, only find that it doesn't work and getting yourself stuck in a rabbit hole.


### 4. Exam Strategy:

All the work you've done has led up to this point. You've completed the coursework and have spent some good time in the labs. Now there's a few things you should do before and during your exam:

**_Report Template_**

The templates provided by Offensive Security are great and are more than enough, but don't be intimidated to forge them a bit into what works for you. After your exam, you're going to have 24 hours to submit your exam. You're likely going to be very mentally drained. You should really rest at this point. Save yourself some time and make your report template ahead of time. This is the general template I used for every machine:

![Alt text](https://github.com/gh0x0st/OSCP_Journey/blob/master/Report_Snippet.png?raw=true "OneNote Snippet")

**_Screenshots_**

A good strategy with your screenshots is trying to get a screen grab with each major step of the exploitation process, but when you save the screenshot, save them in numerical order, such as 1_nmap, 2_nikto, 3_dirscan, 4_exploit, 5_lowshell, etc. This way when you are done a machine, you can scroll through all the screenshots to ensure you have a screen grab of every major step you have taken, and it'll be easier for you to see if you have missed anything.

**_Script Output_**

Learn how to output all your tools to a file and save them to your shared drive directory that we talked about above. This way you can always fall back and review results in the event you close a terminal, reboot, etc.

**_ Automated Enumeration_**

You need to manage your time wisely. This is where it's safe for you to use scripted enumeration. While you're working on one machine, you should be scanning the others. I liked the python script called AutoRecon by Tib3rius. It was efficient and provided all the details you need in easily identifiable txt files. There's a lot of these tools out there, of which I'll reference below. But before your exam, try them all out and see which ones help you the most. Just pick one machine in the lab and let them run.

1. AutoRecon - https://github.com/Tib3rius/AutoRecon
2. Reconnoitre - https://github.com/codingo/Reconnoitre
3. nmapAutomator - https://github.com/21y4d/nmapAutomator


With all of this is said and done, just relax. If you fail the first time, don't give up. Get back in the labs and practice more.
