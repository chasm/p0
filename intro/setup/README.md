# The Tools of the Web Developer

## Learning objectives

1. Learn what the terminal is, what a shell is, and a few basic shell commands.
2. Learn what version control is, install **git**, and learn a few essential git commands.
3. Set up a GitHub account, learn how GitHub differs from git, and create your first repository.
4. Learn the differences between word processors, rich text editors, text editors, and integrated development environments and why you should only use the last two for code.
5. Install and configure Sublime Text 3.
6. Install and configure Chrome and learn a bit about Chrome's Developer Tools.
7. Get a brief overview of other useful tools we may use during the course.

## The terminal

The <strong style="color:red">terminal</strong> is the tool we use to converse with the computer's operating system. We can use it to ask questions, examine the contents of the computer's memory, and to run or test our applications. You'll be using the terminal every day, so get used to it. It will be your best friend if you'll let it.

The terminal is also called the <strong style="color:red">shell</strong> (because it forms a sort of "shell" around the operating system with which we can communicate) or the <strong style="color:red">command line</strong> (because we use it to issue commands to the computer).

Linux, Mac OS X, and Windows all come with terminal applications. The terminals on Linux and Mac are easiest to use as much of the software we'll be using was developed on Unix-like operating systems, and both Linux (an open source version of Unix) and OS X (based on a Unix-variant called BSD) are Unix-like, whereas Windows is in another universe entirely.

On Mac OS X, we recommend that you install the [iTerm2](https://www.iterm2.com/) terminal as it is a bit more powerful than the terminal that comes natively with OS X. On Linux, there is a [variety of terminals](http://www.slant.co/topics/794/~what-is-the-best-linux-terminal-emulator) from which to choose, but the default terminal works just fine.

<figure>
  <img src="/images/the-terminal.png" alt="The terminal"><br>
  <figcaption><p>The terminal (iTerm2 on OS X)</p></figcaption>
</figure>

### Commands

The terminal is where we enter commands as "magic spells". Each command tells the computer to do something, and the computer will respond in some fashion. Be careful what you tell the computer to do! It has no sense of humor at all, and it will carry out your commands no matter how foolish they may be. You can easily make a mess of things, so type carefully and double check yourself *before* you hit that Enter key!

When you open the terminal application, the terminal starts up a "shell" program that knows a few human-understandable commands in plain text. You can then talk to the shell using these commands. The first command we'll learn is how to tell the shell to go away (i.e., close):

```bash
> exit
```

Note that the symbol at the start of the line (in the above instance the `>` symbol) is called the "prompt" because it prompts you for input. The prompt can be very different on different terminals and in different shells. Often it includes information, such as the time, the current user, the current folder, etc. So don't be surprised to see all sorts of things as prompts. And note: this is personalizable, so you can set your own terminal prompt to be exactly what you want it to be. Our recommendation: keep it simple to start.

The `exit` command does exactly what you'd expect: it exits the terminal shell (and may also close the terminal window, depending on your settings).

Here are some more commands:

#### pwd

Your shell runs in a particular directory (folder). When you first open the terminal and start the shell, this is probably your home directory, abbreviated `~`. As you're using the shell, you can navigate to different directories to find various files and open them or execute them (if they're applications). The first step is to figure out what directly you are currently in, which is called the <strong style="color:red">working directory</strong>.

We can do this with `pwd`, which stands for "print working directory". By print we mean "to the shell". Don't worry, your printer won't start up. If you type `pwd` in your terminal, the shell will respond with the current working directory. Try it.

Here is what it looks like on my machine:

![pwd](/images/pwd.png)

You can see that my prompt includes some information. The line starting with # tells me that both my user and computer are named "aries", that I'm currently working in my home folder (`~`), and that the time is around 4 PM wherever I am. The line that begins with the $ is where I type my commands. Here I've typed `pwd`. The line that follows is the response from the computer, which shows that I'm in the `Users/aries` folder, which makes sense as my username is (from the prompt), *aries*.

(I name my computers after zodiac signs and call my home network, "zodiac". My brother names his computers after planets. Go figure.)

#### ls

It might also be nice to see what is in this folder. We can do that with the "list" command, which is abbreviated to `ls`:

![ls](/images/ls.png)

This lists the contents of my home (`~`) folder in columns. My terminal is set to color-code things, so folders, files, etc. show up in different colors. This is the most basic form of listing folder contents. But I might want more information about each folder or file. How can I do that?

The way to find out is to ask the computer for help. We can ask it for help on the `ls` command by adding an "argument" to the command. There are two kinds of arguments. The first are built in arguments, meaning that the command already knows what they mean. The second kind is input from me.

Known arguments are preceded by `--`, or, in shortened form, by `-`. For example, one common argument that almost every command recognizes is the request for help. In long form this looks like this: `--help`. But there is usually a short form as well: `-h`.

Interestingly, neither of the commands we've learned so far, `pwd` and `ls`, provides help. In these cases, we have to call upon serious mojo to find out how the commands work: we'll have to RTFM: *read the funny manual*. (OK, the F doesn't stand for "funny", but we're trying not to offend anyone here. Feel free to substitute the F word of your choice.)

#### man

We can see the options on the `ls` command (or almost any other) by calling up the manual page for the command:

```bash
man ls
```

This opens a text reader in the terminal that shows the manual page(s) for the `ls` command. To page down, hit the space bar. <strong style="color:red">To quit the text reader, hit the q (for quit) key.</strong> Try it!

From the manual we learn that we can see the list in long format by adding the `-l` argument:

![ls -l](/images/lsl.png)

Be sure to use the manual to learn the options for all the commands you use. The manual is your friend.

Now, how do we change directories? Well, naturally, with the `cd` (change directory) command.

#### cd

We can use the `cd` (change directory) command to move through the directories in our computer's filesystem.

Typing `cd` without an argument is the same as typing `cd ~`: it takes us to our home folder. Here, the `~` is the second type of argument to a terminal command: it is one that we make up. True, `~` is a symbol the shell recognizes, but I could as easily go to my home folder by using the path to that folder:

```bash
cd /Users/aries
```

This won't work on your computer, however, unless you're using a Mac and your username is also *aries*. That's what I mean when I say that these kinds of arguments are the kind we make up ourselves, as opposed to the small set of options that come built-in to the command. These pre-built options are often called **command line options** or <strong style="color:red">flags</strong> or <strong style="color:red">switches</strong> to distinguish them from the command line arguments or <strong style="color:red">parameters</strong> that we make up ourselves.

Flags or switches are easily distinguished: they are the ones preceded by `-` or `--`.

Besides the `~` symbol that represents our "home" folder, there are two other important symbols that we can use to represent folders on our system, but these are *relative to the current folder*. The first is `.`, which represents the current folder itself. As a result, `cd .` doesn't do anything. It tells the shell to change the directory to the current one. Um, say what?

So why have a `.` for the current folder? Well, it is useful when we want to tell the shell to look for something *starting in the current folder*, as we'll see later.

The other special symbol we'll need is `..`, which stands for the current folder's *parent* folder. If we want to jump up one folder in the folder hierarchy, we can simply do `cd ..`. And we can jump multiple folders by using the "path separator" (`/` on Unix-like systems and `\` on Windows, just to be ornery). So the following changes the working directory to its great grandparent on a Unix-like system:

```bash
cd ../../../
```

Why don't we have a symbol for child folders? Think about that for a while, and consider the nature of a "tree structure", which is what the filesystem is.

That's enough to get started&mdash;`pwd`, `ls`, `cd`, and `exit`. You can play around with those and practice moving from one folder to another. We'll learn many more commands over the coming weeks.

Oh, one more, for fun. Want to know what your username is? Try this one:

```bash
whoami
```

##  Version control



## Text editors

There are numerous text editors that we can use to write our code, and which one we use is mostly a matter of personal preference. But what's most important is that we use either a <strong style="color:red">text editor</strong> or an <strong style="color:red">integrated development environment</strong> (IDE). What we *don't* want to use is a **word processor** or **rich text editor**.

The reason we want to avoid word processors (such as Microsoft Word or OpenOffice.org Writer) and rich text editors such as Microsoft's WordPad is because they add hidden markup to the text to tell the editor how to display it. We'll be writing code, so we want *all our text* to be visible. No hidden nothing!

Text editors fall into two classes, essentially: GUI (graphical user interface) editors that use a window, and editors that work in the terminal itself. In the first class (GUIs), we have [Sublime Text 3](http://www.sublimetext.com/3), [Atom](https://atom.io/), and [TextMate 2](https://macromates.com/download) (Mac only). Of these, Sublime Text 3 is the most popular, but GitHub's Atom is gaining ground. TextMate was the former, long-running champion, but slow development has cost it dearly. There are a few other interesting options around, such as [Light Table](http://lighttable.com/). which looks promising. Your mileage may vary.

The second class of text editors include [vi](https://en.wikipedia.org/wiki/Vi), [vim](https://en.wikipedia.org/wiki/Vim_(text_editor)), [emacs](https://www.gnu.org/software/emacs/), and more. These are very powerful editors, and are incredibly fast once you learn how to use them. The key phrase, however, is "once you learn how to use them". The learning curve for these apps is long and painful. We don't recommend them for beginners, but once you've mastered the basics of web application development, they are worth checking out.

Integrated development environments (IDEs) are far more complex. The provide many benefits beyond those available in a text editor (although with plugins, many text editors are nearly as powerful). IDEs are more commonly used for *compiled* programming languages, such as C, C++, Java, Scala, C#, and F#. Some of the more popular ones are [Eclipse](https://eclipse.org/downloads/) (free), [NetBeans](https://netbeans.org/) (free), [IntelliJ IDEA](https://www.jetbrains.com/idea/) (expensive), and, of course, [VisualStudio](https://www.visualstudio.com/) (expensive, and Windows-only). For a beginner, an IDE is probably a lot more than you need.

At EDA, we are standardized on Sublime Text 3, so we suggest you get familiar with it now.


## Browsers

There are numerous web browsers from which to choose, including Internet Explorer, Safari, Chrome, Firefox, Opera, and more. Which one you choose to use for browsing the Web is up to you. But for development, we strongly encourage you to use Chrome.

Chrome has the most full-featured set of developer tools of any browser, with Mozilla's Firefox a close second. As you become a more experienced developer, you should install as many browsers as you can from the set of popular web browsers and become familiar with the quirks of each. But when you're just starting out, it's easier, as with text editors, to choose one, and currently [Chrome](http://www.google.com/chrome/) (from Google) is the best.

Once you have Chrome, you can open the Developer Tools in one of three ways:

1. Right-click on an item on the page and select "Inspect Element" from the context menu that appears.
2. Click on the "hamburger menu" in the upper right navbar on Chrome, then select "More Tools > Developer Tools".
3. Use the keyboard shortcut (e.g., Cmd-Alt-I on a Mac).

To close the Developer Tools, click the X in the upper right corner of the Developer Tools panel. Note that you can move the panel to either the bottom or the right side of the window, or pop it out entirely into its own window, using the small icon button next to the X button.

![Developer Tools](/images/dev-tools.png)

We'll be learning a lot more about Chrome's Developer Tools as we go along.

## Other tools


## Glossary

<dl>
  <dt>terminal</dt>
  <dd>
    A computer terminal is an electronic or electromechanical hardware device that is used for entering data into, and displaying data from, a computer or a computing system. [<cite><a href="https://en.wikipedia.org/wiki/Computer_terminal">Wikipedia</a></cite>]
  </dd>
  <dt>shell or command-line interface</dt>
  <dd>
    A user interface for access to an operating system's services. In general, operating system shells use either a command-line interface (CLI) or graphical user interface (GUI), depending on a computer's role and particular operation. [<cite><a href="https://en.wikipedia.org/wiki/Shell_(computing)">Wikipedia</a></cite>]
  </dd>
  <dt>bash</dt>
  <dd>
    Bash is a command processor that typically runs in a text window, where the user types commands that cause actions. Bash can also read commands from a file, called a script. The name itself is an acronym, a pun, and a description. As an acronym, it stands for Bourne-again shell, referring to its objective as a free replacement for the Bourne shell. As a pun, it expressed that objective in a phrase that sounds similar to born again, a term for spiritual rebirth. The name is also descriptive of what it did, bashing together the features of sh, csh, and ksh. [<cite><a href="https://en.wikipedia.org/wiki/Bash_(Unix_shell)">Wikipedia</a></cite>]
  </dd>
  <dt>zsh</dt>
  <dd>
    An alterntive to bash that some of the instructors and developers at EDA prefer. The Z shell (zsh) is a Unix shell that can be used as an interactive login shell and as a powerful command interpreter for shell scripting. Zsh can be thought of as an extended Bourne shell with a large number of improvements, including some features of bash, ksh, and tcsh. [<cite><a href="https://en.wikipedia.org/wiki/Z_shell">Wikipedia</a></cite>]
  </dd>
  <dt>version control (source control, revision control)</dt>
  <dd>
    A component of software configuration management, revision control, also known as version control or source control, is the management of changes to documents, computer programs, large web sites, and other collections of information. [<cite><a href="https://en.wikipedia.org/wiki/Version_control">Wikipedia</a></cite>]
  </dd>
  <dt>GitHub</dt>
  <dd>
    GitHub is a Web-based Git repository hosting service, which offers all of the distributed revision control and source code management (SCM) functionality of Git as well as adding its own features. Unlike Git, which is strictly a command-line tool, GitHub provides a Web-based graphical interface and desktop as well as mobile integration. It also provides access control and several collaboration features such as bug tracking, feature requests, task management, and wikis for every project. [<cite><a href="https://en.wikipedia.org/wiki/GitHub">Wikipedia</a></cite>]
  </dd>
  <dt>text editor</dt>
  <dd>
    A text editor is a type of program used for editing plain text files. Text editors are provided with operating systems and software development packages, and can be used to change configuration files, documentation files and programming language source code. <a href="https://en.wikipedia.org/wiki/Comparison_of_text_editors">Editors compared</a>. [<cite><a href="https://en.wikipedia.org/wiki/Text_editor">Wikipedia</a></cite>]
  </dd>
  <dt>integrated development environment (IDE)</dt>
  <dd>
    An integrated development environment (IDE) is a software application that provides comprehensive facilities to computer programmers for software development. An IDE normally consists of a source code editor, build automation tools and a debugger. Most modern IDEs have intelligent code completion. [<cite><a href="https://en.wikipedia.org/wiki/Integrated_development_environment">Wikipedia</a></cite>]
  </dd>
</dl>


## Resources

- Terminal applications
    - [iTerm2](https://www.iterm2.com/)
    - [Linux terminal options](http://www.slant.co/topics/794/~what-is-the-best-linux-terminal-emulator)
- Source control management (SCM)
    - [git](https://git-scm.com/)
    - [GitHub](https://github.com/)
    - [ProGit book](https://progit.org/)
- Text editors
    - [Top 3 Text Editors for Mac](http://www.guidingtech.com/29369/top-code-text-editor-mac/)
    - [Sublime Text 3](http://www.sublimetext.com/3)
    - [Atom](https://atom.io/)
    - [TextMate 2](https://macromates.com/download)
    - [Light Table](http://lighttable.com/)
- Web browsers
    - [Chrome](http://www.google.com/chrome/)
    - [Firefox](https://www.mozilla.org/en-US/firefox/new/)
    - [Opera](http://www.opera.com/)
