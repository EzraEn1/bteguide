Contributing to the Wiki
==========================

Prerquisites
------------

Before you can start translating this wiki you will need to install a few programms and set up your environment to interface with the github repository and collaborate with the wiki editors. You need the following programs:

**Python Version 3.6 or higher**

Python is a programming language. You do not need to know any python to help translating but we need the language installed to setup the environment.

You can find the download here `Python download <https://www.python.org/downloads/>`_. The `Hitchhiker's Guide to Python <https://docs.python-guide.org/starting/installation/>`_ has a short tutorial on how to install python properly using the command line.

**git**

git is a decentral version control system that allows you to synchronize changes in a folder with remote repositories. It also allows to revert changes and split off parts of a project in independent project-branches.

You can download it here `Git download <https://git-scm.com/downloads>`_. 

**A Github account**

Github is a webinterface for collaboration using remote git repositories. The wiki is created in a such a remote repository. you need to create an account to collaborate with the team.

Create an account here `Github <https://github.com/>`_.

**If you want to translate**

The translation of this wiki works internally by creating portable object (.po) files for each language. These files simplify the translation of web interfaces. To work with .po files we recommend a dedicated .po editor such as Poedit.

Download it here: `Poedit download <https://poedit.net>`_.

Whether you're translating or just adding new information, these will be your tools, so get familiar with them! If you need help getting set up, contact us in `#support <https://discordapp.com/channels/690908396404080650/691034211464773684>`_. If noone responds, DM ``@EzraEn#4291``.

We're using Sphinx with ReadTheDocs to run the Guide. For those unfamiliar with it, we suggest you look into the `basics of reStructuredText <https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html>`_. We do have the option for Markdown, however many features are not supported by it (e.g., tables, other common extensions), so going forward we will be investing in Sphinx.

Setting up the environment
--------------------------

After you created a Github account click the **Fork** buttom at the top right of the `bte-guide Github page <https://github.com/EzraEn1/bteguide>`_. This will create a copy of the whole wiki project on your own Github account. You can work on this copy without disturbing any of the things happening on the main wiki. If you are a translator and will work on a language for which a translation is already in progress you can also request your co-translator to accept you as a direct collaborator on their fork of the repository.

The next step is to create a clone of the fork on your computer. This clone will be an ordinary folder but it can be synchronized to both your fork and the main BTE wiki.
Click the green 'Clone or download' button on the top right and copy the link that appeard.
Go to the folder you want to work in.

**Windows**
Shift-right-click in the folder and open the command terminal/Powershell. A command line Window will open up.

**If you are using git for the first time** you need to register your name and your e-mail address. This is essential for your collaborators to identify which changes were made by you. Type in the following commands (middle mouse button is used to paste a copied text into the git console):

.. code-block:: 

    git config --global user.name "Your 1st and 2nd Name" 
    git config --global user.name

If everything is correct your username should be retured to you after the second command.

.. code-block:: 

    git config --global user.email "email@example.com"
    git config --global user.email

Again your e-mail address should be returned after the second command.

We can now **clone your github repository** and connect it to the main wiki for synchronization.

.. code-block:: 

    git clone [your link]
    git remote add upstream https://github.com/EzraEn1/bteguide.git

This downloads the repository into the folder you chose it will appear as a folder named **bteguide**. Run

.. code-block::

    cd .\bteguide
    pip -r requirements.txt

This will install all packages you need to work on the wiki.

Contributing to the wiki
------------------------

To contribute directly to the source files, find them in /source/. 
If you are looking to create a new document, make sure the corresponding ``index.rst`` for it's directory includes it in it's `toctree` directive. This applies whether you choose to write in Markdown or reStructuredText (preferred). You miht want to check out these resources.

Git/Github
~~~~~~~~~~
| Go through this first. Steps 1, 2, and 3 of **Setting Up Git** are all you really need to do, but if you'd like better security, you can go through the **Next Steps** if you'd like.
| https://help.github.com/en/github/getting-started-with-github/set-up-git
|
| See the **Github Flow** section, it's a pretty good overview if you've never used Git before.
| https://guides.github.com/introduction/git-handbook/#basic-git
| https://guides.github.com/activities/forking/
|
| If you use VSCode, I `highly recommend` using `GitLens <https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens>`_. Seriously. It helps. A lot. 

reST
~~~~
These are a few highly recommended resources we've found on getting started with reST/rST.

| https://docs.typo3.org/m/typo3/docs-how-to-document/master/en-us/WritingReST/CheatSheet.html
| https://stackoverflow.com/questions/2746692/restructuredtext-tool-support/2747041#2747041
| https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html
| https://docutils.sourceforge.io/docs/ref/rst/restructuredtext.html
| 
| If you're using VSCode (seeing a trend?) definitely install the `reStructuredText <https://marketplace.visualstudio.com/items?itemName=lextudio.restructuredtext>`_ extension.


Optional Quality-of-Life
------------------------

You can install ``sphinx-autobuild`` with the guide, though it only seems to be compatible with Python versions less than 3.8. We don't recommend installing an older version of Python just for that, but if you really want to, you can. If you find that the package `does work` with 3.8, please notify ``@EzraEn#4291`` as we'd like to see that as a default install. 

Installing sphinx-autobuild is as simple as ``pip install sphinx-autobuild``.
If you want to use live-reload, run ``make livehtml`` (or ``./make.bat livehtml``) and visit http://localhost:8000 to see your changes.