Now that Flox is installed machine, we can set up our reproducible development environment!

To start off we need to retrieve the project we will be working on. In this case, it's a simple Flask application, but we can imagine a huge monorepo with complex dependencies, environment variables and requirements.

Run the following to to clone the repository for the example project and move into the directory:

`git clone https://github.com/bjornthiberg/DD2482-executable-tutorial-project &&
cd DD2482-executable-tutorial-project`

We can now proceed to initialize our Flox environment for the project by running the following command: 

`flox init --auto-setup`

Flox will infer that we are working on a python project, and using the  `--auto-setup` option will automatically proceed to include a python installation in our environment.

Basically, `flox init` does the following:
- Creates a new Flox environment, with the same name as the directory.
- Creates a `.flox` directory with a few configuration files (which can be checked into source control!).
- Notices that we have a `requirements.txt` file, and provides us with a Python virtual environment.

We will take a closer look at the contents of the .flox directory later.

Now, let's get our environment activated and run our app!
