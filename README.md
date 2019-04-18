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
Providers are used to register dependencies (see Service Container) or just to load custom things.

To create a custom provider use the following command;

```
php console create:provider MyCustomProvider
```

When the provider is created you will need to register it in the config.php at the providers section.

## Service container
A service container is available to perform dependency injection. To use this, first create a custom provider and register it at the providers section in the **config.php**;

```
php console create:provider MyCustomProvider
```

In the created provider there is a **load** method. In this load method you can bind your dependencies like so;

```
public function load(): void
{
    // Interface binding
    $this->app->bind(MyCustomInterface::class, MyCustomClass::class);
    
    // Or initiate a class with custom parameters
    $this->app->bind(MyClass::class, function () {
        return new MyClass([
            'some' => 'custom',
            'params' => [1, 2, 3],
        ]);
    });
}

```

## License
The CLI framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).