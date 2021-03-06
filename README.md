Dwarf Fortress
====

This repo contains the data necessary to compile Dwarf Fortress into a Flatpak.
Currently 0.43.03 w/ dfhack is 32-bit only, so you need to install 32-bit versions of the Flatpak platform and SDK.
0.43.05 doesn't have dfhack but it is 64-bit, and such doesn't need the 32-bit layer anyway.

To build it you need the freedesktop platform and SDK, which can be installed in the following manner;
```
$ wget https://sdk.gnome.org/keys/gnome-sdk.gpg
$ flatpak --user remote-add --gpg-import=gnome-sdk.gpg gnome http://sdk.gnome.org/repo
$ flatpak --user install gnome org.gnome.Sdk 3.22
$ flatpak --user install gnome org.gnome.Platform 3.22
```

For 32-bit;
```
$ wget https://sdk.gnome.org/keys/gnome-sdk.gpg
$ flatpak --user remote-add --gpg-import=gnome-sdk.gpg gnome http://sdk.gnome.org/repo
$ flatpak --user install --arch=i386 gnome org.gnome.Sdk 3.22
$ flatpak --user install --arch=i386 gnome org.gnome.Platform 3.22
```

To build and install/run the application you can do the following;
```
$ make
$ make install
$ make run
```

The application data when run can be found in `~/.var/app/com.bay12games.DwarfFortress/df_linux`

### TODO

- Clean up more unnecessary data
- Improve install steps, strip down configure parameters to just what's needed
- Perhaps work the Dwarf Fortress folders into a more XDG-ish state
  (~/data, ~/cache, ~/config, etc)
- Make a proper readme
- Look into possibly packaging and publishing the package somewhere, depending on what bay12games thinks about it
