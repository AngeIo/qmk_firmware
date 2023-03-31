# AngeIo's Planck Layout

## Key features
Similar to default layout with some minor changes:
- move mouse with `I` `J` `K` `L` and scroll with `P` `:` when holding `Fn`
- fixed startup sound not working when keyboard is plugged in
- 2u spacebar (MIT layout)

## Build instructions
- Clone the entire repo with submodules `git clone --recurse-submodules https://github.com/AngeIo/qmk_firmware.git`
- `cd /path/to/qmk_firmware`
- Run the install script `util/qmk_install.sh`
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
