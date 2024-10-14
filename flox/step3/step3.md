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

Normally, we would probably use a Python package manager like pip. 

But, that would of course defeat the purpose of having an all-in-one dev evironment!

Let's learn how to do it the Flox way.
