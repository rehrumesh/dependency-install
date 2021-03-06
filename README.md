# dependency-install
Install dependencies in multiple package.json files also allowing to define custom dependency paths.

## Installation

Dependency-install package can be install via NPM. Use following command to install this package to your project.

`npm install dependency-install --save`

## Usage

```javascript
var di = require('dependency-install');

// Without callback
di.install('./path/to/required/directory');

// With callback

di.install('./path/to/required/directory', function() {
    // Instructions to execute after dependency installation.
});

```

### Custom dependencies

You can also use custom dependencies feature to share your common code with different directories.

```
__/your_custom_dependency_directory
    |__dependency_a
    |__dependency_b
    |__dependency_c
    |__dependency_d
```

In your package.json files have `customDependencies` with the required dependencies.

```
package.json
{
        ...
        customDependencies: {
            "dependency_a" : "local",
            "dependency_b" : "local"
        }
}

```

Before use the `install` method, remember to set the base path for your custom dependency directory.

```javascript

di.init('/path/to/your/dependency/directory/');
di.install('./path/to/required/directory');

```
## Contributing

We love our contributors! If you'd like to contribute to the project, feel free to submit a PR. But please keep in mind the following guidelines:

* Propose your changes before you start working on a PR. You can reach us by submitting a Github issue. This is just to make sure that no one else is working on the same change, and to figure out the best way to solve the issue.
* If you're out of ideas, but still want to contribute, help us in solving Github issues already verified.
* Contributions are not just PRs! We'd be grateful for having you, and if you could provide some support for new comers, that be great! You can also do that by answering this plugin related questions on Stackoverflow.
You can also contribute by writing. Feel free to let us know if you want to publish a useful guides, improve the documentation (attributed to you, thank you!) that you feel will help the community.

## License

  [MIT](LICENSE)
