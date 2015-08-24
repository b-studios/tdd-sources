TDD-Sources
===========
These are some notes and files that should help students
participating in the TSP at Tubingen University to get started
with test-driven-development (TDD).

There are tons of testing frameworks / libraries / dsls out
there. Here we consider two testing frameworks:

- Mocha (for unit testing)
- Nightwatch (for End-to-End testing)

Both frameworks support writing test cases in a dsl called `chai`.
Nightwatch uses "Selenium" for browser automation. That is,
you don't have to manually click through a homepage and assert
everything is fine, but selenium will do that for you.

Mocha
-----
https://mochajs.org/
Testframework based on node.js

~~~
npm install -g mocha
~~~

Chai
----
http://chaijs.com/api/bdd/
Assertion language that can be used with both mocha and nightwatch.

~~~
npm install chai
~~~

Selenium
--------
http://www.seleniumhq.org/
Automated webbrowser

Nightwatch
----------
http://nightwatchjs.org/
https://github.com/nightwatchjs/nightwatch
DSL for writing automated tests in JS using node.js

### Setup
There is a detailed guide on nightwatchjs.org. Here just a
short summary:

Download the [latest selenium jar](https://selenium-release.storage.googleapis.com/index.html):
`selenium-server-standalone-2.XX.X.jar`

Install node.js and npm and then
~~~
$ git clone git@github.com:nightwatchjs/nightwatch.git
$ cd nightwatch
$ npm install -g
~~~

Running the selenium standalone server:

~~~
# in selenium/
java -jar selenium-server-standalone-2.47.1.jar
~~~

Running the nightwatch test suite to check whether everything
works fine:

~~~
# in nightwatch/
npm test
~~~


Project Setup
-------------
Create the directory structure

~~~
your-project/
  bin/
    selenium-server-standalone-2.XX.X.jar
  gui-test/ # nightwatch tests live here
  test/     # mocha tests live here
  reports/
  nightwatch.json
  package.json
~~~

Given this directory structure we can tell nightwatch to automatically start
the selenium server in `nightwatch.json`:

~~~
...
"start_process" : true,
"server_path" : "bin/selenium-server-standalone-2.47.1.jar",
...
~~~

To be able to use `chaijs`, in the file `package.json` we must
inform `npm` about the dependecies:

~~~
"devDependencies": {
  "chai": "*",
  "mocha": "*"
}
~~~

Running `npm install` will fetch latest version of mocha and
chai.
