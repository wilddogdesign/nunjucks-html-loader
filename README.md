Nunjucks (Webpack) HTML Loader
==============================
The original 'nunjucks-loader' takes nunjucks templates and turns them into javascript. I wanted to take nunjucks templates and turn them into pre-compiled static html files.

This is an internal **Wild Dog Fork** of the [original repo by Ryan Hornberger](https://github.com/ryanhornberger/nunjucks-html-loader).

Usage
-----

This is a very simple webpack loader for nunjucks files. It performs the following opteration:

    some-template.nunj -> html string

When you mix it with the file-loader you can take it one step further!

    some-template.nunj -> html string -> some-file.html

Add your personal variation to the below loader configuration to your webpack config and you should be good to go.

	{
        test: /\.nunj$/,
        loader: 'file?context=' + precompiledContext + '&name=[path][name].html!nunjucks-html?' +
        	JSON.stringify({
        		'searchPaths': [
					'/path/to/sources',
					'/path/to/more/sources'
				],
        templateParameters: {
          envCallback,
        },
        	})
    }

