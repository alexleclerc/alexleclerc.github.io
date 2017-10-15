# Homework 1 (CS460)

For the first homework we were asked to learn the basics of HTML and CSS, using git from the command line, and using Bootstrap for the layout. Luckily, I had some previous experience with HTML, CSS, and GitHub. 

I was unfamiliar with Bootstrap and the command line version of git, so I spent the most time figuring out how to make a nice layout with Bootstrap.

### Step 1: Command Line Git, Accounts
Over the summer I made a GitHub account and used the GitHub GUI, but I hadn't used the command line version so I had to download that from [Git-scm](https://git-scm.com/). 

*I am on a windows machine, but only use the Windows Command line when forced to, so I use the Git Bash with Linux commands.*

```
git init
git add . 
git commit -m "First commit."
```

I accidently did this the hard way, by starting my project in a local repository and then having to set the Remote repository and link the two. I used the documentation on [this page](https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/) as a guide.  
```
git remote add origin https://github.com/alexleclerc/CS460.git
git -v 
origin  https://github.com/alexleclerc/CS460.git (fetch)
origin  https://github.com/alexleclerc/CS460.git (push)
```
Later I made my remote repositories on github and just cloned them on my machine.