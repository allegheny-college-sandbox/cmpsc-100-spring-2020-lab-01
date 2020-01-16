# CMPSC 100-03 Lab Session 1: GitHub, file management, basic tools

* Assigned: 16 January 2020
* Due: 23 January 2020 by 2:30 PM
    * These toolss will be necessary for class next Thursday, so be sure to finish this work before our next lab period!
* Point value: 30 pts

In this lab session, we focus on setting up some of the various tools and platforms that are mission-critical to our work. Initially, these include:

* [Slack](https://www.slack.com)
* [GitHub](https://www.github.com)
* git
* [Atom](https://atom.io)

## General guidelines for laboratory sessions

* **Follow steps carefully.** Laboratory sessions often get a bit more complicated than their preceeding Practical sessions. Especially for early sessions which expose you to platforms with which you may not be familiar, take notes on `command`s you run and their corresponding effects/outputs. If you find yourself stuck on a step, let a TL or the professor know! Laboratory sessions do not mean that we won't help you in the same way we do during Practicals.
* **Regularly ask and answer questions.** Some of you may have more experience with the topics we're discussing than others. We can use this knowledge to our advantage. But, like in Practicals, let students try things for a while before offering help (**always _offer_ first**). To ask questions, use our [Slack](https://cmpsc-100-02-sp-2020.slack.com)'s `#labs` channel.
* **Store and transfer files using GitHub.** Various forms of file storage are more or less volatile. *You* are responsible for backing up and storing files. If you're unsure of files which have been changed, you can always type `git status` in the terminal for your working folder to determine what you need to back up.
* **Keep all of your files.** See above, but also remember that you're responsible for the files you create.
* **Back up your files regularly.** See above (and above-above).
* **Review the [Honor Code](https://sites.allegheny.edu/about/honor-code/) reguarly when working.** If you're taking a solution from another student or the Internet at-large (_especially_ [Stack Overflow](https://stackoverflow.com)), bear in mind that using these solutions _can_ constitute a form of plagiarism that violates the Allegheny Honor Code. While it may seem easy and convenient to use these sources, it is equally easy and convenient to rely on them and create bad habits which include not attributing credit or relying exclusively on others to solve issues. Neither are productive uses of your intellect. Really.

## Further helpful reading for this assignment

I recommend reading the [GitHub Guides](https://guides.github.com) which GitHub makes available. In particular, the guides:

* [Mastering Markdown](https://guides.github.com/features/mastering-markdown/)
* [Documenting your projects on GitHub](https://guides.github.com/features/wikis/)
* [GitHub Handbook](https://guides.github.com/introduction/git-handbook/)

* You may find a cheatsheet for Unix `command`s helpful throughout your time here. I recommend [this one](https://files.fosswire.com/2007/08/fwunixref.pdf) from FOSSwire.
* For Markdown, [this GitHub repository](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) serves as a useful guide.

If you find either helpful, I suggest bookmarking them.

## Accepting an assignment

- [ ] Log into the `#labs` channel in our class [Slack](https://cmpsc-100-02-sp-2020.slack.com)
- [ ] Click the link provided for the lab assignment and accept it in GitHub classroom
- [ ] Once the assignment finishes building, click the link for your personal repository assignment
```
If you see this message, you've already accepted the assignment!
```

## Assignment setup

You will only need to perform in the installation steps below _one time_ this semester -- today!

### Slack

A communications platform curing the headache of email.

- [ ] If you have not already, accept my invitation to our Slack workspace.
- [ ] Log in to our [Slack workspace](https://cmpsc-100-02-sp-2020.slack.com)
- [ ] Navigate to the `#labs` channel.
* If you did not receive an invitation, let me know and I can send it again.
* **Note**: You can use the `#labs` channel to discuss various elements of the assignment. In addition you can directly message me (@dluman) to chat directly about questions or issues that you have.

### GitHub

A kind of social network for code and developers to share and comment on code projects.

#### If you do not already have a GitHub account

- [ ] Visit [GitHub](https://www.github.com)
- [ ] Create an account using your `@allegheny.edu` email
- [ ] When creating a username, pick one which is the same as your Allegheny account username. If the username is taken, you may try substituting underscores for spaces, or adding a digit to the end of the name.

* Once you've completed the above steps, continue with the steps below.

#### If you have a GitHub account

- [ ] Log in to GitHub

* If you have a bit of time, consider:
    * Adding a professional profile picture to your account
    * Downloading [GitHub's "Student Developer Pack"](https://education.github.com/pack)

### Chocolatey (Windows only)

* If you aren't a Windows user, you can skip to [git](#git)

Chocolately adds Unix-like commands to the Windows command prompt. Many of these commands are helpful for making your work more efficient and easier.

- [ ] Open a Command Prompt window with administrative privileges
    * You may need to find and right click the `Command Prompt` entry in the start menu, and select `Run as Administrator`
- [ ] Copy and paste the following command:
```
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```
- [ ] To test this step, open a new Command Prompt window (`CTRL` + `R`, type `cmd` in the "Run" window) and hit `Enter`), and type:
```
choco --version
```
* You should see a line similar to `Chocolatey v0.10.15`. This indicates that the install was successful.

#### Windows Terminal

To help smooth out differences between operating systems, you will want to install `Windows Terminal` using the [instructions found here](https://chocolatey.org/packages/microsoft-windows-terminal).

### git

Where GitHub is a kind of social network which stores code, git is the application that allows you to contribute your code to that network.

#### Opening a terminal window

- [ ] If you haven't already, open a "terminal" window
* Depending on your operating system there are several ways to do this:
   * **Windows**
       * You may need to find and right click the `Command Prompt` entry in the start menu, and select `Run as Administrator`
   * **Mac**
       * Press `⌘` + `SPACE` and type `terminal`
   * **Unix**
       * Generally, `CTRL` + `ALT` + `T` does the trick
       
```
Keep this terminal window open! We will need it throughout this exercise
```

#### Windows

- [ ] In your terminal window, type:
```
choco install git
```
- [ ] After this operation completes, type `git --version` in the terminal window.
* If a line similar to `git version 2.25.0.windows.1` appears, the installation was successful.

#### Mac

- [ ] In a terminal, type `git --version`
* If git is not yet installed, the installer will start.

#### Unix

- [ ] In a terminal window, type `sudo apt-get install git`
* If git is not yet installed, the installer will start.

### Securing your GitHub account

The professional world uses a standard object known as an "SSH key" to prove a given user's identity and encrypt communications.

#### Generating a key

> Raise your hand to call a TL or the instructor over to help you through the following steps

- [ ] In the resulting terminal window based on the steps above, type `ssh-keygen -t rsa -b 4096 -C "{YOUR ALLEGHENY EMAIL}"` and press `Enter`
- [ ] At the prompt `Enter file in which to save the key`, press `Enter` to accept the default location
* If you look at the prompt, can you tell where the default location is?
- [ ] At the next prompt, enter a password used to secure the key
* You will use this passphrase to identify yourself as an owner or user of the key
- [ ] Once the keygen has finished, located the `id_rsa.pub` file where the process saved the key
* This is your unique key; it will be unintelligible to you (because it's "encrypted"), but it is your unique identifier. Keep all of the files this program generates.
- [ ] In the terminal window, type `cat ~/.ssh/id_rsa.pub`
- [ ] Copy only text output to the screen
- [ ] In the browser window containing GitHub, click the uppermost-right icon to access your account menu
- [ ] Locate and click the `Settings` entry
- [ ] On the resulting screen, locate and click the option for `SSH and GPG keys`
- [ ] Click `New SSH key`
- [ ] Give the key a title such as `Allegheny CS`
- [ ] Paste the long string of letters and numbers you copied above into the `Key` field
- [ ] Click `Add SSH key` to add the key

### File management

One key to making the process of completing assignments easier is to practice good "file management." The steps below will help you create a good foundation for your work this semester.

#### Creating a CMSPC100 folder structure

- [ ] On your desktop, right click to create a new folder
- [ ] Name the new folder `CMPSC100`
- [ ] Click the folder to open an enter it
- [ ] In your `CMPSC100` folder create `3` new folders:
* `Labs`
* `Practicals`
* `Activities`

Depending on the activity we're doing (be it a lab, practical, or in-class activity), we'll download and save our work to the appropriate folder. Today, that's the `Labs` folder.

#### Navigating your new folders

This section uses the commands or symbols:
* `ls`
* `pwd`
* `cd`
* `~`

Make notes about these commands as you use them so that you can remember how they work!

**Note**: For all intents and purposes, the words "folder" and "directory" are interchangeable below.

- [ ] At the `command` prompt, type `ls` (short for **l**i**s**t) and press `Enter`
* This `command` displays a listing of files in the current "working directory."
- [ ] To find the "current working directory," type `pwd` and press `Enter`
* This `command`'s syntax stands for "**p**ath to **w**orking **d**irectory"; your "working directory" is your current location on your hard drive.
* What displays?

The output of your `pwd` command was probably not your new `CMPSC100` folder. Let's try to get there.

- [ ] At the `command` prompt, type `cd ~` and press `Enter`
* `cd` stands for **c**hange **d**irectory, and allows us to move to and from different folders
* The `~` should take you to your "home" directory. This isn't your desktop, but it's closer.
    * For Mac users, your "home" directory generally appears similar to `/Users/{YOUR COMPUTER'S USER NAME}`
    * fOR Windows users, your "home" might look something like `C:/Users/{YOUR COMPUTER USER NAME}`
- [ ] Type `pwd` again and press `Enter.
* Did your location change?
- [ ] To look around where you're at, type `ls`
* What do you see? There may be a listing for your `Desktop` -- that's where we want to go!
* Windows users mights see a `OneDrive` directory
- [ ] Depending on what you see above (`Desktop` or `OneDrive`), type `cd ~/Desktop` or `cd ~/OneDrive/Desktop`
- [ ] In your new location, type `ls`
* Do you see your `CMPSC100` folder?
* How might you get there?

### "Cloning" a repository

#### Using the correct download link

- [ ] On this repository's page, click the `Clone or download` button in the upper right hand corner
* You may need to scroll up to see it
- [ ] In the upper right corner of the box that appears, click `Use SSH`
- [ ] Copy the link that appears in the textbox below the phrase "Use a password with a protected key."

#### Cloning

- [ ] Type `ls` in your terminal window
* You should be in your `CMPSC100` directory
- [ ] Change directories (`cd`) to your `Labs` folder
- [ ] Once in the labs folder, "clone" the repository using the link copied above
* If I (the instructor) were to clone my own repository, I'd enter (your link will look different):
```
git clone git@github.com:allegheny-college-cmpsc-100-spring-2020/cmpsc-100-spring-2020-lab-01-dluman
```

### Helping Ulysses find his way home

![Ulysses S. Cat](https://cs.allegheny.edu/sites/dluman/cmpsc100/img/ulysses-4-teh-fanz.jpg)

Now we're to the real problem at hand. My cat, Ulysses, has been wandering around the `neighborhood` folder, and needs to get back `home`; he loves to eat, and it's getting near dinner time. Your task: to move or copy him from the `neighborhood` sub-folders to the `home` folder. He's been known to hang out at the following places:

* Alley
* Corner
* Drugstore
* Mini Mart
* Pet Store
* Pizza Place

#### Copying and moving

This section adds the following commands or symbols:
* `mv`
* `cp`

- [ ] In your terminal, type `pwd` and press `Enter`
* Where are you right now?
* If not in your `CMPSC100/Labs` folder, how might you find your way there?
- [ ] From your `Labs` folder, `cd` to your `cmpsc-100-spring-2020-lab-01` folder
* The above is pretty long, so here's a tip: if you've typed at least `cmpsc-100-spring`, press `Tab`; your terminal will fill in the rest!
- [ ] Type `ls` to see a list of places where Ulysses hangs out
- [ ] `cd` into the `alley` folder`
- [ ] Type `ls` and press `Enter`
* You should see a file name staring with `ulysses` -- you've found him!
- [ ] To _move_ this picture _down_ one directory, type:

```
mv ulysses-1.jpeg ../
```

- [ ] Press `Enter`
- [ ] Type `pwd` and press `Enter`
* Where are you now? 
* What do you suppose `../` does?
* This command moves the image (`ulysses-1.jpg`) from the `Alley` to the `neighborhood` folder; now we have to follow it!
- [ ] Type `cd ../` and press `Enter` to move down one folder
- [ ] Type `ls` and press `Enter`
* Do you see the picture?
- [ ] To move the picture down one level and into the `home` folder, type:
```
mv ulysses-1.jpeg ../home
```
- [ ] Press `Enter`

* `cp` (or "copy") works exactly the same way, except that it _copies_ the image from one place to another instead of only _moving_ it.
* Tip: You can combine `../` multiple times to move images down more than one level. For example, to move `ulysses-1.jpeg` from `Alley` directly to `home`, I could've typed:

```
  mv ulysses-1.jpeg ../../home
```

- [ ] Move the remaining 5 pictures `home`!


### Waypoint

> 
> If you reach this point, stop here and we'll continue this exercise tomorrow during our first practical session.
>

### Finishing your work

First of all, thanks for bringing my cat back home. It'd be great if we could document and save this work.

#### Documenting your work

Throughout the semester, I'll ask you to write technical documentation which reflects on the work you've done in a given lab. Many students find this step helpful in recalling or explaining what they've learned.

- [ ] In Atom, open the `reflection.md` file located in the `writing` folder of your lab
* This file contains questions for you to respond to.
* It also contains `Markdown`, a text format which quickly creates document structure. We'll learn more about this in future weeks. For now, simply respond to the questions, writing at least 1 paragraph per question in the space provided.
* Be sure to save your work as you follow along!

##### A brief primer on Markdown

`Markdown`, as described above, is a set of symbols and conventions that structures a document. Here, we see use of the `#` character to signify _headings_.

The fewer the number `#` characters, the more important the heading is! This means that:

* `#` is the most important
* `##` the second most
* ...

The `#` is referred to as a _tag_, and must be separated from the text used in the tag by a space (` `).

### Docker

Docker is what is referred to as a "containerization" platform. Essentially, it is software  which ensures that programs run the same way _everywhere_. Docker is developed with the same goal as that of the Java language we'll learn in this course--that software should work the same regardless of where it's run. Our Docker "images" will contain a single, standard Unix operating system. This minimizes technical issues and allows developers to concentrate on their code, rather than system specs. Instead of downloading dozens of tools to build and execute software, containers allow us to run one file containing all of the utilities necessary.

- [ ] Download and install Docker.
* Depending on your operating system's version, you may need a specific platform. Consult your OS when considering the following options:
    * **Windows 10 Pro or Enterprise**: [https://download.docker.com/win/stable/Docker for Windows Installer.exe](https://download.docker.com/win/stable/Docker%20for%20Windows%20Installer.exe)
    * **Mac OS X > 10.11**: [https://download.docker.com/mac/stable/docker.dmg](https://download.docker.com/mac/stable/docker.dmg)
    * **Unix**: Depending on your version, use `apt` or `yum` (or other package manager)
        
#### Verifying installation

- [ ] Once Docker has started, open a terminal window
- [ ] In the terminal window, type `docker --version`.
    * The terminal should display a line similar to `Docker version 19.03.1, build 74b1e89`
    * If not, let either the professor or a TL know.
    
### Running your first container

A "container," though a technical term here, is pretty much what it sounds like: a sealed package that, while "renting" space on your hard drive, acts as an isolated set of software, usually containing an operating system and other specialized applications necessary for a specific task. Like we've briefly discussed in class, think of it as a kind of "picture-in-picture" system for running two different operating systems at once.

Typically, these operating systems and software combinations are _as spare as possible_, meaning that (to conserve "weight" or "footprint") they only incorporate exactly what they need to run and nothing more.

The "Hello, World" is a well-established computer science tradition. Often, when learning a new language or technology, the first example that a user makes is called a "Hello, World." This Docker container contains only enough to run this example, the output of which is highlighted below.

- [ ] In a terminal window, type `docker run hello-world`.

* This command will download and run the "Hello, World" container, returning output looking similar to the following:

```
docker run hello-world
docker : Unable to find image 'hello-world:latest' locally
...
latest:
Pulling from library/hello-world
ca4f61b1923c:
Pulling fs layer
ca4f61b1923c:
Download complete
ca4f61b1923c:
Pull complete
Digest: sha256:97ce6fa4b6cdc0790cda65fe7290b74cfebd9fa0c9b8c38e979330d547d22ce1
Status: Downloaded newer image for hello-world:latest
Hello from Docker!
This message shows that your installation appears to be working correctly.
```

> When you've finished running the Docker container, raise your hand to call a TL or the professor over so that they can have a look!

### GatorGrader

#### Docker `container`

- [ ] In a terminal window, type `docker pull gatoreducator/dockagator` to download the correct `container`.

##### Running GatorGrader directly on `container` start

* Be sure that you are in the main directory of your lab repository when running these commands, or you'll certainly experience issues!
    * Remember, the folder containing your work is located on the desktop.
* Remember that if you run `ls -la`, you should see a `.git` folder if you're in the main repository folder.
- [ ] To make sure you're in the right repository, type `pwd` and press `Enter`
    * If you recieve the expected path, you're in the right place!

```
docker run -it --mount type=bind,source="$(pwd)",target="/project" --hostname GatorGrader gatoreducator/dockagator
```

##### Windows users

Some Windows users may have difficulty with the above command. The command below should substitute for it:

```
docker run -it --mount type=bind,source=%cd%,target="/project" --hostname GatorGrader gatoreducator/dockagator
```

Here, `%cd%` is equivalent to the Unix command `"$(pwd)"`.

### Turning or saving progress in an assignment

The GitHub platform is a place to store your work. So, it makes some sense that should be able to _clone_ (download) from it, and push back (upload) to it. Here, we'll learn this second part.

- [ ] `cd` to your folder containing this lab in your `~/Desktop/CMPSC100/Labs` or `~/OneDrive/Desktop/CMSPC100/Labs` directory

Once in this folder, we need to tell git that there have been changes.

- [ ] Type `git add .` and press `Enter`
* This tells git to look through the _entire_ folder structure for new changes and "stage" them

- [ ] Type `git commit -m "{Commit message}"` to "label" the commit
* This is typically something like `git commit -m "Fixing a typo" -- the message in quotes should be as descriptive as possible, while still remaining somewhat short

- [ ] To send all changes to the server, type `git push`
- [ ] At the prompt, input the password associated with the `SSH Key` you created earlier in this exercise (yesterday)