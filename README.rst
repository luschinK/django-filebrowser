Django FileBrowser WebP
==================

A little modification to Django FileBrowser to handle webp formats with versions.  

* You need *libwebp-dev* package (Ubuntu/Debian). Reinstall Pillow if it was already installed.

How to use it
---------------
In your FILEBROWSER_VERSIONS settings, add the 'webp' option as True to any version you want, just like this:

    'big': {'verbose_name': 'Big (6 col)', 'width': 660, 'height': '', 'opts': ''},  
    'big_webp': {'verbose_name': 'Big (6 col)', 'width': 660, 'webp': True},  
    
Then, in the template, you can use it like this (pug syntax):

        picture
            source(type="image/webp", srcset="{% version image 'big_webp' %}")  
            source(srcset="{% version image 'big' %}")  
            img(src="{% version image 'extra_large' %}")  
            
Known Issues
---------------
* The supported formats are: ".jpg",".jpeg",".png" . However, if you try to convert a .png image to .webp sometimes the image gets broken, mainly when .png has transparent layers. (These layers turn black)

Original Django FileBrowser README
===============

**Media-Management with Grappelli**.

The FileBrowser is an extension to the `Django <http://www.djangoproject.com>`_ administration interface in order to:

* browse directories on your server and upload/delete/edit/rename files.
* include images/documents to your models/database using the ``FileBrowseField``.
* select images/documents with TinyMCE.

Requirements
------------

FileBrowser 3.11.1 requires

* Django 2.1 (http://www.djangoproject.com)
* Grappelli 2.12 (https://github.com/sehmaschine/django-grappelli)
* Pillow (https://github.com/python-imaging/Pillow)

Documentation
-------------

http://readthedocs.org/docs/django-filebrowser/

Translation
-----------

https://www.transifex.com/projects/p/django-filebrowser/

Releases
--------

* FileBrowser 3.11.1 (November 2nd, 2018): Compatible with Django 2.1
* FileBrowser 3.10.2 (November 2nd, 2018): Compatible with Django 2.0
* FileBrowser 3.9.2 (November 2nd, 2018): Compatible with Django 1.11

Current development branches:

* FileBrowser 3.11.2 (Development Version for Django = 2.1, see Branch Stable/3.11.x)
* FileBrowser 3.10.3 (Development Version for Django = 2.0, see Branch Stable/3.10.x)
* FileBrowser 3.9.3 (Development Version for Django = 1.11, see Branch Stable/3.9.x)

Older versions are available at GitHub, but are not supported anymore.
Support for 3.10.x and 3.9.x is limited to security issues and very important bugfixes.
