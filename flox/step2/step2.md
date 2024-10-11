Now that Flox is installed on your machine, you can set up your reproducible development environment.

To start off we need to retrieve the project you and your dev team are working on. In this case, it's a simple Flask application, but we can imagine a huge monorepo with complex dependencies, environment variables and requirements.

Click the following to to clone the repository for the example project:

`git clone https://github.com/bjornthiberg/DD2482-executable-tutorial-project &&
cd DD2482-executable-tutorial-project`{{exec}}

We can now proceed to initialize our Flox environment for the project by running the following command: 

`flox init --auto-setup`

Flox will infer that we are working on a python project, and using the  `--auto-setup` option will automatically proceed to setup a new python virtual environment.

Basically, `flox init` does the following:
- Creates a new Flox environment, with the same name as the directory.
- Creates a `.flox` directory with a few configuration files (which can be checked into source control!).
- Notices that we have a `requirements.txt` file, and provides us with a Python virtual environment.

We will take a closer look at the contents of the .flox directory later.

Now, we want to get our environment activated and run our app!
