# Arcticons Freedesktop Theme

This is an adoption of the arcticons icons for Linux desktop managers like GNOME and KDE.

## Generating the icons

**Important:** to generate the icons you need to clone the parent repo <https://github.com/Donnnno/Arcticons> with the `--recurse-submodules` argument (or run `git submodule update --init` afterwards) and switch to the `freedesktop-theme` folder.

The `./generate-manual.sh` script can be used to generate the icons according to the mappings file. it accepts two arguments:

`./generate.sh black/white <stroke thickness>`

The first argument is used to control whether the white or the black icons are generated. (default is white)

The second argument is a number which controls the stroke thickness of the generated icons. (default is 1)

After the icons are generated, there is a folder `arcticons` and a `arcticons.tar.gz` file.

## Manual installation

You can install the icon theme by copying the `arcticons-light` and/or `arcticons-dark` folder into `~/.local/share/icons` for an user-wide installation or into `/usr/share/icons` for a system-wide installation.

## Applying the icon theme

In GNOME Shell, you can either use the Terminal and type the command `gsettings set org.gnome.desktop.interface icon-theme <arcticons-light/arcticons-dark>` or use the GNOME Tweaks GUI to change the icon theme to Arcticons Light or Dark. (To change the icons for Qt/KDE applications in GNOME as well, you need to open `qt5ct` and/or `qt6ct` and select the icon theme there)

In KDE, you can select the icon theme in the System Settings > Icons.

## Mapping the icons

The `mappings.txt` contains the mappings of the arcticons in the format `<Arcticon icon name>,<Freedesktop icon path>:<Freedesktop icon path>`

When one Arcticons icon is used for multiple icons in the freedesktop theme, the paths are separated by a `:`.

To contribute, you need to look the path of the priginal icons. Application icons are in `/usr/share/icons/hicolor/<icon size>/apps`, while system icons are covered by the other icon themes. (In GNOME, the default is Adwaita; For KDE Plasma, it's Breeze) The icons are either in the `<icon size>/<icon category>`, or in `<icon category>/<icon size>` subfolders.

For example, the icon for the Steam application is in `/usr/share/icons/hicolor/<icon size>/apps/steam.png`, while the system icon for Wi-Fi is in `/usr/share/icons/Adwaita/symbolic/devices/network-wireless-symbolic.svg`. The `-symbolic` part of the file name specifies, that the icon is theme-aware, but because only the fill color and not the stroke color is theme-aware, Arcticons can't take advantage of this.

The Freedesktop icon path in the mapping file refers to the path `<icon category>/<icon size>`, without the file extension. So `/usr/share/icons/hicolor/<icon size>/apps/steam.png` is written as `apps/steam` in the mappings file.

Some application files may also be found in the `/usr/share/pixmaps` folder, then the mapping path is `apps/<icon name>`.

## Contributing own icons

To contribute icons, which don't fit into the Android icon pack, you can place them into the `icons_linux` folder (there has to be one with stroke color `#000` in the `black` folder and one with stroke color `#fff` in the `white` folder). The style of the icons and the structure of the SVGs have to follow the style used in the parent repo.

Then follow the section [Mapping the icons](#mapping-the-icons) the put the mapping into the `mappings.txt`.

## Screenshots

![160259223-c419e600-fa67-48d6-be9f-dc86945b5978](https://github.com/Donnnno/Arcticons-Linux/assets/31142286/59f5fce5-0cd3-4bc2-82a8-b097eefbeb2f)

![24eb69654801089f](https://github.com/Donnnno/Arcticons-Linux/assets/31142286/c7348690-cc56-4d6c-9cfb-bc2d65ba5a39)
