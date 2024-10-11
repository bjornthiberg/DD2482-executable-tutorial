We want to get up and running with our new shiny Flox environment.

To do this, run the following command. It will activate the Flox environment stored in the current directory, if one exists:

`flox activate`

You will notice that the terminal prompt changes to include "flox" and the environment name.

As a first test, we will see if our Python environment was created properly. Let's check what "python" currently points to:

`which python`

As you can see, the python executable used by our shell is located inside the local .flox directory, rather than using a global python installation.

Now, inside our flox environment and with our local python installation, let's run our Flask app!

`python ./run.py`

Woops, we got an error?! Looking more closely, it looks like the Flask module is not installed:

```bash
ModuleNotFoundError: No module named 'flask'
```

This makes sense, as we have only installed a Python environment, we haven't touched any other dependencies yet.

What would we normally do in such a situation? Well, we have a requirements.txt file which we can use with a Python package manager such as pip. But that would of course defeat the purpose of having a ready-made dev evironment!

Instead, we are going to install Flask as a package from the Flox Catalog (which uses [nixpkgs](https://github.com/NixOS/nixpkgs) as an input).

With Flox, we can ditch our Python package manager for something that works universally across all languages!

To do this, we search for the Flask package using the built-in search functionality:

`flox search flask`{{exec}}

We get several options, but as we are using python 3.12, it makes sense to install the corresponding Flask version:

`flox install python312Packages.flask`{{exec}}.

We get a response from flox that Flask was installed to our environment. 

Now, let's run the Flask application again. This time, we append a '&', so that it runs as a background process.

`python run.py &`{{exec}}

Let's double-check that the server is up and running, by sending a request to the api:

`curl 127.0.0.1:3000/api`{{exec}}

If everything is up and running, you should see a response from the Flask API!
