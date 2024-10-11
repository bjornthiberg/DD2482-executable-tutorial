Now, to get our new Flox environment up and running.

To do this, run the following command. It will activate the Flox environment stored in the current directory, if one exists:

`flox activate`

You will notice that the terminal prompt changes to include "flox" and the environment name. This tells us that the environment is activated.

Let's see if the Python environment was created properly. See what "python" currently points to:

`which python`

As you can see, the python executable used by our shell is located inside the local .flox directory, rather than using a global python installation.

Now, inside our flox environment and with our local python installation, let's run our Flask app:

`python ./run.py`

Woops, we got an error! Taking a closer look, it appears our Flask module is not installed:

```bash
ModuleNotFoundError: No module named 'flask'
```

This makes sense, as we have only installed Python, we haven't touched any other dependencies yet.

Normally, we would probably use a Python package manager like pip. But that would of course defeat the purpose of having an all-in-one dev evironment!

Instead, we are going to install Flask as a package from the Flox Catalog (which uses [nixpkgs](https://github.com/NixOS/nixpkgs) behind the scenes).

With Flox, we can ditch our Python package manager for something that works universally across all languages!

To do this, we search for the Flask package using the built-in search functionality:

`flox search flask`

We get several options, but as we are using python 3.12, it makes sense to install the corresponding Flask package:

`flox install python312Packages.flask`

We get a response from flox that Flask was installed to our environment. 

Now, let's run the Flask application again. This time, we also append a '&', so that we can have it run as a background process:

`python run.py &`

Let's double-check that the server is up and running, by sending a request to the api:

`curl 127.0.0.1:3000/api`

If everything worked correctly, you should now see a response from the Flask API!

Now, let's see add a new package.
