[![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

# natural-gentoo-remastered
This theme is a sort of remaster of [natural-gentoo](https://jtyr.github.io/natural-gentoo), an old GRUB and Splashutils theme I found on the Internet a while ago that I couldn't install, possibly due to its age, so I decided to remake it.

This repo contains both a GRUB theme and a Plymouth theme to customize the splash screen at the start.

# Installation
It should be noted that this README makes a few assumptions about the system it's going to be installed in. It's assumed that both GRUB and Plymouth are already installed and configured on your machine, and the initrd image is built using dracut (if done manually please refer to the documentation used to do so when performing the final step on "Configuring the system").

## Installing the theme
* For Gentoo, this theme can be installed with the "x11-themes/natural-gentoo-remastered" package available in [my overlay](https://github.com/foopsss/Ebuilds). Both parts of the theme can be installed individually with the "grub" and "plymouth" use flags.

* For other Linux distributions, the theme can be manually installed by copying and pasting the "natural-gentoo-remastered-grub" and/or "natural-gentoo-remastered-plymouth" folders into "/boot/grub/themes" and "/usr/share/plymouth/themes" respectively.

## Configuring the system
After installing the theme, the "grub" file at "/etc/default" has to be modified to add the following line:

	GRUB_THEME="/boot/grub/themes/natural-gentoo-remastered/theme.txt"

Also, natural-gentoo-remastered has to be set as the default Plymouth theme:

	plymouth-set-default-theme natural-gentoo-remastered

Finally, the GRUB configuration and the initrd image have to be rebuilt for the theme to be properly installed and detected by the system. It can be done with:

	grub-mkconfig -o /boot/grub/grub.cfg && dracut --force

If GRUB detected the theme succesfully it will output "*Found theme: /boot/grub/themes/natural-gentoo-remastered/theme.txt*". Meanwhile, dracut will output something like "*Creating initramfs image file '/boot/initramfs-*.img' done*".

# Caveats
* The background images for the theme are specifically tuned to my display, meaning their resolution is 1366x768. I don't know if there's a way to make the images more usable for other display sizes.
* The GRUB theme uses the standard stock font. This is something I haven't paid much attention to but I'm definitely open to changing it. It does not use scrollbars either because I don't have many boot options, but it's definitely something that can be added if others need it.

# License and Acknowledgements
This theme is published as-is with no warranties under the [Creative Commons Attribution-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-sa/4.0/legalcode) license, also known as CC-BY-SA 4.0. A full copy of the license is included in the repo.

It uses the [dark Gentoo logo](https://wiki.gentoo.org/wiki/File:Gentoo-logo-dark.svg) made by Lennart Andre Rolland and the Gentoo Foundation as part of the background images, as well as the "terminal_box_.png" files from the [Starfield](https://git.savannah.gnu.org/cgit/grub.git/tree/themes/starfield) GRUB theme made by Daniel Tschudi, which are licensed under the [Creative Commons Attribution-ShareAlike 2.5 Generic](https://creativecommons.org/licenses/by-sa/2.5/legalcode) and [Creative Commons Attribution-ShareAlike 3.0 Unported](https://creativecommons.org/licenses/by-sa/3.0/legalcode) licenses respectively, also known as CC-BY-SA 2.5 and CC-BY-SA 3.0.

The Gentoo logo and name are a trademark of the Gentoo Foundation, Inc. in the United States of America and regions that recognize it, and it's owned by Förderverein Gentoo e.V. in Europe, who defines the usage rights of the name and logo inside the territory.

Neither the Gentoo Foundation nor the Gentoo Project are in any way affilliated to this project and the Gentoo logo is used under the rules listed in the "Gentoo-related software projects" and "Service Identificacion" sections of the [Gentoo name and logo usage guidelines](https://www.gentoo.org/inside-gentoo/foundation/name-logo-guidelines.html).

# Credits
* The shield at the top of the README and the copy of the CC-BY-SA 4.0 come from the [cc-licenses](https://github.com/santisoler/cc-licenses) GitHub repo.
* The [CyberRe](https://www.gnome-look.org/p/1420727/) and Starfield GRUB themes, which helped me to understand GRUB themes.
* The "[Theme file format](https://www.gnu.org/software/grub/manual/grub/html_node/Theme-file-format.html)" section in the [GNU GRUB manual](https://www.gnu.org/software/grub/manual/grub/grub.html), for the much-appreciated information on how to make a theme.

# Special Thanks.
* Thanks to Ulrich Mueller from the Gentoo Licenses team and u/erkiferenc from the r/Gentoo subreddit, who helped me clearing my doubts around some of the details of the CC-BY-SA license and the usage of CC-BY-SA licensed materials. Also, thanks to u/gyakovlev and u/OptionalKarmotrine for taking the time of chimming in with some suggestions to help me with this problem when I asked about it.

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg
