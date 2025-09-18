# JM's Lemonbar

This is my old [Lemonbar](https://github.com/LemonBoy/bar) script. Lately, I use [this](https://github.com/jm-janzen/skel/blob/master/.config/polybar/config.ini) tricked out [Polybar](https://github.com/polybar/polybar),
but it's still fun to see how one would make an entire [i3](https://i3wm.org/) status bar by creating a format string

```shell
%{l} | %{F#00FFFF}jm%{F-} | OS: Linux 6.14.0-24-generic x86_64 | %{r} | CPU: %{F#00FF00}00%%%{F-} | MEM: %{F#FFFF00}63%%%{F-} | DSK: %{F#FFFF00}56%%%{F-} | THU : 2025-09-18 07:45:40 |
```

and piping it to lemonbar to get

```shell
| jm | OS: Linux 6.14.0-24-generic x86_64 | // | CPU: 00% | MEM: 00% | DSK: 00% | THU: 2025-09-18 07:45:40 | 
```

colours not shown here, but you get the idea. That kind of control is prettty neat!

### How to use with your i3 setup

Add or edit your `status_command` to look like this:

```i3config
bar {
    status_command exec $HOME/lemonbar/pybar.py | lemonbar -p -b
}
```

With path edited to be wherever you downloaded this repo to.

You can experiment with changing the output, or tweaking the `lemonbar` options by simplying entering this repo on your local machine and executing `./pybar.py | lemonbar`.
For example, if you wanted to output to a specific monitor, you could look it up with `xrandr --listactivemonitors` then use the following command `.pybar.py | lemonbar -o HDMI-1` (or whatever your monitor is designated as).
