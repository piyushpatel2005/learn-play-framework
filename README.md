# Learn Play Framework

First of all, to create a simple seed project, we can use following commands.

```shell
sbt new playframework/play-scala-seed.g8
sbt new playframework/play-java-seed.g8
```

Some of the key featuers of Play framework are:

- Declarative application URL scheme configuration
- Type-safe mapping from HTTP to an idiomatic Scala API
- Type-safe template syntax
- Live code changes when you reload the page in your web browser
- Full-stack framework features, including persistence, security and internationalization

Play supports Java and Scala.
Launch the application using `sbt run` command. Once it executes, you can open `http://localhost:9000` on your browser.

```
app                      → Application sources
 └ assets                → Compiled asset sources
    └ stylesheets        → Typically LESS CSS sources
    └ javascripts        → Typically CoffeeScript sources
 └ controllers           → Application controllers
 └ models                → Application business layer
 └ views                 → Templates
build.sbt                → Application build script
conf                     → Configurations files and other non-compiled resources (on classpath)
 └ application.conf      → Main configuration file
 └ routes                → Routes definition
dist                     → Arbitrary files to be included in your projects distribution
public                   → Public assets
 └ stylesheets           → CSS files
 └ javascripts           → Javascript files
 └ images                → Image files
project                  → sbt configuration files
 └ build.properties      → Marker for sbt project
 └ plugins.sbt           → sbt plugins including the declaration for Play itself
lib                      → Unmanaged libraries dependencies
logs                     → Logs folder
 └ application.log       → Default log file
target                   → Generated stuff
 └ resolution-cache      → Info about dependencies
 └ scala-2.13
    └ api                → Generated API docs
    └ classes            → Compiled class files
    └ routes             → Sources generated from routes
    └ twirl              → Sources generated from templates
 └ universal             → Application packaging
 └ web                   → Compiled web assets
test                     → source folder for unit or functional tests
```

Routes are defined in `conf/routes` file. Here, we have defined GET `/hello` route which accepts `name` query argument. If we try to access `http://localhost:9000/hello?name=John`, it will greet that user.
We have also defined another route `hello.scala.html` which takes `name` argument. It is passed from controller method `hello(name)` into this view. This can then be used on the view.
We can also open `console` in SBT. This will allow us to interact with the code in live session.

```shell
sbt
compile
console
views.html.hello.render("Play")
```

This way we can test web application without running a server.