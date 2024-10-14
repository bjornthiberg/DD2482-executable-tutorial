Now that we've seen Flox in action, let's take a look at how it organizes an environment in a clean way.

Let's have a look at what is inside the .flox directory. To do this, we can use the "tree" command to get a prettier view.

It's not available by default on Ubuntu, but of course we can install it as a Flox package!

`flox install tree`

Now, let's run it to get a view of the structure of the .flox directory:

`tree .flox -L 2`

Here we have some logs and the cached python installation. We can also see a symlink hinting to the fact that Flox uses interacts with Nix behind the scenes.

However, most important from a user's perspective is this:

- env/manifest.toml
- env/manifest.lock

This is a declarative manifest in TOML format and its lockfile. Together, they can be used to reproduce the environment on another machine.

For example, what we have done so far will have added something like this to under the [install] header:

```ini
[install]
python3 = { pkg-path = "python3" }
flask.pkg-path = "python312Packages.flask"
jq.pkg-path = "jq"
jq.version = "1.7.1"
tree.pkg-path = "tree"
```

The manifest can be edited with `flox edit`. You can read more about the specific contents of the manifest file [here](https://flox.dev/docs/concepts/manifest/).
(Running `flox edit` will open vim, a command line editor which can be tricky for newcomers. If you get stuck in vim there are some instructions in the following step)

Let's move on to looking at a case where we directly edit the manifest, by exploring how environment variables and services are managed in Flox!
