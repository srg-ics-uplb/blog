How to contribute to this blog (Short Method)
############################################

:date: 2019-2-2
:modified: 2019-3-6
:category: HowTo's
:author: Joseph Anthony C. Hermocilla

This method is easier because the editing will be done in
github itself via the web browser.

**1. Fork the original repository**

`SRG Blog Repository <https://github.com/srg-ics-uplb/blog>`_

This is accomplished in github and you must be logged in. You should have 
the repository under your account after the fork. The succeeding steps will be done on this forked repo.

**2. Create your entries**

If this is your first entry, you must create an folder for your articles.

Navigate to  ``"contents/articles"``.

Click the ``"Create new file button"``.

Specify the file name of the first entry, say ``"clinton/clinton_001.rst"``.

You can begin writing your article. Save.

- `Adding content <http://docs.getpelican.com/en/3.6.3/content.html>`_

- `More on RST Syntax  <https://github.com/ralsina/rst-cheatsheet/blob/master/rst-cheatsheet.rst>`_

For your succeeding articles, you can go directly to your own folder and 
create the file there.


**4. Using images**


Navigate to  ``"contents/images"``.

Upload your image, say "code.png"

To use your image in the article:

.. code:: html

   .. image:: ./images/code.png

**3. Make a pull request**

If your article is ready to be published, make a pull request.
