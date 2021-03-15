
## Directory Structure

_build - This directory is where the compiled files of your project goes to. Deleting it will cause your whole project to be rebuilt from scratch.
It must not be  so you have to add it to the .gitignore if it was not already done.

assets - As the name already suggests, this is the directory that keeps all the front-end related files. So all your CSS, JavaScript, static images goes into it. By default, it is handled by npm tool. Once you run npm isntalll into it, Phoenix will take care of the rest.

config - It takes care of the whole project configurations.

deps - Short for dependencies, this is the directory in which all the dependencies lies. You can find all the dependencies listed in mix.exs file. This must not be versioned and deleting it cause to Mix download all over again.

lib - This directory holds your application source code. Usually you can see two sub-directories. lib/application_name and lib/application_name_web.
The former holds your business logic and business domain. You can understand it as the "Model" if the MVC. The latter is responsible to interacting with the outside world. It is usually found the View and the Controller of the MVC architecture.

priv - a directory that keeps all assets that are necessary in production but are not directly related to your souce code.

test - directory with all of the application tests.


## Plug
Plug comes with the idea of unifying the concept of a connection that we operate on. It differs from other HTTP middleware layers such as Rack, where the request and response are separated in the middleware stack.

Plug specification comes in two flavours: 
*function plugs* and *module plugs*.

### Function plugs

Any function that accepts a connection struct (`%Plug.Conn{}`) and options is a function plug.

```elixir
def introspect(conn, _opts) do
  IO.puts """
  Verb: #{inspect(conn.method)}
  Host: #{inspect(conn.host)}
  Header: #{inspect(conn.request)headers}
  """
  conn
end
```

If we add this function to the `endpoint.ex` , set the plug before the HelloWeb.Router and access `localhost:4000` we would get something similar to this in your terminal

```elixir
Verb: "GET"
Host: "localhost"
Headers: [...]
```



See more about all the fields of the connection and other functionality associated to it  [see the documentation for Plug.Conn](https://hexdocs.pm/plug/Plug.Conn.html).

### Module Plugs

Module plug is another approach to define a connection transformation in a module.
The module only needs to implement two functions:

- `init/1` which initializes any arguments or options to be passed to `call/2`
- `call/2` which carries out the connection transformation. `call/2` is just a function plug that we saw earlier













