
# README #

This is the first version of a python interactive mode for TextMate implementing [REPL](http://en.wikipedia.org/wiki/REPL).

Please do not hesitate to contribute.
Feedback's welcome, too, but, unfortunately, I can't guarantee that I'm able to fix bugs ('cause I'm new to textmate and screen)

## LICENCE ##

<a href="http://creativecommons.org/licenses/GPL/2.0/">
<img alt="CC-GNU GPL" border="0" src="http://creativecommons.org/images/public/cc-GPL-a.png" /></a><br />
This software is licensed under the <a href="http://creativecommons.org/licenses/GPL/2.0/">CC-GNU GPL</a> version 2.0 or later.

## Requirements ##

- [TextMate](http://macromates.com/)
- [iTerm](http://iterm.sourceforge.net)
	- a bookmark **Screen'd Python** in iTerm that executes the following cmd:
	- `/usr/bin/env screen -S iPythonSession -t iPython`
- Python installation (of course)

## Installation ##

Double-Click the tmbundle contained in this zip-file, it should automatically install itself (as long as you have textMate installed)

## Usage ##

<!-- - Open iTerm
- Create new session by executing the bookmark **Screen'd Python**. -->

- call *Open Terminal with Screened Python*
	- A Terminal window should appear saying *Welcome to Python Interactive*
- `enter` (`fn-return`) executes the line or selection in the python screen-session.
- When done with your interactive session, `ctrl-d` the python process in iTerm and **end the screen session via ctrl-d**. If you don't do it that way, it wil be still there (as a detached screen session).

If something goes wrong, it may be caused by an already-running screen session. Look for it via `screen -ls` and kill it by attaching (`screen -r <pid>`) and `ctrl-d`.

## Customization ##

Support for 

- `Terminal.app` / `iTerm.app`
- `python` / `ipython` 

Defaults are `terminal` and `python`.
This can be changed by declaring

- `TM_TERM_PROG=iTerm` 
- `TM_PYTHON_INTERACTIVE=ipython` 

in TextMate's *Advanced Preferences*.


## Known Bugs ##

Still _very_ alpha.

## Big Thanx ##

Big Thanx go to [technotales](http://technotales.wordpress.com) for his [excellent howto on slime, vim, screen and REPL](http://technotales.wordpress.com/2007/10/03/like-slime-for-vim/), 
Thomas Hermann the initial idea and suggestions on how to automate the screen creation process, and to the [SuperCollider](http://supercollider.sf.net) community, which inspired me to look for a way to get python REPL'y to work in TextMate.

## Authors ##

so far:

- 2009, [LFSaw](http://LFSaw.de), (*lfsaw at lfsaw dot de*)

## Release Notes ##

- Sun Apr 19 12:57:28 CEST 2009
	- complete rewrite of screen sesison creation based on thomas' suggestions
	- changed default keyboard shortcut for evaluation of selection to `enter` (`function-return`)
	- added support for terminal and ipython (defaults are terminal and python, iterm and ipython can be switched on by declaration of TM_TERM_PROG=iTerm resp. TM_PYTHON_INTERACTIVE=ipython in TextMate's "Advanced Preferences")
	- changed interpret to use bash instead of python (prevents python to misinterpret (single-)quotes)
- Fri Apr 17 18:26:34 CEST 2009
	- First release
	- manual creation of screen session required
	- supressing python interactive prompts

## ToDos ##

- TODO customize, such that iPython supresses prompts