# CS 234 Lab 1: Hello World"

## Preliminaries
**GitHub**. We're using GitHub to manage how all the code goes from us to you and back to us again. That means you'll need to create yourself an account at https://github.com. If you haven't already done so, you need to it now.

**Student Introduction**. We have an introduction form in the LMS to track all of the students in the class. Please fill it out ASAP if you haven't already done so. If you don't fill out the form, we won't be able to give you a grade in the class.

** Moodle LMS**. We will use Moodle LMS to manage all the activities within this course. We will post lab exercises, assignments, and any other practical-related announcements in the LMS. Please, make sure you login regularly.

## Introduction
This lab will focus on making sure you have installed IntelliJ properly, including the necessary libraries and plugins. Our goal is to make sure that we've sorted out all development environment issues. If you have already programmed in Java, you should be good to go. If you are a beginner, don't panic. This exercise will walk you through getting everything installed properly on your computer so, for subsequent assignments, things will go much smoother.

## Install Git
"Git" is a distributed version control system, used to manage code repositories. "GitHub" is a commercial service that hosts Git repositories in the same way that "Gmail" is a commercial service that hosts email. We're not going to teach you all the gory details of how Git works, since there's a lot of complexity that only really happens when you work in teams. Nonetheless, Git is widely used in industrial and open-source software development. You might as well get started.

To get Git installed on your computer, each operating system you might be using has its own quirks for this. You can follow the instruction as described here: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

## Install Java
You need to install the latest version of the Java Development Kit (JDK). You can get it here: https://www.oracle.com/java/technologies/downloads/. The latest version is Java 18. Oracle has different packages for all platforms including Linux, macOS, and Windows. You can follow the installation instructions for each platform as described here: https://docs.oracle.com/en/java/javase/18/install/overview-jdk-installation.html

## Install IntelliJ
Visit the IntellJ IDEA download site: https://www.jetbrains.com/idea/download/ and download the free "community edition" (CE). Versions are available for Windows, MacOS, and Linux. IntelliJ is an example of an integrated development environment (IDE). The other popular Java IDE you may have heard of or used in the past is Eclipse and NetBeans. For CS 234, you will use IntelliJ. If you run anything else, we won't help you when it breaks, and if you submit something that "works for you" but doesn't work for us, your grade will suffer.

If this is the ﬁrst time you have installed IntelliJ IDEA on your computer, the software will ask you to customize it a bit before starting. You can pick a color scheme that you like, then it will ask you to customize diﬀerent plugins. You can skip this for now, and start using the IDE.

If you've previously installed IntelliJ, it's time to upgrade. The latest version as of this writing is "IntelliJ IDEA CE 2022.1" which was released on 12 April 2022. It is important to install the latest version as IntelliJ keeps getting better every year, with new features and bug fixes.

## Getting Started with IntelliJ
If you've previously used IntelliJ and have a project open, you'll see a menu entry, File → New → Project... Otherwise, if you're staring at the "Welcome to IntelliJ IDEA" launch screen, there's a Create New Project button. Click it. Either way, you'll see many different kinds of projects to choose from. In the left column, it should offer you a "Java project" as the default option, and there's a drop-down from the top that should let you select "18" as the Project SDK. If it's only offering you an older version, don't worry, we'll fix that below. Otherwise, you just give it a name (“Hello”) and tell IntelliJ where to put the files (typically inside the “IdeaProjects” directory).

If IntelliJ is telling you it has Project SDK: <No SDK> at the top of the window and gives you no other choices, you should hit the New... box. It should automatically find the path to the latest JDK installation. If it doesn't you can manually locate it. On my Windows machine it was located at C:\Program Files\Java\jdk-18.

### Hello, world
At this point, you're ready to write a program that actually does something. We're going to keep this super simple and verify that you can create a Java8 "Hello, world" program.  You should be able to right-click on the left column where it has "src" and create a new Java class. Go ahead and do that with a simple name like "Hello". It should go ahead and make that for you and will fill it out with something hopefully like this:

```
public class Hello {

} 
```

Rewrite that to look like this:

```
public class Hello { 
    public static void main(String[] args) { 
        System.out.println("Hello, world"); 
    } 
} 
```

Right-click on "src/Hello" in the left column, and select "Run Hello.main()".  It should go split-screen on you and you'll see "Hello, world" printed at the bottom. Now for something silly, but it's enough to verify that yo''ve got the latest version of Java working, rather than something older that might be leftover on your computer:

```
import java.util.function.Supplier; 

public class Hello { 
    public static void main(String[] args) { 
        System.out.println("Hello, world"); 

        Supplier<String> x = () −> "Hello, lambda!"; 
        System.out.println(x.get()); 
    } 
}
```

If that worked, then you're running Java. Congratulations!!!

## IntelliJ, Git, and GitHub
We already had you install Git in a previous section. Now you're going to connect it to IntelliJ and use it to copy our reference code from GitHub to your own computer.

### IntelliJ + GitHub
IntelliJ has special support to talk to GitHub, avoiding all the mess of usernames and passwords you'd use for other Git servers. After you log into GitHub's web page, the icon in the upper right
has a Settings selection, and from there you can select the Personal access tokens tab on the left.

Picture here

At that point, you select the Generate new token button in the upper right, and give the token a name (e.g., "Aron's Laptop"). It's important, when GitHub asks you, that you give this token all the "repo" permissions.

Picture here

After you generate it, your token is displayed as a long string of random digits. Leave this on-screen, then flip over to IntelliJ. You're going to need to tell IntelliJ how to use this token. You do this, one time, and IntelliJ will remember it. Go to your preferences (IntelliJ IDEA →Preferences... on a Mac, File →Preferences... on Windows) and select Version Control →GitHub. You should see this:

Picture here

Click the "Add account" link. You'll see the ﬁrst dialog box, below. Click the "Enter token" link and you'll see the second dialog box, also below. That's what you want. Paste the "personal access token" into the "token" box and hit "Log in."

Picture here

If you're successful, you'll end up looking at something like this:

Picture here

IntelliJ might also ask you for a "master password" that it uses to encrypt a database of all the different usernames and passwords that you might use with it. You can choose any password you like This password will never leave your laptop.

### Cloning your repository
Every week, we'll give you a new link via the LMS. You'll click on it and GitHub will create a copy of our reference code for you. For this week, go ahead and click this:

Link Here

You may see a permission dialog from GitHub, which you should approve. Next, click the button to Accept this assignment and you're ready to make a local copy by "checking out" this code from
GitHub. You'll want to select File →New →Project from Version Control →Git. You'll then get a dialog like this:

Dialog here

You'll use the URL that GitHub created for you. It probably looks something like https://github.com/RiceComp215-Fall2018/comp215-week01-dwallach/. Copy-and-paste it into the dialog box, then hit Clone . You'll get some pretty obvious questions like this:

Here

Select Yes. You'll also get a somewhat more complex dialog like this:

Here

We use a tool called "Gradle" to help conﬁgure IntelliJ and many other things. Select "Gradle", hit Next, and you'll see this:

here

Make sure you select Use gradle 'wrapper' task conﬁguration and make sure it mentions the Java18 JDK that you installed earlier as the Gradle JVM. If so, you're good to go. Hit Finish and it will then do all the work for you.

*Now that it's all done, you'll have a directory that lives inside IdeaProjects in your home directory. You'll create a separate Git repository every week as part of CS 234. Please make sure they're in separate directories. Don't try to open one on top or inside of another.*

### Make sure it's working
If everything is working, you should be able to scroll through the "Project" tab on the left, into the test directory, which will have a green background. You can dig your way down to and right-click on StringThingTest, selecting "Run StringThingTest". Everything should compile but one of the tests will fail. If so, then you're almost done. If you get compiler errors, then you need to back up and revisit the steps above to get Java conﬁgured properly. (Or, if you have problems, ask for help.)

## Do the Lab Assignment
For this week, there is a simple assignment.
- There's a file called README.md at the very top-level of your week's files. Right now, it's got your instructor's name in it. Please edit it to have your own name, your Rice NetID, etc. In future weeks, we'll have other questions for you here as well. </p>This file is an a format called "Markdown", which lets you do all sorts of fancy formatting without having to learn HTML. You're free to read up on how it works: https://guides. github.com/pdfs/markdown-cheatsheet-online.pdf. When you visit the webpage at GitHub.com corresponding to your project, you'll see this Markdown turned into beautiful HTML.

- You will edit StringThing.java. There's a static class instance, defined on top, that's meant to represent your student information. Change it to instead have your own name, expected graduation year, Rice NetID, and preferred email.

- Run StringThingTest, and you'll notice that one of the tests fails. There's a bug in StringThing's getNetID() method. Fix it. Verify that StringThingTest works.

A quick warning: GitHub has a bunch of features that you should absolutely not use. Notably, you can directly edit files on the web in GitHub. Don't use GitHub's editing features. We're trying to ensure that you make all your changes in IntelliJ, so you never have to worry about merge conflicts and other problems that can happen when you're editing in more than one placed at a time.