---
title: "Sprucing Up Your Online Portfolio with Jekyll"
date: 2020-09-02
tags: [Jekyll, Portfolio, Blog, Website]
header:
  image: "/images/blog/john-schnobrich-unsplash.jpg"
  teaser: "/images/blog/john-schnobrich-2FPjlAyMQTA-unsplash.jpg"
excerpt: "How to update your Github Page Portfolio using Jekyll"
mathjax: "true"
---
### Sprucing up your Portfolio/Blog
<p align="justify">
I've had this blog for sometime now. While it was a great way to get a website up using the free options available at with Github pages, I didn't really look into it as much as I should have. I found a good tutorial, forked over some files and made some customizations. I will probably write a tutorial on how to create a basic one as well. It's a great start, but its not really something I created on my own. I wanted to really create something myself and customize it the way I envision.
<br>
<br>
My original site used the Jekyll Theme Minimal Mistakes (https://mmistakes.github.io/minimal-mistakes/). Forking over was a great start but I really wanted to make some customizations.
<br>
<br>
I went over to Jekyll's Website (https://jekyllrb.com/) to get more information on installing Jekyll. I am a windows user by the way.
<br>
<br>
In order to install Jekyll, you need Ruby version 2.5 for higher, RubyGems, GCC and Make. Ruby comes pre installed in Linux and iOS but not in Windows. In order to see which ones I had installed I went into my command prompt (using Git Bash for me) and ented the following commands which produced the results following each command
</p>

```
$ ruby -v
bash: ruby: command not found

$ gem -v
bash: gem: command not found

$ gcc -v
bash: gcc: command not found

$ g++ -v
bash: g++: command not found

$ make -v
bash: make: command not found
```

<p align="justify">
<br>
<br>
Of course I didnt have any of those and needed to install each one
<br>
<br>
<u>Ruby Installation</u>
<br>
I first began by installing Ruby. In order to do this for windows, I went to the RubyInstaller for Windows site (https://rubyinstaller.org/downloads/). At the time of writing this, they recommended Ruby+Devkit 2.6.X (X64) so I downloaded the 2.6.6-1 version. I installed it and selected MSYS2 development toolchain as well.  After installation, I was ready to go!
<br>
<br>
<u>Download and Install RubyGems</u>
<br>
This was a lot simpler to do. First I restarted my Git bash and confirmed that Ruby was installed:
</p>
```
$ ruby -v
ruby 2.6.6p146 (2020-03-31 revision 67876) [x64-mingw32]
```

Next I entered the following command to download and install RubyGems

```
$ gem update --system
```
Once installation was complete, I entered the following to confirm installation

```
$ gem -v
3.1.4
```
<br>
<u>Downloading and Installing GCC and Make</u>
###
https://www.youtube.com/watch?v=78j-Gvx2MP0
###

GCC is a C code compiler (GNU Compiler Collection). For Windows I needed to download and install the MinGW C compiler located at the official MinGW website (http://www.mingw.org/). In the downloads section of their website you can download the setup file mingw-get-setup.exe Once it has been downloaded you can run the set up.

Open the file and click on the Install Button.

At the next step you are given the installation directory as well as some interface options. Since I am new to MinGW, at this time I had no reason to stray away from the default settings so I clicked continue.

The installer will download some files and take you to the installation manager. At the installation manager, select mingw32-base-bun as well as mingw32-gcc-g++-bin by right clicking each one and selecting Mark for installation. Once they have been selected, go to the menu on the top left section and click on Installation and select Apply Changes. Once the installation is completed, open an explorer window into your C drive. You will see a folder for MinGW confirming that it has been installed. If you go into the folder and then the bin folder, you will see your compliers that have been installed. Although the compiler has been installed, it has not been set up yet.

In order to be able to execute the compiler form your command prompt we need to update the path variable. Go into your windows search bar and type in variable and select "edit the system environment variables" once it appears. This will bring up the system properties window. Select the Advanced Tab and click on Environment Variables. This will open the Environment Variables window.

In the bottom section you will see a list of System variables. Click on the Path entry and click on the edit button to add a new path for MinGW. Click on New and enter the location of your MinGW bin folder. If you used the default installation, this should be "C:\MinGW\bin". In order to apply these changes, Click on the Ok button to close the edit window, Ok to close the Environment Variables window, and then Ok in the System Properties window. This will set up your GCC and G++ but we still have to finish setting up MAKE

###
https://www.youtube.com/watch?v=taCJhnBXG_w
###

Go back into your MinGW bin folder (C:\MinGW\bin) and look for a file named mingw32-make. Right click on the file to make a copy and paste it into your folder, the copy should be named mingw32-make- Copy. Right click the copy and rename it "make".

Now restart your git bash and confirm the installations by typing in the code below:

```
$ gcc -v
$ g++ -v
$ make -v
```

<br>
<u>Install Jekyll</u>
<br>

###
https://jekyllrb.com/docs/installation/windows/
###



Next we install Jekyll using the command (the install will take a few minutes)
```
gem install jekyll bundler
```

and testing it by entering

```
jekyll -v
```

<br>
<p align="justify">
Follow these steps and you can save yourself a little time!
</p>
