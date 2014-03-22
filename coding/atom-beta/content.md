# Atom Beta

In truth, [Brackets](http://brackets.io/) has been pretty good to me. Despite taking some flak for it, I’ve staunchly defended a _browserified_ editor and, by and large, Brackets has been a good friend.  In short, we’ve had rather pleasing arrangement. However, that relationship may be ending very soon.

One of the latest offerings from [Github](https://github.com/) is [Atom](https://atom.io/), which, in it’s own words, is an editor for modern hacking.

> A hackable text editor for the 21st century

It’s a fully featured and highly extensible editor that encompasses the ideals of Github as a company. It is a web-based native solution (?) that has javascript and modern design techniques at it’s very core. Apparently, it’s all you’ve ever wanted from an editor and is more than enough to tempt you away from your solid, dependable and well-groomed old hacking buddy.

But, enough waffle and summarisation, what’s really going on?

### Enter Atom

[Atom](https://f.cloud.github.com/assets/69169/2289498/4c3cb0ec-a009-11e3-8dbd-077ee11741e5.gif)

I [wrote about Brackets](http://veryfizzyjelly.com/coding/brackets-sprint-25/) when it was back in sprint 25 (it now quietly updates but it’s currently at a well featured sprint 37) in May 2013 after using it for a while so I’m coming up for a year of solid coding using Brackets and a list of extensions. What this means is that I’m comfortable with Brackets, I’ve learnt a lot in that time and felt that we’ve learnt together, that we’ve grown up (coding-wise) in that time.

In contrast, I got my invite to the Atom beta this morning.

Many a head has been turned by a newer model and after only a few hours with Atom I’m hardly in a place to make a decision about it but tooling is an  important consideration for any dedicated hacker and it’s well worth taking some time to assess new products and technologies.

### Initial Impressions

Atom is a _web-stack_ browser so for me, as a web developer, it’s basis in HTML/CSS/JS and Chrome is a massive advantage over native solutions if I need to be able to alter/extend it.

Out-of-the-box Atom supports most of the features that I require. There’s the basics of code-folding, syntax highlighting, file management and standard controls for editing text that you’d expect just about everywhere.

Atom is extensible and for what I’ve read this is a fairly straight-forward procedure that has involved some forethought from Github to make it so. Asthetics are something that are valuable to me if I’m to spend half of my day looking at a text editor (the other half will be in terminal) and this is valuable to Atom too. In about an hour I was able to use the [docs](https://atom.io/docs/latest/) and navigate through the HTML to find what I needed to find to style it up to my tastes.

Atom splits the styling in to two sections, the UI and syntax highlighting. This separation is a clever design decision that makes life so easy. Most coders seem to be pretty picky and so long as you’ve savvy with web technologies it isn’t a big effort to style Atom how you want although I’m sure there will be a glut of themes available before the initial release. My syntax highlighting is pretty much complete, and, in true Github style, is available as a [repo](https://github.com/mattstyles/lambda-syntax). I’ve also forked the main dark UI theme that ships with Atom to [here](https://github.com/mattstyles/lambda-ui) and will use the handy styleguide to make some small changes, although the theme is pretty nice anyway.

Tomorrow’s job will be ploughing through the extensions, there are already a few (mainly from the core team) although one of the concepts behind Atom is that it has a number of features right-away to save you spending time configuring the editor. According to the _packages_ menu the beta I’ve downloaded today comes with 14 packages already fired into it and they are the usual suspects of packages that you’d probably download anyway such as snippets, markdown integration, a file viewer etc etc.

Atom also comes booted with a package manager and set of CLI tools that make life for developers that little bit sweeter and stop you having to write that stuff yourself.

Even though I’ve hardly given Atom a proper once-over yet a few inaccuracies are already irksome. Very occasionally selecting sections of text go awry which is a fairly minor bug. More concerning is a lack of code-hinting but there is likely already a package for this and just as likely that that package will make it into the bundle as standard before long. Another minor is that my ignore list doesn’t seem to be honoured so I have some junk in the file view. I’ve tried to come up with more negatives but so far, so good.

### Comparison with Brackets

I feel a little bad doing this but there is the inevitable comparison with Brackets and lists are easy to write and read so here goes:

* __Concept__ Conceptually both are _web-stack_ editors which, if you are a JS nonce like me, is a little win over native IDE’s or something like Sublime. Beyond ideals there is a practical benefit to this thinking—my python skills are lacking so hacking on Sublime is difficult and the intensity, clutter and _hidden workings_ of IDE’s (not too mention the usually appalling resource load) like Eclipse or WebStorm put me right off. The web likes skinny and web developers should follow suit. Atom has a CoffeeScript slant but it’s certainly more appealing than a different language to learn just to make minor tweaks.

* __Concept__ Extension-wise both editors are well catered for. Both are fairly easy for web developers to build for. Brackets has a GUI for such things but Atom has the basis in CLI tools and will grow. Brackets surely has more choice but that is timing. Atom comes packaged with more right-off-the-bat and they are well though of too which saves time and effort at the cost of hiding some workings of the editor (if you’ve sourced your extensions then you’ve probably already got an idea how and why to use them and so your learning time is reduced but offset by sourcing time).

* __Creators__ Both Adobe and Github are fantastic companies with a good ethos for supporting open source. Atom is in a slightly odd place here as it won’t be entirely open source—it will involve a cost but pull-requests will be accepted and it relies heavily on an army of open source modules to work.

* __Features__ Due to extensibility both are well featured. Both are well documented with active communities. Brackets has a more mature field, but that’s to be expected as the first to the market.

* __Performance__ Creating a DOM and all that goes with it just to edit some characters is not without it’s own problems, but, that aside (and there are plenty of advantages to this approach, advantages which both push), there are other issue. Brackets has a torrid time with minified files (where a lot of characters are on a single line) and can also splutter when asked to handle too many files in a project, even if those files aren’t actively opened into an editor instance (there used to be a limit on the number of files, which, when you consider _node_ or _bower_ modules, can quickly become a problem). At first inspection, Atom seems to have neither problem. Infact, Atom seems quick, very quick.

* __Asthetics__ Both are a minimalist text editor at heart. If you want to focus just on your code then neither will stop you. Theme generation is easy enough in either editor but Atom seems to actively encourage it as a natural step in choosing an everyday editor.

* __Code Hinting__ Brackets uses Tern and is, by-and-large, excellent. It’s not perfect and I’ve seen better but it’s good. Nothing yet in vanilla Atom, but there will be.

### End

Atom seems great. The minor points I’ve found so far are just that; minor. Invariably you’ll have a checklist of things that _your_ editor should do and Github have gone to some pains to make sure that for the _average_ web developer Atom answers a lot of those questions.  Sure, I’ve had a day (infact, it’s been a busy day so it’s only been a few hours) to hack with Atom but early indications are almost entirely positive.

I love Brackets, I really do, but, I may just come to love Atom more.

### Links

* [Brackets](http://brackets.io/)

* [Atom](https://atom.io/)

---

Want to discuss this article?  Hit me up [@veryfizzyjelly](https://twitter.com/veryfizzyjelly)

---

Posted in [Coding](../ "coding") on March 22nd 2014.  _Atom_ _Brackets_
