# AngulAR cli

The Angular CLI is a command-line interface tool that you use to initialize, develop, scaffold, and maintain Angular applications directly from a command shell. we can install angular latest CLI using the following command

`npm install -g @angular/cli`

1. ng new <project-name> [ options ] - Creates a new Angular project. By default, the project is created under the current directory.

  Options:

  * --dry-run - only output the files created and operations performed not actually create the project.
 Alias:
 --verbose
'd'.
output more information.
Alias:
'v'.
--skip-npm
--skip-gitdo not run any npm command once the project is created
--directoryparent directory to create the new project into.
do not create a git repos itory for the project.

2. ng init <project-name> [options ] - Creates a new Angular project in the current folder.

Options
--dry-run
only output the files created and operations performed
not
actually create the project
Alias:
--verbose
output more information.
Alias:
--skip-npm
name
ng completion
'd'.
'v'.
do not run any npm command once the project is created
The name of the project to create.

3. ng completion - Adds autocomplete functionalitY to your shell for ng commands.

4. ng doc <keyword> - Opens a browser window with the keyword as search in Angular documentation.

5. ng e2e - Runs all end-to-end tests defined in your application,using protractor.

6. ng format - Formats the code of this project using clang-format.

7. ng generate <type> [options] - Generate new code inside your project.
Alias: 'g'

Valid types:
component <path/to/component-name>Generates a component.
directive <path/to/directive-name>
route <route/to/route-component>Generates a directive.
Generates a route. The name should
be the route used in the RouteConfig.
pipe spath/to/pipe-name>Generates
service <path/to/service-name>Generates a service.
a
pipe.
The generated component has its own directory, unless the --flat options
is specified.
Ankita TripathyOptions
flat
Do not create the code in its own directory.
--route=<route>
Specify the parent route. only for generat ing components
and routes. Default to the path specified.
--skip-router-generation
Skip generating the route config for the parent.
only usable for routes.
--defaultSpecify that the route should be a
default route.
--lazySpecify that the route is lazy. Default to true.

8. ng get pathl, path2, ...pathN> [options ] - Get a value from the Angular CLI configuration. The pathN arguments is a val
Javascript path like "users[ 1].userName ". If the value isn't set,
"undefined
will be shown. This command by default only works inside a project directory
Options:
--globall
Returns the global configuration value instead of the loca
one (if both are set). This option also makes the command
work outside of a project directory.

9. ng set path1=valuel, path2=value2, ...pathN=valueN> [options] - Set a value in the Angular CLI configurat ion. By default, sets the value in the project ' s configuration if ran inside a project, or fails if not inside a project.
The pathN arguments is a valid JavaScript path 1ike
"users[1].userName". The value will be coerced to the proper type or will
throw an error if the type cannot be coerced.

Options
--global - Sets the global configuration value instead of a local one. This also makes ng set works outside a project.

10. ng github-pages :deploy [options ] - Ankita TripathyBuild the application for production,setup the itHub repository,then publish the app.

options
--message=<message> - Commit message to include with the build.
Defaults to "new
--environment=<env>
The Angular environment to build.
Defaults
--branch=<branch-name>
gh-pages version"
to
"production "
.
The git branch to push the pages to.
Defaults to "gh-branch".
Skip building the project before publishing.
--skip-build
--gh-token=<token>API token to use to deploy. Required.
--gh-username=<username>The Github username to use. Required.

11. ng lint - Run the codelyzer linter on your project.

12. ng test [options] - Run unittests, using karma.

Options:
--watch - Keep running the tests. Default to true.
--browsers, --colors, --reporters, --port, --log-level - Those arguments are passed directlY to karma.

13. ng version - Outputs the version of angular-cli,node and the operating system.

## Ng build

The command can be used to build a project of type "application" or "library". When used to build a library, a different builder is invoked, and only the ts-config, configuration, and watch options are applied. All other options apply only to building applications.

## Ng serve

ng serve — This command builds, deploy, serves and every time watches your code changes. if find any change in code it builds and serves that code automatically. How do Angular builds? After coding our Angular apps using TypeScript, we use the Angular CLI command to build the app.

## Ng generate

ng generate is used to create the component in angular project. These are the two main ways to generate a new component in Angular: using ng g c <component_name>, and using ng generate component <component_name>. Using either of these two commands, the new component can be generated pretty easily and followed by the suitable component name of your choice.

## Ng test

ng test is used to runs unit tests in angular project.

`ng test <project> [options]` | `ng t <project> [options]`

## Ng e2e

End-to-end testing (E2E) of Angular applications is performed using the Protractor testing framework, which is created by the Angular team themselves. Protractor can perform end to end tests on Angular applications that are running in a real browser by interacting with it, similar to that of an end-user.

## Ng new

`$ ng new [name]`

That’s the default usage of the command and creating a new project folder with name. The project which is created in that folder is containing:

The default Angular project, All dependencies installed in node_modules folder , Testing files for each components

## Schematics

A schematic is a template-based code generator that supports complex logic. It is a set of instructions for transforming a software project by generating or modifying code.
