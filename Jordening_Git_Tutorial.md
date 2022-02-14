## **Version Control Systems: Using Git**

This is a basic tutorial that allows individuals to get comfortable with the basic functions of Git. This tutorial does not explain how Git be used with a remote repository such as Github. It is simply to teach an individual how to use the basic functions of Git to track changes made throughout their own personal projects that will be edited on a local repository. 

### What is it and why use it?

Before we get into the tutorial, it will be beneficial to understand what a version control system is (in this case Git), why it is useful, and how it works. In general, version control systems are used to track the changes made to the source code over time. This is done by committing substantial changes periodically to the Git repository. That way, if an error occurs while working on the project, the code can be reverted to an earlier state. 



One of the other main benefits of using a version control system is that it allows for an easy means of collaborating on a project. Through branching and merging, members of a group can make changes in their own local repository, review these changes, and then filter through which of those changes will be committed to the source code and stored in a remote repository (such as Github) – while also being able to check whether or not there are conflicts across the committed versions.

### How does it work?
There are three different areas Git uses to track your changes.

**Working Tree**

The Working Tree simply consists of the current directory you are in and the files that it contains. 

**Staging Area**

After making some edits to your project, files can be added to the Staging Area (using the git add command). The files in the Staging Area will sit and wait to be committed. This allows you to maintain organization by breaking down large edits into smaller commits. 

**Git Repository**

Git creates an empty repository in which all committed versions of the project can be saved. Changes made to your project will not be committed to the .git repository until you actually run the git commit command (which we will see later). These commits can be accessed from the repository at any point in your work. That way, if you have an idea that didn't work out as planned or if something goes wrong you can access an earlier committed version of your project.

## ***Tutorial***

This tutorial will cover the basic functions of Git in order that it might be used for version control in personal projects.

To demonstrate how it works, we will be making changes to a basic python project.


**Changing Directories**

Once you are in your command-line editor, the first thing you will want to do is change your directory to the one that you will be working in. This can be done on Mac in Terminal by using the cd command. 

`$ cd <directory/directory_pathname> `


For this tutorial I will be working in a directory that I have on my desktop called "Tutorial." Within this directory I have an empty python project. I will open an empty terminal shell and change my directory to my "Tutorial" folder by using the command:

`$ cd /Users/calebjordening/Desktop/Tutorial `


**Initializing a .git Repository**

Now, we will start using Git. The first thing you want to do is initialize a git repository (if you have not done so already in the past). This can be done by using the command:

`$ git init`

It should say that you have "initialized empty Git repository in..." and then the current directory.

It is important to note that the .git repository is a hidden repo. You can confirm that it is there by typing 
`ls -a ` into the CLE.

Congratulations! You have successfully initialized your first Git repository. You can now start using Git!

**Observing the Working Tree**

The files currently in the directory will be listed by Git as "untracked." This can be seen by running the:
`$ git status` command. 



<img width="568" alt="Working Tree" src="https://user-images.githubusercontent.com/99101887/153798029-4119a0c6-fb6e-498d-8853-669166725925.png">



As you can see, I have two files. The important one being the Tutorial.py, which will be tracked using Git after making changes to it.

**Adding a File to the Staging Area**

Alright, so say you want to create your first backup/copy of your project before making any edits. This will be done by adding a file to the Staging Area. To add a file to the staging area, type ` git add <file_name>`

In my case, I will type `$ git add Tutorial.py`

To confirm that the file was added, use the `$ git status` command again, and you will see that there are "changes to be committed." Tutorial.py has been successfully added to the Staging Area, and is waiting to be committed. 

**Making Your First Commit**

It's time for your first commit! To finally add your project to the Git repository, we must run the commit command. The simplest way of doing this is by entering: `git commit -m "<enter your message here>" `. 

The message is necessary and very important to add – as it allows for you to recollect what changes were made within the commit. Be descriptive, but also keep it brief! 

As for the example project, all that is in my Tutorial.py file for this first commit is the function "print("Hello World!")" This is what has been saved into the git repository. While working on projects, you want to be committing backups to the repository after you've made substantial progress/changes.


**Making Changes**

Let's say you would like to edit or add some new features to your code. Go ahead and make these revisions. Once you are done making your changes, type `$ git status` and notice how it says "modified" next to your project file. This just signifies that changes have been made since your last commit.

For my example, since the "print("Hello World")" commit, I have added two other print functions signifying the changes that might be made in an actual project. 

<img width="1203" alt="Changes" src="https://user-images.githubusercontent.com/99101887/153798056-22c48c5e-75fc-4496-9469-f62e55aaacd2.png">


And as you can see here, Git is telling me that the Tutorial.py file has been modified since my last commit.

<img width="566" alt="Changes2" src="https://user-images.githubusercontent.com/99101887/153798070-c487c233-ceba-4d1b-90a7-4f67790722da.png">


I will then go ahead and make another checkpoint in the git repository by adding the modified file to the Working Tree using `$ git .add <file_name>` again, and then commit these changes with another message.

**Getting Back to an Earlier Commit**

Hypothetically, let's say that these changes that you made prove to be not needed for some reason, and you really want to get back to how things were in your first commit. With Git, this is made completely possible!

By entering `$ git log`, you will see that you can see all of the commits you have made. In my example you can see how it lists the two commits I have made so far.



<img width="569" alt="Log" src="https://user-images.githubusercontent.com/99101887/153798098-247a94d0-ee85-494e-8730-f5335d5b40fe.png">



As you can see, there are hash codes in an olive color next to "commit." These hash codes can be used to access earlier committed versions of the project. To get back to my first commit that only has "print("Hello World!")", We can use the hashcode next to our first commit and enter:

 `$ git checkout <Hashcode>`
 

**Detached Head State?**

After inputting the command you should receive an odd message saying that you are entering a "detached HEAD state." 
<img width="566" alt="Detached Head" src="https://user-images.githubusercontent.com/99101887/153798112-2b958d3f-cefd-4c39-9ba4-dfe7c4e1d0ee.png">


Do not panic! The HEAD in Git acts as a reference to let you know where in the repo you are currently at. Everytime you make a new commit, the HEAD updates and points to that commit. By pointing to the most current commit, the HEAD is considered "attached." All we've done is moved back a commit, and so the head is "detached" from the most recent commit and is pointing towards an earlier commit. 

Most importantly, if you look back at your project's code, you will see that it has reverted back to how it was after the first commit!

<img width="1212" alt="Revert" src="https://user-images.githubusercontent.com/99101887/153798152-715a6dd0-a318-4569-a4e1-9ae4a05099a0.png">


**Getting Back to Latest Commit**

If you would like to get back to your latest commit and exit out of the ever-so-frightening detached head state, you can enter:

`$ git reflog`

This will bring up all of the commits and their subsequent hashcodes as seen below:


<img width="560" alt="Reflog" src="https://user-images.githubusercontent.com/99101887/153798166-f4217df0-cc0d-4eb9-9356-30a20113e2ed.png">

To get back to the latest commit, simply use the checkout command again with the desired commit hashcode.


**Branching**

Now let's say that you want to try something completely experimental. You have no idea whether or not it's going to work; however, you want to try it. This brings up the concept of branching. So far, we have been making changes to what is called the "master branch." If all of the changes on the master branch are finalized, and you would like to try and experiment with something, you can essentially create a separate timeline (or branch) on which you can freely make changes *without* altering the finalized stuff whatsoever. This is useful because if you don't like the changes or if the changes you made don't get approved, you can simply delete the branch. Otherwise if you do like them or if they are approved, you can easily merge the experimental branch with the master branch and easily add those changes to the project. 


To create a new branch all you have to do is enter:

`$ git branch <branch_name>`

In my example, I am creating a new branch called "Experiment." To move from the main branch to the new (in my case) "Experiment" branch enter:

` git checkout <branch_name>`

After doing so, the CLE should say "switching to branch" and then the name of the branch. Now you are able to freely make changes to this new branch, *without* altering what is on the main branch (yet).



**Merging** 

Now that we are on a new branch, we can start making our experimental changes. This will be reflected by the "print("woah look, I am experimenting with some changes")" function added to the python Tutorial file. Within this branch we can add the file to the Staging Area and make commits just like normal. These commits will only be visible on the branches they were created on. 

Let's say we do not like the changes. Move back to the master branch via the git checkout command. Then the branch can be deleted by entering:

`$ git branch -d <branch_name>`

If we do like the changes, go ahead, add and commit them. Once this is done, we can merge these new changes into the master branch. First switch back to the master branch via the checkout command. *Notice that when you switch back to the master branch, that the changes made in the experimental branch are gone from your source code.* Next, simply enter:

`$ git merge <name_of_branch_to_be_merged>`

Now, the changes made in the Experiment branch have been added to the master branch. By using the `$ git log` command, you can see that the commit from the experiment branch is also visible on the master branch. 


**Stashes**

In a similar vein, stashing is another way of storing changes made without affecting the master branch. Let's say you are working on an experimental portion of a code, but then you realize that there is a bug in another part of your code. You can use the stash command which will store everything that has been done since the last commit and clean/revert the Working Tree of that branch back to how it was during the last commit. This is done by entering:

`$ git stash`

That way you can fix the bug in your code and make a separate commit with a message indicating you have fixed the bug. Then you can retrieve the stashed code to prep it for its own commit. To retrieve the stashed code, simply enter:

`$ git stash apply`

This will re-insert the code that was stashed so that you can continue making changes.


## **Conclusion**

Although the functions that enable Git to be used as a collaborative tool were not thoroughly mentioned (i.e. cloning a remote repository to a local repository, pushing and pulling, etc.) this tutorial demonstrates how useful Git and other VCS's can be for securely tracking changes to a project made on a local repository, along with many other benefits.
