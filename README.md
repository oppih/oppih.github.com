# From oppih: a better way to keep up with Jekyll-Bootstrap

The official guide tells me to clone it and re-set the remote repo:

    $ git clone https://github.com/plusjade/jekyll-bootstrap.git oppih.github.com
    $ cd oppih.github.com
    $ git remote set-url origin git@github.com:oppih/oppih.github.com.git
    $ git push origin master

But as I did so, I cannot get new features from the rapid development of Jekyll-Bootstrap.

So I'd recommand you to to it like this:

    $ git clone https://github.com/plusjade/jekyll-bootstrap.git oppih.github.com
    $ cd oppih.github.com
    $ git remote set-url origin git@github.com:oppih/oppih.github.com.git
    $ git remote add jekyllbootstrap git://github.com/plusjade/jekyll-bootstrap.git
    $ git push origin master

You can use `git remote -v` to see what remotes you have.

And if you want to get new features from Jekyll-Bootstrap, juse do:

    $ git pull jekyllbootstrap master

Then use `git status` to check what changes. You may encounter **conflicts** with some files especially **_config.yml**. Merge it manually and then just push to your site!

# Jekyll-Bootstrap

The quickest way to start and publish your Jekyll powered blog. 100% compatible with GitHub pages

## Usage

For all usage and documentation please see: <http://jekyllbootstrap.com>

## Version

0.2.9 - stable and versioned using [semantic versioning](http://semver.org/).

## Contributing 

This repository tracks 2 projects:

- **Jekyll-Bootstrap Framework.**  
  The framework for which users should clone and build their blog on top of is available in the master branch.
  
  To contribute to the framework please make sure to checkout your branch based on `jb-development`!!
  This is very important as it allows me to accept your pull request without having to publish a public version release.
  
  Small, atomic Features, bugs, etc.   
  Use the `jb-development` branch but note it will likely change fast as pull requests are accepted.   
  Please rebase as often as possible when working.   
  Work on small, atomic features/bugs to avoid upstream commits affecting/breaking your development work.
  
  For Big Features or major API extensions/edits:   
  This is the one case where I'll accept pull-requests based off the master branch.
  This allows you to work in isolation but it means I'll have to manually merge your work into the next public release.
  Translation : it might take a bit longer so please be patient! (but sincerely thank you).
 
- **Jekyll-Bootstrap Documentation Website.**    
  The documentation website at <http://jekyllbootstrap.com> is maintained in the gh-pages branch.
  Please fork and contribute documentation additions to this branch only.

The master and gh-pages branch do not share the same ancestry. Please treat them as completely separate git repositories!


## License

[Creative Commons](http://creativecommons.org/licenses/by-nc-sa/3.0/)
