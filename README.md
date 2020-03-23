# GSatis ([Satis][satis] with GitHub Private Organisation Support)

Simple static Composer repository generator.

[![Build Status](https://travis-ci.org/composer/satis.svg?branch=master)](https://travis-ci.org/composer/satis)
[![codecov](https://codecov.io/gh/composer/satis/branch/master/graph/badge.svg)](https://codecov.io/gh/composer/satis)

## GitHub Private Organisation Support

I have few private GitHub organisations which have many private composer libraries, and Satis requires to add them all
one by one in `satis.json` file, which is pretty annoying if you have more than few libraries.

So I forked Satis project and added Github Organisation support by running GitHub API V4 GraphQL query to fetch all
repositories with composer.json file if it exists and add that repository into repository list programmatically.

For authentication, it uses Composer Github OAuth Token so no additional configuration is required.

```json
{
  "name": "Satis Repository",
  "homepage": "http://127.0.0.1",
  "repositories": [
  ],
  "github-organisations": ["composer"],
  "require-all": true,
  "output-dir": "./public"
}
```

## Run from source

Satis requires a recent PHP version, it does not run with unsupported PHP versions. Check the `composer.json` file for details.

- Install satis: `composer create-project aurimasniekis/gsatis:dev-master`
- Build a repository: `php bin/satis build <configuration-file> <output-directory>`

Read the more detailed instructions in the [documentation][].



## Contributing

Please note that this project is released with a [Contributor Code of Conduct][].
By participating in this project you agree to abide by its terms.

Fork the project, create a feature branch, and send us a pull request.

If you introduce a new feature, or fix a bug, please try to include a testcase.


## Authors

See the list of [contributors][] who participate(d) in this project.


## Community Tools

- [satis-go][] - A simple web server for managing Satis configuration and
    hosting the generated Composer repository.
- [satisfy][] - Symfony based composer repository manager with a simple web UI.
- [satis-control-panel][] - Simple web UI for managing your Satis Repository
    with optional CI integration.
- [composer-satis-builder][] - Simple tool for updating the Satis configuration
    (satis.json) "require" key on the basis of the project composer.json.


## Examples

- [eventum/composer] - A simple static set of packages hosted in GitHub Pages


## License

Satis is licensed under the MIT License - see the [LICENSE][] file for details


[documentation]: https://getcomposer.org/doc/articles/handling-private-packages-with-satis.md
[Contributor Code of Conduct]: http://contributor-covenant.org/version/1/4/
[contributors]: https://github.com/composer/satis/contributors
[satis-go]: https://github.com/benschw/satis-go
[satisfy]: https://github.com/ludofleury/satisfy
[satis-control-panel]: https://github.com/realshadow/satis-control-panel
[composer-satis-builder]: https://github.com/AOEpeople/composer-satis-builder
[LICENSE]: https://github.com/composer/satis/blob/master/LICENSE
[eventum/composer]: https://github.com/eventum/composer
[satis]: https://github.com/composer/satis/
