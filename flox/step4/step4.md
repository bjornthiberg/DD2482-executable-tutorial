Adding a dependecy to our environment was quite easy, right?

Let's add another one so we can better process the API data. This one will not be related to Python, to highlight the universal nature of Flox as a package manager.

`jq` is a great tool for processing JSON formatted data. This could of course be installed using brew, apt, or any other package manager, however with Flox we can bundle `jq` with the rest of the development environment to enable our fellow developers who also work on this project to have direct acces to it.

First, let us see what packages Flox has available related to jq:

`flox search jq`

As we can see from the description, the first option is the JSON processor we want to install.

Next, let us see which versions are available in the Flox repositories.

`flox show jq`

We could now install the default (latest) version, but let's instead choose a specific version of the package by adding a `@version`:

`flox install jq@1.7.1`

To confirm that we have installed jq correctly, run the following command to see that it is in our $PATH.

`which jq`

Now we can use jq as a JSON processor to better consume our API data:

`curl http://127.0.0.1:3000/api | jq`

As a next step, let's look into how the flox environment files are structured.
