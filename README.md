# Custom-Login ( clogin )
*Make your own login page for GNU/Linux !*

It's **secure** and **fun** and of course **beautiful**.

Imagine you turn on your pc and see the login page **that you made for yourself**, for e.g:

![ alt text ]( ./login.png "damn beautiful :)")

You can customize it with what ever you want (EDIT)'s
##
### For your information
* This script uses `dialog`, so it should be installed on your OS. You can read more about it in the [linux man page](https://linux.die.net/man/1/dialog).
* Password is handeled just like linux shadow file ( hashed , salted and encrypted ) so be sure that this is secure.

##
## Installing
Before everything be careful because this script uses root privilages and needs the password, **There is no way to bypass**
so be carefull editing it ( I put `EDIT` on every editable line to help you )

For installing it:

`git clone https://github.com/alirezarpi/custom-login.git`

`cd custom-login && chmod +x clogin`

but **before running** it:

Open file `/etc/systemd/system/getty.target.wants/getty@tty1.service` with your favorite editor and
Change the line `ExecStart=-sbin/agetty ....` to this:

``
ExecStart=-/sbin/agetty --autologin root --noclear %I $TERM
``

Then open `Settings > Users` and enable `Automatic Login`

and finally in ``custom-login`` directory do `./clogin` as root and it's ready to go :)

##

Recommended Distros: Debian base ( Ubunt , Mint )

Note: Tested on Ubuntu 16.04 , Mint 18.3 , Fedora 27
