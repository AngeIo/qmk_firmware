# AngeIo's Planck Layout

## Key features
Similar to default layout with some minor changes:
- move mouse with `I` `J` `K` `L` and scroll with `P` `:` when holding `Fn`
- fixed startup sound not working when keyboard is plugged in
- to use 2u spacebar, i disabled the right switch to prevent double space key presses

## Build instructions
- `cd /path/to/qmk_firmware`
- Ensure latest libraries are loaded `make git-submodule`
- Build with docker
  - Planck Rev. 6 : `util/docker_build.sh planck/rev6:AngeIo`
- Build with Vagrant
  - `vagrant ssh`
  - `cd /vagrant`
  - `make git-submodule`
  - Planck Rev. 6 : `make planck/rev6:AngeIo`
- Flash hex file
  - Using dfu-programmer `dfu-programmer atmega32u4 erase --force && dfu-programmer atmega32u4 flash .build/planck_rev4_narze.hex`
    - For Planck Light change the target microcontroller `dfu-programmer at90usb1286 erase --force && dfu-programmer at90usb1286 flash .build/planck_light_narze.hex`
  - Use [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases)
