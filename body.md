# TITLE
## SUBTITLE
DATE


#### Presentation Notes and Resources:
  - [slides](slides/index.html)

#### ToC

###### Section 1 - Gems by Example
  - What's a Gem?
  - Example of a Gem (hub)

###### Section 2 - Build Pseudo Complex large_app
  - The Formation of Our Software

###### Section 3 - Gem Extraction
  - Bundler Usage and Configs
  - Who haz thoughts?


# Section 1 - Gems by Example

## What's a Gem?

So if you're new to ruby gems, let's start out with a very basic description.  

  "A gem is a piece of ruby code that has been formatted into an easy to manage package."

So if you've ever used the `apt-get` package manager on debian based linux distros, that's pretty much what gems are, but for code within the ruby ecosystem.  


## Example of a Gem (hub)

Let's go over an example of a very popular gem, Hub.  Hub is a ruby gem that allows you to interact with github from the command line.  

Hub can easily be installed on any machine that has ruby installed by the below command:

```
  $  gem install hub

  Fetching: hub-1.12.4.gem (100%)
```

Go ahead and try it now.  In the command's output, you'll see that it fetched `hub-1.12.4.gem`.  That's telling you the name of the gem and the version installed... Gem defaults to the latest version of any given gem.  If that version is no good, you can tell gem to install a specific version manually.  

```
  $  gem install hub -v 1.12.3
```


Hub is a CLI tool.  Most ruby gems are just libraries, code that you use from within other ruby code, but we're installing a ruby gem that has a "binary file" component.  
Once you install a CLI gem, the binary becomes exposed on the system path.  Typing `which hub` will show you where this "binary" is.  
I'm scare quoting the term binary because if you open that file up, you'll actually see that it's just a ruby script with a shebang.  

Now you have two versions of a CLI gem on your system.  How do you choose between them?  
By default the latest version is used, which is probably ideal, but you can explicitly declare which gem to use by making the first argument an underscoric version identifier.

```
  $ hub _1.12.3_ --version
```

I don't know how this works... it just does.  




# Section 2 - Build Pseudo Complex large_app

## The Formation of Our Software

Before we get started building a gem, let's suppose that we have some code in an actual large application that needs to be extracted out into a gem.  Better than supposing, let's build a mock large application right now.  And in doing so, we'll add some ruby logic that will later be extracted into a gem.  

> What should that logic be?

Well... **what if** we had to encrypt and decrypt a string from within an important web app?  And we expect to be using this same crypto algo in several other rails apps.  This is the perfect place to use a gem.  

This is a fairly typical workflow for a gem's creation; we do this by first stumbling upon code that exists in a large app and then we decide to 'extract' the functionality into its own gem because late in the game we realized how re-usable this code was, or who atomically complex it has become.  

> Does anyone know how a star is formed?

*Wait to see if it's remotely applicable*

I was hoping that someone could tie in the creation of stars to the creation of gems.  But I realized last night that it's not gems that form like stars, rather it's rails apps that do!  All this stuff, these space particles, lots of hydrogen, just kinda drifted in -- gravitated towards this central, monolithic body.  And after a certain point, things started to get hot.  Things got out of hand!  There was too much friction, too much stuff, and things reached the verge of igniting in a blaze of nuclear fusion -- this is the kind of fire that won't relent in our god, damn lifetimes.  Once a star reaches that point, it's completely out of any one's control.  At this point, this point of no return it becomes a fixture of the universe.  A symbol of life amidst haphazardness, amidst chaos --completely absent of any notions of coercion or management outside of it's own brilliant, blazing body.  

Did you bank 50k this year?  100k?  200 kay?  Ok... ok... but at some socio-economic point does a being become a fixture of the universe...  Are the billionaires entrenched in our political vex-o-sphere the reason for the spectrum that we know as the periodic table of elements?  Of course not my dear present company, we are of these things, but as members; as participants.  And try as some might with ascriptions of measurements and commendations, embelishments and bull shit, as hackers we must vigilantly recognize that those on that path are little more than kidders and self-delusionists with but a loose sense of context.  A more noble question than salary or rank that I recommend everyone ask themselves is this: am I creating beauty of some kind?  

Anyway that's what a feature-rich rails application is: A mass of particles on the verge of nuclear detonation.  And maybe every good rails app --MAYBE EVERY GOOD THING should lead up to an explosion.  A really nice one that produces more for the universe than what existed before hand.  Maybe that's what I'm getting at.

With that said, lets begin by creating a fake rails app that we'll add pseudo complex functionality to.  



# Section 3 - Gem Extraction

Note: Tests...

So now it's time to start a new gem.

## Bundler Usage and Configs

It's a particularly under-advertized feature, but bundler, that nearly ubiquitous ruby gem that tends to be installed at the same time as ruby, has the capability of creating a gem skeleton.  This is really handy!  

You can configure some helpful defaults for bundler's gem function in the below file as I've done:

(~/.bundle/config)
```
---
BUNDLE_GEM__COC: 'false'
BUNDLE_GEM__TEST: rspec
BUNDLE_GEM__MIT: false
```

To build a gem, follow these commands:

```
  cd ~/dev/misc/edu/gem_building

  bundle gem kewl_crypto
```

Who
haz
thoughts?
