# dotfiles

| tl;dr |
| :--- |
| Enjoy my dotfiles _and_ learn how to maintain a repo of your dotfiles **without** symlinking or other complicated, easy-to-forget processes.

## What are dotfiles?

## About my dotfiles

My UN*X dotfiles (configuration files).

These will work on most *NIX environments; they' started back on 1980s UNIX distributions and have followed me to macOS. Some of these files are in use on the <a href="https://msdn.microsoft.com/en-us/commandline/wsl/about">Windows Subsystem for Linux</a>, so there's that.

Each the files in this repo has been added because I want to:

* have easy access for deployment on new UN*X machines I wind up working on, including my go-to platform, macOS [<a href="https://en.wikipedia.org/wiki/Darwin_%28operating_system%29">Darwin</a>].
* share with others those things over the years I've found useful, productive, and fun.

I've commented as heavily as possible, used some interesting bash techniques to get things done, and generally tried to <a href="https://xkcd.com/844/">stay out of the way of my future self</a> whilst making it possible to go back and tweak and add features without cursing my past stelf too much :-) 

Comments and corrections are always welcome.

Michael



```
cd $HOME
alias df='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
df config --local status.showUntrackedFiles no
echo "alias df='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'" >> $HOME/.ba*le
echo ".cfg" >> .gitignore
git clone --bare mickeys:mickeys/dotfiles.git $HOME/.dotfiles



df push --set-upstream origin master



df add .bash_profile ; df commit -m 'initial commit' ; df push
```

---
OLDER, OBSOLETE EXPLANATION -- TO-DO: MERGE W ABOVE
---


<a href="https://xkcd.com/1692/"><img src="./.dotfiles/images/xkcd_1692.png" width="40%" align="right"></a>


Feel free to peruse these, and even to use them as a start for your own use. I have stood on the <a href="https://stackoverflow.com/">shoulders of giants</a>, although all mistakes are my own (and,, besides, <a href="https://en.wikipedia.org/wiki/Turtles_all_the_way_down">it's turtles all the way down</a>, so now it's your turn to bulid for those who follow).

Symlink each of these into your home directory by

`for d in ~/dotfiles/.[a-z]* ; do ln -sv $d ~ ; done`



<img src="./.dotfiles/images/playa-pink-and-blue-hair.jpg" border="1">

## the tools

For a thoughtful, hard-core look at dotfile management, visit <http://dotfiles.github.io>.

À Propos nothing at all, a note about the tools I've used to generate these README files on github:

* on-line:  [dillinger.io](http://dillinger.io/) is a WYSIWYG side-by-side Markdown editor
* off-line: on my Mac I use [MacDown](https://macdown.uranusjr.com/) for the same functionality. I especially like ability to toggle CSS formatting files to use Markdown for other documentation purposes.

<br clear="right"></a>

## the files

| filename        | purpose |
| ------------- |------------- |
| .bash-ck      | CK-centric bash run-commands file for dealing with local (laptop) and remote (vagrant) instances. |
| .bash_profile   | Primary workhorse for customizing your bash experience. My `.bashrc_profile` includes a test yoke, which you can switch on to validate the internal functions I've written. I'm a quality assurance software engineer, and I'm really proud of giving this file the full software reliability treatment. |
| .gitconfig | `git` configuration |
| .gitignore | Local additions for things `git` should ignore, extending `.gitignore_global`. |
| .gitignore_global	| A master `.gitignore` based upon the collected wisdom we call <https://www.gitignore.io>. |
| .grc/ | Radovan Garabík's [Generic Colouriser ](http://kassiopeia.juls.savba.sk/~garabik/software/grc.html) is an almost-trivial way to colorise text output from any program. Makes everything easier. |
| .inputrc     | Changes input processing for all programs that use readline (like bash, python, etc) and turbo-charges what you can do with fingers still on the keyboard |
| .macos | Mathias Bynens' jaw-dropping _magnum opus_ of `default write` commands that tweak every aspect of macOS (found in his own [dotfiles](https://github.com/mathiasbynens/dotfiles/blob/master/.macos) repo). |
| .set_colors.sh | Provide color shortcuts for shell prompts, etc. |
| .set_prompt.sh | Create an easy-to-love command shell prompt. |
| .vimrc | Configure the `vim` text editor to be borderline awesome. |
| bin | My home-grown binaries (programs)
| README.md	| This very file. |

It's possible that the real world has gotten ahead of my documentation; you may see files checked in that aren't mentioned here. Sorry.

## Citations

[<small>1</small>] [The best way to store your dotfiles: A bare Git repository](https://www.atlassian.com/git/tutorials/dotfiles)<br>
[<small>2</small>] [I use: git init --bare $HOME/.myconf alias config='/usr/bin/git --git-d... 
| Hacker News](https://news.ycombinator.com/item?id=11071754)