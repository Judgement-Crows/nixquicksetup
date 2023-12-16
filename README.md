# Hyprland

# Dependencies
- [aylurs-gtk-shell](https://github.com/Aylur/ags/wiki/installation)
- sassc
- swww
- nerdfonts
- brightnessctl
- slurp
- grim
## optional
- asusctl
- supergfxctl
- hyprpicker
- wf-recorder
- wayshot
- imagemagick
- wl-gammactl
- pavucontrol
- swappy
- python
- python-pam

```bash
sudo nixos-rebuild boot --flake github:rubixcube199/dotfiles.nix --impure # impure allows the path /etc/nixos/configuration.nix to be evalutated remotely for install

sudo reboot --force # there is an issue with services stopping in 23.11 && 24.05pre (as of this edit)

git clone https://github.com/Aylur/dotfiles.git
cd ags/
nix build
cd ~
nix profile install github:Aylur/ags

git clone https://github.com/rubixcube199/nixos-needed-extras-hyprland
```

## Bindings
some bindings you might want in your hyprland.conf

reload
```
bind = Super, R,  exec, ags quit; ags -b hypr
```

opening windows
```
bind = Super, A,       exec, ags -t applauncher
bind = ,XF86PowerOff, exec, ags -t powermenu
bind = Super, Tab,     exec, ags -t overview
```

screenshot & screenrecord
```
bind = ,XF86Launch4, exec, ags -r 'recorder.start()'
bind = ,Print, exec, ags -r 'recorder.screenshot()'
bind = Shift,Print, exec, ags -r 'recorder.screenshot(true)'
```

brightness adjusting
```
bindle=,XF86MonBrightnessUp,   exec, ags -r 'brightness.screen += 0.05; indicator.display()'
bindle=,XF86MonBrightnessDown, exec, ags -r 'brightness.screen -= 0.05; indicator.display()'
bindle=,XF86KbdBrightnessUp,   exec, ags -r 'brightness.kbd++; indicator.kbd()'
bindle=,XF86KbdBrightnessDown, exec, ags -r 'brightness.kbd--; indicator.kbd()'
```

volume adjusting
```
bindle=,XF86AudioRaiseVolume,  exec, ags -r 'audio.speaker.volume += 0.05; indicator.speaker()'
bindle=,XF86AudioLowerVolume,  exec, ags -r 'audio.speaker.volume -= 0.05; indicator.speaker()'
```

Please understand that this is my personal configuration for my setup. If something doesn't work, feel free to open up an issue or message me, and I will try to help. However, before doing that, make sure you read the error output, use some common sense, and try to solve the problem yourself if it is something simple.
