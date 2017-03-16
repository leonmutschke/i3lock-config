# My i3lock configuration #

i3lock is an awesome screen locker. Check out the official repository [i3lock](https://github.com/i3/i3lock).
This repository includes a script with my configuration. When locked, it should display your desktop being blurred.

Tested on Ubuntu Gnome 16.04 LTS.

### Install required packages: ###

<code>sudo apt install i3lock imagemagick, scrot</code>


### Make the script executable ###

Go to the path, where the script <code>my-i3lock-config.sh</code> is located. In my case it is in my home folder <code>$HOME/my-i3lock-config.sh</code>. Now we want to make the script executable. Best way is to create a directory <code>bin</code> in the homedir (<code>mkdir -p ~/bin</code>). Then write a new script <code>lock</code> that runs the script <code>my-i3lock-script.sh</code> and save it in <code>~/bin</code>. Then make it executable.

<pre><code>$ mkdir -p ~/bin
$ cat > ~/bin/lock << 'EOF'
$ #!/bin/sh
$ exec $HOME/lock.sh
$ EOF
$ chmod +x ~/bin/lock
</code></pre>

You need to log out and back in again, if you haven't had a <code>~/bin</code> directory before. This will add it to your PATH. Now you should be able to run <code>lock</code> from the command line and it should lock the screen.

Now you can use this and set a custom keybinding in your keyboard settings. Create a new shortcut and give it a name. The command we want to set is <code>lock</code>. Then add the keybinding. And now test it, it should work. 
