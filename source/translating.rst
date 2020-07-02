Translating the Wiki
---------------------

Setting up for translation
~~~~~~~~~~~~~~~~~~~~~~~~~~

To begin to translate the wiki into a language you first need to find out if a translation into that language is already in the process of being translated.
Each language is translated in its own language branch (A branch is like a separated version of the project that is used to create features without disturbing the integrity of the hole project). 

the name of a language branch is `lang-xx` where xx is the `Language code <https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes>`_ as listed under the 639-1 column.

Open the command terminal inside of your **bteguide** folder and run ``git checkout lang-xx`` if the language is already in the process of being translated the output will tell you that you are now on the lang-xx branch.

If your target language hasn't been started on yet, you can create the branch yourself by running:

**Windows:**

.. code-block::

    git checkout -b lang-xx
    ./make.bat gettext
    sphinx-intl update -p build/gettext -l xx

**Linux/Other:**

.. code-block::

    git checkout -b lang-xx
    make.bat gettext
    sphinx-intl update -p build/gettext -l xx

Working on the translation
~~~~~~~~~~~~~~~~~~~~~~~~~~

Once that's done, you will find the .po files in /locale/xx/.

**A workflow example**

     #. **Synchronizing the repository before starting to work:**
        The first thing to do before you start the day or (if you are translating into multiple languages) to switch languages is to synchronize your local copy of the repository to the remote master file. This will download all changes that have been made by your collegues.
        Open your command terminal in the **bteguide** folder and run:
        
        ..codeblock::

          git checkout lang-xx 
          git pull origin\lang-xx
          sphinx-intl update -p build/gettext -l xx

        Where `xx` is the language code of the language you want to work on.
        
        Now your .po files are up to date. 

     #. **Working with Poedit**
        Explaination (probably a link to a detailled explaniation)

     #. **Staging and Commiting changes**
        
        After you have worked on a .po file and made your translations you need to store your changes in a commit. Commits are progress packages that enable us to revert to any former version of the project if anythin goes wrong.
        Save the changes in the file and then open your command terminal in the folder.

        ..codeblock::

           git add [filename]
           git commit -m [commit message]

        The commit message should be a max 50 character explaniation of what changes you made e.g. ``First translation of index.po`` or ``Spellcheck discord.po``. These messages help to track changes so it is encouraged to add and commit after every finished task (e.g. a translated file) and before going on to the next tasks as well as when you finish working at the end of the day. It is better to commit once to often than not enough. These commits are saved locally on your computer and are not visible for collaborators.
        
     #. **Publishing/Pushing changes to the fork and the main wiki project**
        
        Finally, you need to make your commits available for collaborators. For this you need to push your commits onto a Github repository. Your commits will bis pushed onto your personal project fork first:

        ..codeblock::

           git pull lang-xx
           git push lang-xx

        This will update your changes to the fork. If everything goes correctly you should see a message on your Github account showing your last commit message. You can push your progress at any time during the process to update the remote repositories (be aware that only the changes that you commited earlier will be uploaded).

        To get your changes updated on the main project you need to do a pull request on Github. Open your Github fork and click the green `Pull Request` button. You have to write a short message about what changes you have made and submit the pull request. Your pull request will be accepted by the main wiki editors.
