# CLI
A small and simple to use command line interface application.

## Installation
To install the CLI framework just run the following composer command;

```
composer create-project onemustcode/cli my_project --prefer-dist
```

## Create new commands
To add a new command execute the following command;

```
php console create:command my-command MyCommand
```

The first parameter is the name of the command that you will run;

```
php console my-command
```

The second parameter is the class name.

## Create providers
To create a custom provider use the following command;

```
php console create:provider MyCustomProvider
```

When the provider is created you will need to register it in the config.php at the providers section.

## License
The CLI framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).