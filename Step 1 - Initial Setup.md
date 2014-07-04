django CMS Tutorial - Step 1
============================
Good to see you! Now let's get started by setting up our environment.

Preparing your workstation
--------------------------
In order to keep an overview about view packages are installed, we create a virtual environment for every project. Make sure you have the latest version installed:

```bash
$ pip install --upgrade virtualenv
```

Installing the CMS
------------------

### Make a project folder

Go back to your workspace and create a new folder for this project:

```bash
$ cd ~/workspace    
$ mkdir demo && cd demo
```

### Setup virtual environment

Let's set up the virtual environment and install [`aldryn-installer`](https://github.com/nephila/aldryn-installer):

```bash
$ virtualenv env
$ source env/bin/activate
(env) $ pip install "git+https://github.com/nephila/aldryn-installer#egg=aldryn-installer"
```

> ***Note:*** If you're using Windows, activate the virtual environment by doing this instead:
> ```bat
> > env\Scripts\activate
> ```

### Install django CMS

We're now about to install django CMS. We'll do that using the previously installed `aldryn-installer` since it's easy and hassle-free. Just follow the interactive wizard, don't worry if it takes a while :)

```bash
(env) $ aldryn -p . my_demo
```

> ***Note:*** Again, if you're using Windows you'll have to make sure your python files are associated correctly. Open up a shell with admin rights:
> ```bat
> C:\Windows\system32> assoc .py=Python.file
> .py=Python.file

> C:\Windows\system32> ftype Python.File="C:\Users\Username\workspace\demo\env\Scripts\python.exe" "%1" %*
> Python.File="C:\Users\Username\workspace\demo\env\Scripts\python.exe" "%1" %*
> ```

Feel free to answer the questions to your liking, but please note that this tutorial was designed after the following setup. If you chose other settings, it may not always quite fit! To be on the safe side, just use the settings below:


```bash
$ Database configuration (in URL format) [default sqlite://locahost/project.db]: [ENTER]
$ django CMS version (choices: 2.4, stable, beta, develop) [default stable]: develop
$ Django version (choices: 1.4, 1.5, 1.6, stable) [default 1.5]: 1.6
$ Activate Django I18N / L10N setting (choices: yes, no) [default yes]: [ENTER]
$ Install and configure reversion support (choices: yes, no) [default yes]: [ENTER]
$ Languages to enable. Option can be provided multiple times, or as a comma separated list: en,de
$ Optional default time zone [default America/Chicago]: Europe/Zurich
$ Activate Django timezone support (choices: yes, no) [default yes]: [ENTER]
$ Activate CMS permission management (choices: yes, no) [default yes]: [ENTER]

Creating admin user
$ Username: admin
$ Email address: email@example.com
$ Password: admin
$ Password (again): admin
```

### Let's run it

That's it! The installer took care of setting up your whole environment, you're now ready to start the server:

```bash
(env) $ python manage.py runserver
```

Now you can open [http://localhost:8000/](http://localhost:8000/) and should be presented with your brand new django CMS homepage!

Congratulations, you now have a fully functional CMS! Awesome job!

To log in, append `?edit` to the URL and hit enter. This will enable the toolbar, from where you can log in and manage your website. Switch to Draft Mode to add and edit content!

Try to switch between Live and Draft view, between structure and content mode, add plugins, move them around and delete them again. Go mess with it and see how awesome it is!

In the next step we're going to have a look at Templates & Placeholder: [Step 2 - Placeholder.md](https://github.com/Chive/djangocms-tutorial/blob/new/Step%202%20-%20Templates%20%26%20Placeholder.md)
