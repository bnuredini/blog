+++
title = 'Terminal User Interfaces'
draft = true
date = 2025-05-20
+++

# Terminal User Interfaces
 
Terminal user interfaces (TUIs) have been experiencing something of a revival lately. For example,
[this repository](https://github.com/rothgar/awesome-tuis) lists more than 350 projects, almost 300
of which have over 1000 stars and have received a commit within the last year. This data doesn't
really tell us whether these projects are any good, of course, but it does show the sentiment: TUIs
are back in style. It's been interesting to see a new wave of users adopting these tools for
day-to-day work. I'm not just talking about users who refuse to leave the comfort of their
terminal or those who like post screenshots of their Linux desktops on the Internet -- I'm talking
about users who just want to get their work done and move on with their day. 

Even big corporations have started shipping small TUI utilities instead of just doing the obvious
thing (that, of course, being: shipping a browser in the form of an Electron app because that's what
we do in 2025).

Looking at how user interface have evolved over the years, you can see that the TUI model for
representing interactive UI elements via text was pretty common before it became apparent that
interactive elements like menus, button, windows, icons, modals, and input fields could be better
represented via a visual medium that wasn't limited by what a terminal could render. The graphical
model is more flexible and expressive because it can render UI elements more distinctively. This not
only makes some interfaces easier to use, but it makes possible interfaces that couldn't have been
conceived of in the terminal. It makes programs that are trying to solve inherently complex problems
(think Photoshop, Figma, Unreal Engine) possible by adding support for rendering high-quality assets
(images, videos, and 3D objects), integrating with the host operating system (notifications, file
pickers, and other native OS features), smooth animations, and graphical richness. So TUIs -- which
even then were used primarily by more technical users -- remained a niche and then dropped into
popularity even further. 

Considering these limitations (or maybe because of these limitations), I sense that TUIs got a
mini-revival in certain programming communities where people would show off screenshots of their
desktops, usually running Linux, usually with a terminal on the side with a TUI program opened for
managing files or listening to music. I was always under the impression that this had something to
do with the hacker-like aesthetic, but I've been seeing new frameworks and
libraries like [BubbleTea](https://github.com/charmbracelet/bubbletea), [Textual](https://github.com/Textualize/textual), [Ratatui](https://github.com/ratatui/ratatui),
so often now and it looks like this interface is now popular among a new set of users and I was
curious to know why.

Before thinking about what it is that people are getting from these kinds of interfaces, I though
I'd first take a look at my own workflow to understand what these tools have been doing for me.
Since I'm quite fond of spending time on the terminal myself, I find TUIs to be great for certain
use cases. Looking at my own day-to-day workflow, I can outline these benefits: 

* an interface for computers that can't render GUI applications,
* an interface for controlling another computer remotely using SSH with easier interactivity than
  using a sequence of commands,
* fast,
* lightweight,
* lots of keybindings,
* more customizable, and
* rendered on a terminal.

The first two points are only relevant for certain use cases and are not relevant for everyday use.
Thus, I suspect that, for most users, they're not a primary motivator for using a TUI.

Regarding all the other points (except for the last one): yes, they're relevant, but they're not
necessarily exclusive to TUIs. There's no reason why a good graphical program can't provide
comparable speed, efficient use of resources, lots of customizability, or a plentiful number of
keyboard shortcuts -- in fact, you can argue that it could even do a better job in all regards.
However, in practice, it is often true that for many use cases (think programs for managing files,
inspecting system resources, listening to music, managing databases), TUI-based programs do a better
job of providing these features than their GUI counterparts.

So then why is it that TUIs are often better in these regards when there's nothing inherit to this
model that makes it more suitable for developing programs with these characteristics? I suspect that
the lack of keybindings has something to do with the expectations that most users have when they're
interfacing with a GUI application, namely that they don't expect a graphical program to be used
with an extensive amount of keyboard shortcuts. This could be why most GUIs don't tend to emphasize
this feature as much as the TUIs counterparts do. (To clarify, there are plenty of GUI applications
that have an extensive set of keybindings, it's just that most of them can't be or weren't meant to
be used via the keyboard exclusively.)

Inferior customization could be a consequence of user expectations as well. Most users typically
expect GUIs to just work and don't put as much emphasis on customizing their experience, so, again,
programmers writing graphical applications probably don't emphasize this feature as much as
programmers writing terminal tools do, so the consequence of that is that we get less GUIs with
support for very granular configuration options. TUI users, on the other hand, I think are typically more
inclined to modify the program to suit their personal preferences -- this could include changing the
colorscheme, icons, fonts, and the actions onto which keyboard shortcuts are mapped to.

Related to user expectations, it's worth pointing out that there's a cultural difference between the
two paradigms [1]. The fact that TUIs are harder to use for beginners means that the userbase is
composed of power users and development is meant to cater to the needs of those power users, and
thus features are much more sophisticated that they would have been otherwise. 

These reasons are relevant, but they're not really describing something that's inherit to this
model. Yes, the average TUI user appreciates these benefits (performance, low resource use,
customization, etc.) more than the average GUI user does, and sometimes there tends to be a
difference in terms of cultural mindset between the two userbases, but that's more to do with
coincidental reasons rather than inherit qualities. At the end of the day, a TUI will be running
inside of a window terminal. Even if that program is being rendered on [a GPU-rendered terminal emulator](https://alacritty.org),
it's still a program inside of a window, so these benefits aren't exclusive to TUIs.

An inherit advantage of the TUI model is that which limits in the first place: the terminal. (This
is the last point, mentioned on the list above.) People who live on their terminals prefer to keep
most of their everyday programs inside the terminal because it acts a layer, an operating system of
sorts, for them to work on top of [0]. Having everything in your terminal means that you get to use
one set of keybindings for creating and switching through tabs, splitting panes, running scripts,
and more. 

It also means that, visually, the contextual switch that occurs when you go from one program to the
other (e.g., from you editor to your file manager) is minimal because (1) you can have them both use the
same colorscheme, (2) they both look similar because they're limited by what can be drawn on the
terminal, and (3) have similar keybindings for similar behavior because terminal-based programs tend to
follow common conventions more than their GUI counterparts (think, for example, how ubiquitous Vim
keybindings are).

It's been interesting to see more and more stuff moving onto the terminal. For decades people have
been saying that text it too primitive as an interface; in fact, some might lead to
think that text isn't good enough even for developing software (see attempts at visual programming).
Yet, text is still such a powerful way of defining interaction that it's use has not only persisted,
but grown. Windows -- which for years tried to promote graphical interfaces for everything and had
very poor terminals -- finally "admitted defeat" by making the Windows Terminal in 2019. The main
form of interaction with LMMs, as of right now, is via text. I would also like to believe
that this is a counter-reaction to how normalized it has become to ship Electron apps. It's feels 
great when your music player takes [46 MiB of memory instead of 1 GiB](https://github.com/hrkfdn/ncspot/blob/33ccf944e9701e40edd8479c533a03815e36a8e5/doc/resource_footprint.md?plain=1#L4-L7).

One thing that I don't feel too comfortable with is when I look at everything that's been happening
with Neovim: it often feels like people are just mapping GUI patterns onto the terminal and I'm not
always sure if I like it. Sometimes it feels like it defeats the purpose. One would hope that we
don't start using a primitive system like text as a base for building complex user interfaces like
we did with the web where we started building gigantic web applications on top of a system that was
meant to be used for making [hypertext] documents. 

Still, I'm happy that we now have great terminals like [WezTerm](https://github.com/wezterm/wezterm),
[Kitty](https://github.com/kovidgoyal/kitty), and [Ghostty](https://github.com/ghostty-org/ghostty)
that are both feature-rich and fast. My workflow has changed so much during the last few years and I
keep findings new gems in terminal world.

---

[0] A common, misguided belief is that these users prefer the terminal because of the aesthetics or
because it acts as a form of virtue signaling, which may very well be the case for some, and might
have been for me too when I was a more impressionable programmer; but, I think there are pragmatic
reasons why the terminal interface works so well for programmers.

[1] And I didn't list this as a benefit because I'm still unsure whether it really is a benefit --
considering that it's debatable whether the pros outweigh the cons.
