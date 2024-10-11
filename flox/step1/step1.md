First of all, let's download Flox, since that will take a while. Click the following command to run it:

`sudo wget https://downloads.flox.dev/by-env/stable/deb/flox-1.3.3.x86_64-linux.deb && sudo dpkg -i ./flox-1.3.3.x86_64-linux.deb`{{exec}}

While we wait for that to finish, let's get to know Flox. 

**Flox** is a tool that acts as both a virtual environment manager and package manager. With Flox, you can create isolated, reproducible development environments, where all the necessary dependencies for your project are automatically provided and configured. You can then share and version control these environments, for a team or for yourself. 

Flox environments are not just isolated but also portable across architectures, operating systems, and the entire software lifecycle — from development to production. This makes Flox a powerful solution for managing complex environments that require seamless transitions across different stages of the development process.

In this tutorial, we are going to integrate into a small project, manage dependencies, and how we would add new ones.

When the installation is complete, run the following command to check that flox is installed properly:

`flox --version`

Which should output the installed flox version:

```
$ flox --version
1.3.3
```

