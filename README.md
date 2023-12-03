# Sofi

Terminal-based application launcher written in POSIX-compliant shell. Only
dependency is [fzf](https://github.com/junegunn/fzf).

Caching by default, persistent history and
[rofi](https://github.com/davatorium/rofi) /
[tofi](https://github.com/philj56/tofi)-esque drun mode.

## Installation

Simply add **sofi** to your **$PATH** variable and install **fzf**.

## Usage

Sway config example

    bindsym --no-repeat mod4+d       exec $TERM sofi
    bindsym --no-repeat mod4+shift+d exec $TERM sofi -c

You can rebuild/override existing cache by passing the -c parameter.

If no cache file is found, one will be generated automatically.

## Configuration

Launching non-terminal applications
* If not on Sway, replace **swaymsg exec "$bin"** with your preferred launch
method
* Use **$desktop_entry** in the #RUN section if your launch method requires a
desktop entry file's absolute path or ID (e.g. **gtk-launch "$desktop_entry"**)

Cache is stored in **$HOME/.cache/sofi.cache** by default
* To use a different directory,  set **$dir_cache** to the desired filepath
(e.g. **/tmp/sofi.cache**)
* You can blacklist applications using the case statement in the #REBUILD CACHE
section

For theming and other fzf-related options, see man fzf(1).
