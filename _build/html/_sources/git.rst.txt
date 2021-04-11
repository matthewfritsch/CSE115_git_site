How to do git stuff
====================

Getting Started
----------------
- We all know the URL of the git repo. I'm not gonna put it on here solely because this is the internet and it spoops me to put a personal, private repo online.
- To get started, go ahead and run 

.. code:: Bash

    git clone <url>

- This will clone the repository to your current directory.
- With the repository cloned, you can open the folder in Unity. Please be sure to hit "Add" in the Unity Hub instead of "New". **You do NOT need to make a Unity project, and copy the changes over.** That will 100% be more difficult.


Making your own branch
------------------------
- The "master" branch is where all of our final additions will go. We definitely don't want to make changes on that branch, because it will prevent others from getting work done.
- Instead, you want to make a personal branch and do your work there. Here's what I mean:

.. code:: Bash

    git branch <branch name>
    git checkout <branch name>

- Here is an example:
  
.. code:: Bash

    git branch MattSP1
    git checkout MattSP1

- This will let you start working in your personal branch. Please make sure that you set your branch BEFORE starting work, or you may end up losing some progress.
- After switching to your own branch, feel free to get your work done in Unity!

Pushing changes
----------------
- Once you feel your work is done, or you want to save your progress, go ahead and run the following commands:

.. code:: Bash

    git add *
    git commit -m "<a message of what you completed>"
    git push

- Here is an example:

.. code:: Bash

    git add *
    git commit -m "Implemented the data structure for containing player info"
    git push

- **NOTE**: I 100% expect you to get warnings when you use 'git add \*'. You can disregard the warnings, they're only warning you because they think you're trying to add stuff from the .gitignore, but you're not. 

When A New Sprint Starts
------------------------

- When a new sprint starts, it's important that you work from the latest changes. You can use the following to get the new changes:

.. code:: Bash

    git checkout master
    git pull
    git branch <new branch name>
    git checkout <new branch name>

- This will put you into a new branch, filled with all the latest completed changes from the project.

Problem Solving
----------------

- git push error
    - There is a chance, on your first "git push" that the repository isn't having it. That's because you made the new branch, but the repository is unfamiliar with it. To solve this, try:

    .. code:: Bash

        git push --set-upstream origin <branchname>

    - Following my above example:

    .. code:: Bash

        git push --set-upstream origin MattSP1

