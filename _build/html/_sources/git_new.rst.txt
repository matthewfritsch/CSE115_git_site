Sprint 2-5 Information
=======================

New GitHub Structure
----------------------

- In our meeting with our TA Meg, we were told a different structure for GitHub could be helpful (or rather, how industry does it). 
- Starting with Sprint 2, this is the structure we're going to start following:
    - "production" is the new "master" branch. It's where we put our final, bug-free product at the end of each sprint.
    - "QA" is short for Quality Assurance. This is where we will test the product thoroughly for problems BEFORE pushing to production.
    - "dev" is our collection of completed tasks in a sprint. At the start of a sprint, it will have ZERO difference from the master branch. However, as each of us finishes a task, we will merge personal developer branches to the dev branch.
    - Personal branches ("MattSP2", "Matthew", etc.) are where we do our personal work. We will ALWAYS make our personal branches from the master branch in order to avoid conflicts with other pre-QA code. To see how a personal branch is created, see below.
- The above bullets detail what each branch is for. Our branch list should look something like:

.. code:: Bash

    matthew-pc: git branch -a
      Aaron
      Emmanuel
      Hector
    * Matthew
      Pierson
      QA
      dev
      production
      remotes/origin/HEAD -> origin/production
      remotes/origin/Aaron
      remotes/origin/Emmanuel
      remotes/origin/Hector
      remotes/origin/Matthew
      remotes/origin/Pierson
      remotes/origin/QA
      remotes/origin/dev
      remotes/origin/production

- Note, your personal branch name can have whatever format you want, but preferably it contains your name.

Sprint Starts
--------------

- When a sprint begins, there are only a couple things to do:
    - Make sure you have the latest version of EVERY branch!
    
    .. code:: Bash

        git pull --all

    - Make sure you know what your task is, and more importantly whether or not your task will have an effect on other people. For example, if your task involves editing Menu.unity, AND you know that everyone else has an old version of Menu.unity, then your push will have an affect on other people. Be cautious when making a pull request to avoid deletion of other people's work.

When You Begin Working On A Task
----------------------------------

- When you begin a new task, make a new branch from production. This will NOT include any of the changes made during the current sprint. 
- If you need work from this sprint, then it's okay to make a branch from dev, but try to avoid this while others are working on personal branches.

.. code:: Bash

    git checkout production
    git checkout -b Matthew

    (except obviously put your name instead c:)

- While you could wait to push upstream for later, it might just be easier to make it now:

.. code:: Bash

    git push --set-upstream origin Matthew



        
If You Stop Working On A Task For The Day (Incomplete)
-------------------------------------------------------
- If you stop working on a task for the day, that's bad. Just finish the whole task. What do you mean you have other responsibilities? Don't lie to me like that.
- Thanks for the pity laugh.


- Make sure to add, commit, and push to YOUR branch when done working on your task temporarily. 

.. code:: Bash

    git add *
    git commit -m "Added X feature, Y feature still in progress"
    git push

- The purpose of pushing to your personal branch is NOT to signify that the task is done, but rather to save your work on a remote space where others can pick it up if need be. If I wake up and find out my internet is not going to work through the end of the sprint, someone else would have to pick up my task, right? Making that person work completely from scratch is a huge waste of time, so please PLEASE: add, commit, and push often. Reach out to Matt if you want him to write you a script to make that work easier.


When You Complete A Task
-----------------------------------
- When a task is complete, pat yourself on the back. Once that's complete, follow the above steps to add, commit, and push changes to GitHub.
- Once it's all pushed, now you can merge your branch with dev on GitHub! To avoid concerns of deleting other people's work, follow this one easy solution:
    - Check the top right corner of your pull request "Conversation" and see if there are LOTS of deletions. It's likely that you added a bunch of lines, but tons of deletions usually screams "I'm deleting all of the work someone else did".
    - If this happens, that's okay. Let Matt know, or if you want a guide on solving the problem on your own, also let Matt know. He's happy to do it on his own, and this problem is pretty unlikely, but whatever works for you.
- IMPORTANT: After confirming the pull request merge, DELETE YOUR OLD BRANCH. There is a button right above the "Merge complete" text on GitHub that will let you delete the branch automatically. That works perfectly fine.
    - The reason we're no longer leaving code in our own branches is to avoid task overlap: Your personal branch should be solely representative of the production branch AND the current task you have.

