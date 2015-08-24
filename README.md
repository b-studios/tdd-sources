Mocha
-----
https://mochajs.org/
Testframework based on node.js


Chai
----
http://chaijs.com/api/bdd/
Assertion language that can be used with both mocha and nightwatch.

Selenium
--------
http://www.seleniumhq.org/
Automated webbrowser

Nighwatch
---------
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
  gui-test/
  reports/
  nightwatch.json
~~~

Given this directory structure we can tell nightwatch to start
the selenium server in `nightwatch.json`:

~~~
...
"start_process" : true,
"server_path" : "bin/selenium-server-standalone-2.47.1.jar",
...
~~~
