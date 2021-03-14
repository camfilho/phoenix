
## Directory Structure

_build - This directory is where the compiled files of your project goes to. Deleting it will cause your whole project to be rebuilt from scracth.
It must not be versioned so you have to add it to the .gitignore if it was not already done.

assets - As the name already suggests, this is the directory that keeps all the front-end related files. So all your CSS, JavaScript, static images goes into it. By default, it is handled by npm tool. Once you run npm instlal into it, Phoenix will take care of the rest.

config - It takes care of the whole project configurations.

deps - Short for dependencies, this is the directory in which all the dependencies lies. You can find all the dependencies listed in mix.exs file. This must not be versioned and deleting it cause to Mix download all over againg.

lib - This directory holds your application source code. Usually you can fild two sub-directories. lib/application_name and lib/application_name_web.
The former holds your business logic and business domain. You can understand it as the "Model" if the MVC. The latter is responsible to interacting with the outside world. It is usually found the View and the Controller of the MVC architecture.

priv - a directory that keeps all assets that are necessary in production but are not directly related to your souce code.

test - directory with all of the appliacation tests.
