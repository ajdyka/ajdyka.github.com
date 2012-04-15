---
layout: post
title: "Setting up Octopress under OS X Lion ... nothing is simple these days!"
date: 2012-04-12 18:00
comments: false
categories: [octopress, blog]
---

## My first post

So I'm expanding my repertoire and came across [Octopress](http://octopress.org/), "A blogging framework for hackers". It publishes static html (so it's performant) pages which you can create using markdown syntax (so it's easy to code) and can publish straight to github (so your code is open and freely available). Everything is open source and lovely!

<!--more-->

The install process seems simple enough, all you need is ruby, git .. but getting your Mac up and running takes some effort I found! Here are the hoops I needed to jump through to make it all happen:

1. Get XCode form the [App store](http://itunes.apple.com/app/xcode/id497799835)

2. Install the [XCode CLI Tools](https://developer.apple.com/downloads/index.action)

3. Install [Homebrew](http://mxcl.github.com/homebrew/)

4. Install Git via Homebrew

```
$ sudo brew install git
```
	
5. Time up update your gems! 

```
$ sudo gem update --system
```

6. You'll be needing liquid as a dependancy later on, so it's easier to update that now

```
$ sudo gem install liquid -v '2.2.2'
```

7. rb-fsevent is another dependancy that needs up be updated before you can proceed ... 

```
$ sudo gem install rb-fsevent -v '0.4.3.1'
```

8. Switch your environment to the new XCode

```
$ sudo xcode-select -switch /Applications/Xcode.app
```

9. I'm still running ruby 1.8 so I need to switch to the new version.

```
$ sudo rvm install ruby-1.9.2-p318
```

10. Now switch to the new verison of ruby, it doesn't happen automaically :-/

```
$ rvm use 1.9.3
```

11. Update your bundles ...

```
$ bundle update
```

12. now you can install Octopress!

```
$ rake install
```

Whew :)

Resources: 

* http://stackoverflow.com/questions/8139138/how-can-i-install-ruby-1-9-3-in-mac-os-x-lion
* http://stackoverflow.com/questions/9626729/how-do-you-install-build-ruby-1-9-3-on-osx-lion
* https://github.com/thibaudgg/rb-fsevent/issues/31
* http://daringfireball.net/projects/markdown/basics
 

