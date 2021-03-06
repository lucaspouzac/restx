# RESTX - the lightweight Java REST framework

[![Build Status](https://drone.io/github.com/restx/restx/status.png)](https://drone.io/github.com/restx/restx/latest)

RESTX is a full lightweight disrupting stack, which includes Swagger-like ui & considers REST specs tests as docs.

It shares similarities with modern frameworks like Play! like hot compile and a very productive experience, but focused on REST and pure Java.

It's licensed under the very commercial friendly Apache License 2, and is actively maintained by a community of developers.

You can get more details from the web site at http://restx.io/

Here you will find the build instructions if you want to build RESTX yourself, and why not contribute to the project.

## Build

RESTX requires Java 7.

You can build it using either Maven 2+ or EasyAnt.

With Maven:

`mvn install`

With EasyAnt:

`easyant test package`


## Changing dependencies

The sources for module descriptors are the `md.restx.json` files located in each module, and the `restx.build.properties` for the dependencies version.

Maven poms and EasyAnt Ivy files are generated from these files using `restx build generate pom + build generate ivy`.

## Project organisation

RESTX is decomposed in a set of modules, each one following the traditional Java project layout (main sources in `src/main`, test sources in `src/test`).

The main modules are `restx-core` and `restx-factory`.

Here is a brief summary of each module:

Main modules:

- `restx-common`: Some shared utilities, only few ones, relying on Guava we already get a lot of nice utilities from there.
- `restx-factory`: RESTX Dependency Injection (DI) container.
- `restx-factory-testing`: A module dedicated to test `restx-factory` features involving annotation processing.
- `restx-classloader`: Hot reload / hot compile support
- `restx-build`: The very simple tool which generates POM / Ivy files from `md.restx.json` files
- `restx-core`: Core module, includes the REST framework, base security, JSON support, Validation, ...
- `restx-core-annotation-processor`: Annotation processing to generate routers based on RESTX core annotations. Needed at build time only.
- `restx-security-basic`: A basic implementation of security, still enough in many cases.
- `restx-specs-tests`: Enables using RESTX specs as JUnit tests.
- `restx-specs-server`: Enables using RESTX specs as HTTP mocks.
- `restx-i18n`: I18n Support

Admin console modules:

- `restx-admin`: The pluggable RESTX admin web console.
- `restx-apidocs`: The famous API Docs web console, as a plugin for `restx-admin`.
- `restx-monitor-admin`: Poor's man app monitoring web console, plugin for `restx-admin`.
- `restx-factory-admin`: RESTX Factory admin console, plugin for `restx-admin`.
- `restx-log-admin`: Easy configuration of logback logging from admin console, plugin for `restx-admin`.
- `restx-specs-admin`: RESTX Specs recording and running web console, plugin for `restx-admin`.
- `restx-i18n-admin`: Easy setting of your i18n translations from the web console, plugin for `restx-admin`.

MongoDB support through Jongo API:

- `restx-jongo`: Main MongoDB support through Jongo API.
- `restx-jongo-specs-tests`: Support of Jongo in your specs (recording and running).

Servers support:

- `restx-servlet`: Servlet 2.5+ adapter for RESTX, allowing to embed RESTX in any servlet 2.5+ container.
- `restx-server-jetty`: Embedded Jetty support.
- `restx-server-tomcat`: Embedded Tomcat support.
- `restx-server-simple`: SimpleFramework adapter for RESTX, this is the lightest and fastest solution.
- `restx-server-testing`: JUnit tests for all the supported embedded servers.

Shell modules:

- `restx-shell`: The pluggable shell.
- `restx-shell-manager`: Plugin to manage the shell: install plugins, upgrade shell version.
- `restx-core-shell`: Plugin providing RESTX core support in the shell: app comilation and running, ...
- `restx-build-shell`: Plugin prodividing build support in the shell, especially to generate POM/Ivy files from `md.restx.json` files.
- `restx-specs-shell`: Plugin providing RESTX specs based HTTP mock server.

Others:

- `restx-samplest`: both a sample of individual features and JUnit tests of them
- `restx-package`: assembly module to package the shell
- `restx-annotation-processors-package`: assembly module for annotation processor only, if you prefer to setup annotation processing manually with `-proc` javac option
- `restx-barbarywatch`: MacOSX filesystem watching that actually works. Only module with GPL license, but no other module depend on it, it's detected at runtime, and used only during development


## Contributing

Contributions are welcome, fork the repo, push your changes to a branch and send a Pull Request.

To be sure the PR will be merged please discuss it on the google group before, or create an issue on GitHub to initiate the discussion.

