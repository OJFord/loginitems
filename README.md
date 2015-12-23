# loginitems
loginitems is a simple command line tool to manage applications that launch on startup on OS X. While [previously possible with launchctl]() this is deprecated as of some time before or with 10.11.

## Usage
```sh
Usage: loginitems [-h | -a NAME -p PATH [-s HIDE?] | -d NAME | -l]
  -h Show this help message.
  -a Add an application, optionally hide with -s false.
  -p Path to application.
  -s Show/hide application; defaults to true (no hide).
  -d Delete an application from login items.
  -l List all login items.
```

For example:
```sh
% loginitems -a Caffeine -p "/Applications/Caffeine.app"
% loginitems -l
Caffeine
% loginitems -d Caffeine
% loginitems -l
%
```

## Todo
- While the Applescript use may well work (untested) on earlier versions, I hope to check OS X version and use `launchctl submit` on older versions, or `defaults write` on ancient ones

