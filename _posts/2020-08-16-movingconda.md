---
title: "Transferring Your Anaconda Environments to a new Machine"
date: 2019-05-16
tags: [Anaconda, Environments, Transferring]
header:
  image: "/images/asd/autism-awareness.jpg"
excerpt: "Anaconda, Environments, Transferring"
mathjax: "true"
---

# I got a new PC!
<br>
<p align="justify">
So I recently got a new PC and of course had to deal with the fun of moving all my existing programs and files to the new PC. So when it came time to reinstall Anaconda, I wanted to ensure I still had my previous environments and packages on my new machine.
<br>
<br>
You could go through the process of writing down the names of each package for each environment and then install each one individually, but that too long of a process and of course there's a faster way to do it.
<br>
<br>
<u>From Old Computer</u>
<br>
I went into my old computer and logged into the Anaconda Command prompt. There is a command you can use to save the list of packages as a list to use later. Using the command:

```
conda list --export > package-list.txt
```

a text file called "package-list" was created listing all the packages I have installed for the base environment. I also have a Tensorflow and an R environment and needed to do the same for each of those environments. My Tensorflow env is named tf and the R environment r-env.

```
conda list -n tf --export > tf-package-list.txt
conda list -n r-env --export > r-package-list.txt
```

The text files were saved in the root directory were your Anaconda was installed. This is the directory where your Anaconda Prompt will open up in. For me it's: C:\Users\MYUSERNAME. You can copy these files and transfer them over to the root directory of your new PC.
<br>
<br>
</p>

## Now the fun part
<u>From My New Computer</u>
<br>
Once the files were in my root directory I opened up my anaconda prompt again and entered the following code:

```
conda create -n tf --file tf-package-list.txt
```

This created my tf environment again and installed all the packages listed in the text file.

Next I entered conda create -n r-env --file r-package-list.txt, which created my R environment without a hitch.

So, I had one final task and that was to reinstall the packages from my base environemnt. The code was a little different:
```
conda install --file packagelist.txt
```

I was expecting an easy install like the previous two but I got an error msg. There were packages that were not found! Of course this may also happen to you in some of your other environment but I only saw this in my base. Packages that were not part of Anaconda and installed using PIP or even conda-forge had to be manually reinstalled. The error message will list which packages those were and will suggest you go to Anaconda.org and look up the packages.

I did this for most of my packages and used two PIP installs. Once my missing packages were installed, I went back to the packagelist.txt file and removed those packages from the list and saved the file.

I ran the code again conda install --file packagelist.txt, and now we had success! Follow these steps and you can save yourself a little time!
<br>
<br>
</p>
