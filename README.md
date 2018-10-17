# Hi! Welcome to my bin.

This is where I keep all my executables. I save them in my bin, because my bin's in my path. And that's a good thing because it lets me take advantage of bash's autocompletion feature! Typing <kbd>d</kbd><kbd>i</kbd><kbd>v</kbd><kbd>Tab</kbd> lets me quickly call my "divider" function. This is especially neat when used directly in vim. Executing the vim command `:read !divider --width 15 --vim ':)'` yields `""""" :) """""`

Also check out my [dotfiles](https://github.com/AriSweedler/dotfiles) repo!

## bash\_prompt.sh

Here's a script that'll help you create a custom-made PS1. You can have a fun prompt script really easily! [Source](https://stackoverflow.com/questions/45761508/whats-the-difference-between-script-or-source-script-bash-script) the shell script upon startup. You can use your ~/.bashrc for this. [Here](https://unix.stackexchange.com/questions/129143/what-is-the-purpose-of-bashrc-and-how-does-it-work) is more info on the different run command files.

Boom! Just like that, you have a neat and fancy PS1. Now dive into the script and edit it if you want! All the color variables at the top are escape codes. So instead of being printed out, they simply set the terminal's pen color.

Check out the following links for more details:

1. Check out the [bash man page](https://linux.die.net/man/1/bash), the section titled "Prompting" (What does '\W' do?)

1. Learn more about escape codes for pretty colors in bash [here](https://misc.flogisoft.com/bash/tip_colors_and_formatting)

## divider

Man! Argument parsing in python is rad. Run `divider --help` if you wanna see what this thing does. It basically just makes it easy for me to create dividers in my code, just to make it look nice. Give it a quick read, it should be pretty understandable. It just prints the string you specify in the middle of a comment, using whatever comment syntax you feel like.

##################################### nice #####################################
################################# this is neat #################################
############################## lets call this art ##############################
####################### a haiku would look nice in this ########################
######## view this file in a fixed-width font to see how this lines up #########

## myRsynch.sh

When working on a big project, I tweak this to send the proper local folder over to the proper remote folder. It's useful so I don't have to repeat the boilerplate code. If you specify "file/", then you'll send the directory as a whole over. If you specify "file", WITHOUT the trailing slash, then you'll send over every item in the file. I prefer to send a whole directory over from the host (WITH trailing slash) to a destination folder (WITHOUT trailing slash). That way, I simply place/overwrite the folder.

## dockerPIDs.sh

Output the process ID of all running docker containers

## exchange.sh

Rename a variable in every file in a git repo

## connected <server>

Ping the server represented by argument once. Only wait for 100ms to recieved a response. Pipe all stdout and stderr to /dev/null. Using some syntactic sugar from bash, read more about the "&>" redirection operator [here](https://stackoverflow.com/questions/51715927/why-is-there-a-difference-between-and-but-not-and). (NOTE: It's different from the ">&" operator used in "1>&2"!)

## cowsay-pwd

lmaoooooo

Or should I say lmoooooooooooo

I have the cowsay application stuck in my bin, and I placed `alias pwdd='. cowsay-pwd'` in my .bash_rc file, so I can laugh at how stupid I am whenever I want. A short explanation of the script:

1. You should know what `cowsay -f <animal> <text>` does. If not, read about cowsay [here](https://askubuntu.com/questions/527501/what-cowsay-characters-does-ubuntu-have-by-default-and-how-can-i-test-them). I learned about cowsay from this article: [cool terminal command](http://smashingtips.com/linux/cool-terminal-commands-for-linux).

2. `cowsay -l` lists all the possible animals 3. `tr -s ' ' '\n'` reformats the output such that there's one animal per line

4. `tail -5 | head -1` cuts off all but the last 5 lines, then all but the first line. This effectively selects text only on the 5th to last line. I could also accomplish this with a handsome text editor like [sed](https://stackoverflow.com/questions/6022384/bash-tool-to-get-nth-line-from-a-file) or awk, but I kinda like how beautifully simple and sloppy it is. It makes me smile n laugh, and I'm actually pretty proud of how easy this was for me, `jot` was the only thing I had to look up, so I'm keeping it.

5. `jot -r 1 1 50` Gives me one random number between 1 and 50 inclusive. I just wanted a simple and easy RNG bash tool. This is the driving force behind this whole tool! More info on how to get [random numbers in a shell](https://stackoverflow.com/questions/2556190/random-number-from-a-range-in-a-bash-script)

6. Now that we've taken a random line from our list of animals, we'll just invoke `cowsay -f $ANIMAL $TEXT`, where text is our pwd, to put a nice lil skin over the regular pwd function. Neat! Fun fact, I called this with $PWD instead of \`pwd\` because \`pwd\` in a shell script will return the pwd of the script, NOT the user's pwd. If I had aliased this, then \`pwd\` would have worked.

You can see what it looks like on my
[twitter](https://twitter.com/Adsweed/status/954638087660777475). Or here:
![cowsay pwd](img/cowsay-pwd.png)

## cowsay-fortune

This idea is funny

## swork & work

Set a work directory and restore it
