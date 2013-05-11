# Introducing Grunt-banner

Hot on the heels of [Grunt-booty](https://github.com/mattstyles/grunt-booty) is [Grunt-banner](https://github.com/mattstyles/grunt-banner).  Following along the same lines of creating a quick and simple to use Grunt task, Grunt-banner simply puts some banner text at the top or bottom of a file.  Couldn’t be simpler!

## What does it do?

Like [Ronseal](http://www.ronseal.co.uk/) it does exactly what it says it does - it sticks a banner on to a file.  Other Grunt tasks have this built-in, most notably [concatenation](https://github.com/gruntjs/grunt-contrib-concat) and [uglification](https://github.com/gruntjs/grunt-contrib-uglify) tasks, but others don’t.  Further to this there are times when you want a little more control over where to place banners.

## Using Grunt-banner

_The usage is unlikely to change much but check the [README](https://github.com/mattstyles/grunt-banner) in the repo anyway, also worth checking the build status on github or npm too_.</br>

Using Grunt-banner is pretty simple, as you would expect.  Grunt-banner accepts only 2 options - where to place the banner and the text to use as the banner.  Then you feed it the list of files to add the banner to and it does it’s thing.</br>

_I’m going to assume you’ve got `node` and `npm` all going and that you’ve got some experience with `grunt`, if not, no worries, have a look [here](http://gruntjs.com/) to get started_.</br>

So, get Grunt banner installed in your project:

```bash
npm install grunt-banner --save-dev
```

Then load it as a task in the your Gruntfile:

```js
grunt.loadNpmTasks('grunt-banner');
```

If you’re using [Tyler Kellen’s](http://goingslowly.com/) [dependency matching task](https://github.com/tkellen/node-matchdep/) then it’s even easier, this line of javascript will include Grunt-banner along with all your other grunt-* tasks:

```js
require('matchdep').filterDev('grunt-*').forEach(grunt.loadNpmTasks);
```

Now that Grunt knows all about the task it’s time to specify what it should do for you, firstly create a banner object _(this step is not required, you could specify it straight into the task)_:

```js
banner: '/** My Awesome Project\n' +
	' * Created at <%= grunt.template.today("dd-mm-yyyy") %>\n' +
	' */'
```

Being a standard variable definition inside your `grunt.initConfig` function it has full access to [grunt templates](https://github.com/gruntjs/grunt/wiki/grunt.template) using the standard grunt delimiters `<%` and `%>`.

The actual task is specified using `usebanner` and takes two parameters:

* `options`

_position_ : `top` or `bottom` - where to place the banner</br>

_banner_ : The banner to use

* `files`

_src_ : array of files to add the banner to, `*` is fine</br>

Here’s a working example from this [Gruntfile](https://github.com/mattstyles/yeoman-angular-express-plus/blob/master/Gruntfile.js):

```js
usebanner: {
  options: {
    position: 'top',
    banner: '<%= banner %>'
  },
  files: {
    src: [
      '<%= yeoman.dist %>/scripts/*'
    ]
  }
}
```

Note the use of the grunt template delimiters to specify parameters and also the use of the wildcard `*`, we could just as easily have specified `*.css` or `*.js`.

`Grunt-banner` only adds a banner on to a file, if you want files concatenated or minified then use whichever tasks you would normally run and use the `grunt-banner` task to add a banner to your final files.

_Have fun_

### Links

[grunt-banner on npm](https://npmjs.org/package/grunt-banner)

[grunt-banner on github](https://github.com/mattstyles/grunt-banner)

Be sure to use `npm star grunt-banner`!

---

Want to discuss this article?  Hit me up [@veryfizzyjelly](https://twitter.com/veryfizzyjelly)

---

Posted in [Coding](../ "Coding") on 11th May 2013.  _Grunt-banner_, _Gruntplugin_, 