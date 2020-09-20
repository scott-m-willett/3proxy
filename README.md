# 3proxy

A fork of the 3proxy project. Modified to be lightweight, and to be installed silently via the command line. Useful for lateral movement during penetration testing.

Original project: 
- https://3proxy.ru/
- https://github.com/z3APA3A/3proxy

Modifications
-------------

Minimal changes were made to the original project. I haven't included the source code. It is however available on the original project page, and the changes made are documented below:

- Makefile.msvc was modified to exclude the libraries libeay32.lib and ssleay32.lib, and remove the plugins FilePlugin SSLPlugin. This was due to compilation issues within windows.
- Line 392 of file src/3proxy.c was commented out. This was causing issues installing via the command line in a situation where you didn't have/need a GUI. Removed a messagebox popup.
- Compiled using the visual studio command line: nmake /I /K /f makefile.msvc
- Compiled files stripped down to what you see in this project
- Add a simplified 3proxy.cfg file with custom commenting, ready to serve a socks proxy

Recommendations
---------------

This is useful for penetration testing with Kali Linux in the situation you gain a meterpreter shell and want to use the machine for lateral movement.

I recommend cloning this repo to the /opt/3proxy directory.

You can also download this meterpreter script at () and download it to your /usr/share/metasploit-framework/scripts/meterpreter directory. With an administrator/system meterpreter shell, you can then run "run socks_proxy" to upload and install this proxy for use.
