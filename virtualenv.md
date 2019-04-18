# virtualenv

So you have Python installed. Now, you should probably create a virtual environment, a.k.a. virtualenv, especially if you intend to work on multiple Python projects.

Rationale: You can easily come up with ```requirements.txt``` just with the command ```pip freeze > requirements.txt```. This is apparently not the best practice, due to deprecated dependencies not being removed, but even if you choose to manually create ```requirements.txt```, you can get a clearer view of the dependencies' versions through ```pip list```. If you install all the dependencies in the base Python installation, you can easily have over 50 packages installed. Maintaining them would be a pain.

To get a virtualenv up and running is simple.

### Step 1: Installing virtualenv
Run ```pip install virtualenv```, and pip will do its job.

### Step 2: Creating a virtualenv
You can name it anything you want, but typically a simple name like env or venv will do.

Run ```virtualenv env```. A virtualenv with the name ```env``` will be created in the current directory. Any packages you install in ```env``` will be stored in ```env/Lib/site-packages```.

### Step 3: Activating your new virtualenv
Technically, you do not _have_ to activate the virtualenv, but activation brings about all the convenience you'll need. Plus, you don't want to be accidentally doing things to your base Python installation.

Just run ```.\env\Scripts\Activate``` for Windows, or ```source env/bin/activate``` for Mac OS/Linux.

You should see ```(env)``` prefixed to your console command line. That means you're in!

### Step 3.5: Exiting the virtualenv
To leave the virtualenv, simply run the ```deactivate``` command.
To re-enter the virtualenv, repeat Step 3.

### Step 4: Installing packages
Installing packages in a virtualenv is no different from installing them outside of a virtualenv. Simply ```pip install packagename``` and let the magic happen. For packages not hosted on PyPI, check out the post on [installing packages not on PyPI](https://humanivore.github.io/python-things/installing-packages-not-on-pypi).

For installing from a ```requirements.txt``` file, the command is ```pip install -r requirements.txt```. The ```-r``` flag denotes reading from a requirements file. The requirements file can have any filename, but they're usually ```requirements.txt```. [Here](https://pip.pypa.io/en/latest/user_guide/#requirements-files)'s more on requirements files.

### Step 5: Do your thing
Now that your virtualenv should be properly set up, you can do whatever you need with it. Write code, run your new Python program, destroy it, or something.

##### Other common operations
Running Python interactive console: ```python```
Uninstalling packages: ```pip uninstall packagename```

### Step 6: Deleting the virtualenv
If you're sure you've done everything you want with this virtualenv and you won't use it anymore, it can be deleted by deleting the virtualenv folder. Interestingly enough, if you don't ```deactivate``` before deleting the folder, you can still run commands like ```python``` and ```pip install```. However, they will be referencing the _base_ python installation, so it is highly discouraged. Experimenting is always welcome, though :)
