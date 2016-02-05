# loginitems
loginitems is a simple command line tool to manage applications that launch on startup on OS X. While [previously possible with launchctl]() this is deprecated as of some time before or with 10.11.

## Installation
I'm a big brew fan - so while this repo isn't popular enough to be included in official formulae, if you share my preference then you can run [the formula from my fork here](https://github.com/OJFord/homebrew/blob/formula-loginitems/Library/Formula/loginitems.rb):
```sh
brew tap OJFord/formulae
brew install loginitems
```

Otherwise, you'll need to clone/download the repo to somewhere on your path, and `chmod +x` each of the included scripts.

## Usage
```sh
Usage: loginitems [-h | -a NAME [-p PATH] [-s HIDE?] | -d NAME | -l]
  -h Show this help message.
  -a Add an application, optionally hide with -s false.
  -p Path to application; defaults to /Applications/NAME.app.
  -s Show/hide application; defaults to true (no hide).
  -d Delete an application from login items.
  -l List all login items.
```

For example:
```sh
% loginitems -a Caffeine 
% loginitems -l
Caffeine
% loginitems -d Caffeine
% loginitems -l
% loginitems -a "Custom Name" -p "/Applications/Caffeine.app"
% loginitems -a "App" -p "/that/I/decided/to/store/elsewhere/because/yolo.not-app"
% loginitems -l
Custom Name, App
%
```

## Todo
- While the Applescript use may well work (untested) on earlier versions, I hope to check OS X version and use `launchctl submit` on older versions, or `defaults write` on ancient ones

