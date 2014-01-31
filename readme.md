
FullCalendar - Full-sized drag & drop event calendar
====================================================

This document describes how to modify or contribute to the FullCalendar project. If you are looking for end-developer documentation, please visit the [project homepage][fc-homepage].


Getting Set Up
--------------

You will need [Git][git], [Node][node], and NPM installed. For clarification, please view the [jQuery readme][jq-readme], which requires a similar setup.

Also, you will need the [grunt-cli][grunt-cli] and [bower][bower] packages installed globally (`-g`) on your system:

	npm install -g grunt-cli bower

Then, clone FullCalendar's git repo:

	git clone git://github.com/arshaw/fullcalendar.git

Enter the directory and install FullCalendar's development dependencies:

	cd fullcalendar && npm install


Development Workflow
--------------------

After you make code changes, you'll want to compile the JS/CSS so that it can be previewed from the tests and demos. You can either manually rebuild each time you make a change:

	grunt dev

Or, you can run a script that automatically rebuilds whenever you save a source file:

	./build/watch

You can optionally add the `--sourceMap` flag to output source maps for debugging.

When you are finished, run the following command to write the distributable files into the `./build/out/` and `./build/dist/` directories:

	grunt

If you want to clean up the generated files, run:

	grunt clean


Automated Testing
-----------------

To run automated tests, you must first install [karma] globally:

	npm install -g karma

Then, assuming all your source files have been built (via `grunt dev` or `watch`), you can run the tests from a browser:

	karma start --single-run

This will output a URL that you can visit in a browser. Alternatively, you can run the tests headlessly:

	karma start --single-run --browsers PhantomJS


Before Contributing
-------------------

Before contributing changes in the form of a pull request,
please make sure you have successfully ran the automated tests (instructions above)
as well as checked your code for any quality/styling errors. To do this, run:

	grunt check


[fc-homepage]: http://arshaw.com/fullcalendar/
[git]: http://git-scm.com/
[node]: http://nodejs.org/
[grunt-cli]: http://gruntjs.com/getting-started#installing-the-cli
[bower]: http://bower.io/
[jq-readme]: https://github.com/jquery/jquery/blob/master/README.md#what-you-need-to-build-your-own-jquery
[karma]: http://karma-runner.github.io/0.10/index.html