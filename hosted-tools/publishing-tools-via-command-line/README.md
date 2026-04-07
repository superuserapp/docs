# Publishing tools via command line

Tools are published via our command line tools.

* [Installing `sup`: Superuser package manager](./#installing-sup-superuser-package-manager)
* [Initialize a new Superuser package](./#initialize-a-new-superuser-package)
* [Creating tools aka endpoints](./#creating-tools-aka-endpoints)
* [Installing NPM packages](./#installing-npm-packages)
* [Deploy a Superuser package](./#deploy-a-superuser-package)
* [Additional utilities](./#additional-utilities)
  * [Generate endpoints](./#generate-endpoints)
  * [Generate tests](./#generate-tests)
  * [Run tests](./#run-tests)
  * [Environment variables](./#environment-variables)

## Installing `sup`: Superuser package manager

Our command line tools are available at [github.com/superuserapp/superuser-cli](https://github.com/superuserapp/superuser-cli). For the most up to date guide on using the command line tools, please check the repository. This page exists as a quick getting started guide.

## Initialize a new Superuser package

To initialize a new Superuser package:

```sh
$ npm i superuser.app -g
$ mkdir new-package
$ cd new-package
$ sup init # sup is cli tool for superuser.app
```

You'll be walked through the process. The `sup` CLI will automatically check for updates to core packages, so make sure you update when available. To play around with your Superuser package locally;

```sh
$ sup serve
```

Will start an HTTP server. To execute a standalone endpoint / tool:

```sh
# run functions/index.js
$ sup run /

# run functions/some-endpoint.js
$ sup run some-endpoint

# run functions/index.js with {"name":"hello"} POST parameters
$ sup run / --name hello
```

## Creating tools aka endpoints

Defining custom tools is easy. You'll find the terms **tool** and **endpoint** used interchangeably as they all refer to the same thing: your bot executing custom code in the cloud.

A **tool** is just an **endpoint** hosted by the Superuser Package Registry.

All endpoints for Superuser packages live in the `functions/` directory. Each file name maps to the endpoint route e.g. `functions/hello.js` routes to `localhost:8000/hello`. You can export custom `GET`, `POST`, `PUT` and `DELETE` functions from every file. Here's an example "hello world" endpoint:

You can create a new endpoint with:

```sh
$ sup g:endpoint hello
```

```javascript
// functions/hello.js

/**
 * A basic hello world function
 * @param {string} name Your name
 * @returns {string} message The return message
 */
export async function GET (name = 'world') {
  return `hello ${name}`!
};
```

You can write any code you want and install any NPM packages you'd like to your tool package.

## Installing NPM packages

You can install NPM packages the traditional way, or using your bundler of choice:

```sh
$ npm i stripe --save # or whatever package you want
```

Superuser will **automatically install** NPM packages on deployment, we do not use your locally stored packages.

## Deploy a Superuser package

To deploy a public project to a `development` environment, you can use:

```
$ sup publish
```

You can also publish to `staging` and `production` using:

```
$ sup publish --env staging
$ sup publish --env production
```

## Additional utilities

There are a few additional utilities you may find useful with this package;

### Generate endpoints

```sh
# generates functions/my-endpoint/example.js
$ sup g:endpoint my-endpoint/example
```

### Generate tests

```sh
# Generate blank tests or ones for an endpoint
$ sup g:test my_test # OR ...
$ sup g:test --endpoint my-endpoint/example
```

### Run tests

You can write tests for your tools to verify they work. Simply run;

```sh
$ sup test
```

Your tests in the `test/` directory will be run top-down with shallow folders first, and alphabetically.

### Environment variables

{% hint style="danger" %}
Be careful when using environment variables with public packages.\
By default **we do not expose .env files** in public package code, so your secrets are safe and encrypted. However, all Superuser users can run public package code: it is recommended you do NOT log or return these variables.
{% endhint %}

You can store environment variables with your packages in the root directory as:

```
.env
.env.staging
.env.production
```

Your environment variables will then be available in code via `process.env.VAR_NAME`.

These files **will not** be published for everybody to see, so you can use them to hide secrets within your code. However, be careful when using environment variables with public packages: if you ever return them in an endpoint response, or connect to sensitive data, there's a chance you may expose that information to another user of the platform.
