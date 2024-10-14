As this Flox environment is used for developing our Flask app, we can preconfigure the manifest to simplify the development process.

# Vars
Under the `vars` section of the manifest, we can set local enviroment variables specific to our application.

As we are in a development setting, it would be useful to run our Flask application in `debug_mode` such that any changes made will be automatically loaded without having to restart the application.

Let us run `flox edit`{{}} and enter the following under the [vars] header:

```
[vars]
FLASK_ENV=development
FLASK_DEBUG=1
```

# Services
Flox also allows us to configure `services`, which are any long-running programs which are application are dependent on. Any programs or applications defined as `services` will automatically run when the Flox environment is activated.

For our scenario we can configure the manifest such that our Flask server, with our already defined environment variables, is up and running in debug mode when we activate the environment.

Let us run `flox edit`{{}} and add a Flask service under the [services] header:

```
[services.flask]
command = flask run
vars.port = 3000
```

As our Flox environment is already up and running, these services will not automatically start.

Instead we can run the command `flox services start`.

If we were to make further changes to the services defined in our manifest, we could also activate these changes by running the command `flox services restart`.

Finally, if we want to terminate our services we would run `flox services stop`

While our services are running, we can check their status by running the command `flox services status`.

If we instead want to view the logs of a given service we can run the following `flox services logs --follow`