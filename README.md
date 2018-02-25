# Custom-Login ( clogin )
*Make your own login page for GNU/Linux !*

It's **secure** and **fun** and of course **beautiful**.

Imagine you turn on your pc and see the login page **that you made for yourself**, for e.g:

![ alt text ]( ./login.png "damn beautiful :)")

You can customize it with what ever you want (EDIT)'s
##
### For your information
* This script uses `dialog`, so it should be installed on your OS. You can read more about it in the [linux man page](https://linux.die.net/man/1/dialog).
* Password is handeled just like linux shadow file ( hashed and encrypted ) so be sure that this is secure.
* For now it doesn't work with gpg version above 1. ( *TODO*: It has agent problem <Help> you can encrypt with another encryption instead of gpg )

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

```
ExecStart=-/sbin/agetty --autologin root --noclear %I $TERM
```
