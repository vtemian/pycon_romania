README
======
This project (and its dependencies) contains the EuroPython website source code.

LICENSE
=======
As a general rule, the whole website code is copyrighted by the Python Italia non-profit association, and released under the 2-clause BSD license (see LICENSE.bsd).

Some CSS files (within directories `p3/static/p4/s` and `p3/static/p5/s`) are instead explicitly marked as non-free; those files implement the current EuroPython website design and Python Italia wants to keep full rights on it. They are still published on GitHub as a reference for implementing a new design.

You are thus welcome to fork away and reuse/enhance this project, as long as you use it to publish a website with a new design (without reusing the current EuroPython design).


INSTALL
=======

Project dependencies are stored in the file `requirements.txt` and can be
installed using `pip`.

Although not required the use virtualenv is highly recommended.

>>> virtualenv pycon-env
>>> source pycon-env/bin/activate
>>> pip install -r requirements.txt

SETUP
-----

When the install completes you must setup your pycon installation.

>>> cp pycon/settings_locale.py.in pycon/settings_locale.py

Edit `pycon/settings_locale.py` to your taste!

The next step is the database setup; the pycon site uses sqlite so the only
needed thing is to create the directory where the db will be placed.

>>> mdirk -p data/site
>>> ./manage.py syncdb
>>> ./manage.py migrate
