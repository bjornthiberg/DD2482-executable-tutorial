
We are going to install Flask as a package from the Flox Catalog (which uses [nixpkgs](https://github.com/NixOS/nixpkgs) behind the scenes).

As it uses the Nix, we have access to over 100 000 packages, and Flask is no exception. With Flox, we can ditch our Python package manager for something that works universally across all languages!

To do this, we search for the Flask package using the built-in search functionality:

`flox search flask`

We get several options, but as we are using python 3.12, it makes sense to install the corresponding Flask package:

`flox install python312Packages.flask`

We get a response from flox that Flask was installed to our environment. 

Now, let's run the Flask application again. This time, we also append a '&', so that we can have it run as a background process:

`python run.py &`

Let's double-check that the server is up and running, by sending a request to **ANY** of the api endpoints:

`curl 127.0.0.1:3000/api`

If everything worked correctly, you should now see a response from the Flask API!

Now, let's see how we can add a completely new package, outside of Python.
