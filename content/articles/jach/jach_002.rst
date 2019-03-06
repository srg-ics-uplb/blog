How to contribute to this blog
#########################################

:date: 2019-2-1
:modified: 2019-3-5
:category: HowTo's
:author: Joseph Anthony C. Hermocilla


Contributions are encouraged from SRG members.

**1. Set up the development environment**


.. code:: shell

   $ virtualenv pelican-blog-venv
   $ source pelican-blog-venv/bin/activate
   $ pip install pelican markdown ghp-import

**2. Fork the original repository**

`SRG Blog Repository <https://github.com/srg-ics-uplb/blog>`_

This is accomplished in github and you must be logged in. You should have 
the repository under your account after the fork.

**3. Clone the repository from your account**

.. code:: shell

   $ git clone https://github.com/<YOUR_USERNAME>/blog.git

**3. Configure a remote for your fork**

.. code:: shell

   $ git remote -v
   $ git remote add upstream https://github.com/srg-ics-uplb/blog.git   
   $ git remote -v

`Help: Create a remote  <https://help.github.com/en/articles/configuring-a-remote-for-a-fork>`_

**4. Sync your fork with the upstream**

.. code:: shell

   $ git fetch upstream
   $ git checkout master
   $ git merge upstream/master

`Help: Sync from upstream <https://help.github.com/en/articles/syncing-a-fork>`_

**5. Create your blog entry**

At this point you are ready to write your entries. Create your own directory inside 
content. You're going to place all your entries in this directory.

.. code:: shell 

   $ mkdir -p content/<YOUR_NICKNAME>

For example, the source for this entry is `here <https://raw.githubusercontent.com/srg-ics-uplb/blog/master/content/jach/jach_002.rst>`_.

If your entry has images, place them in the images directory,

**Additional Resources**

- `Adding content <http://docs.getpelican.com/en/3.6.3/content.html>`_

- `More on RST Syntax  <https://github.com/ralsina/rst-cheatsheet/blob/master/rst-cheatsheet.rst>`_

.. image:: ./images/jach/srg.png
   :width: 60pt

