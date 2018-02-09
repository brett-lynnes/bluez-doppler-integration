## SandmanDoppler-specific build/dev instructions

### Development

A new `sandmanDoppler.Makefile` and `sandmanDoppler` BR2_Ext directory have been created. This will keep sandmanDoppler's changes separate from upstream Buildroot, and separate from the upstream Gadget-OS. The `sandmanDoppler/` external path is more or less a duplicate of the `gadget/` external path. As such, all configuration can and should happen there. This strategy will help us move forward as quickly as possible, ideally without any merge issues, while being able to track our latest supported configurations.

### Builds

Builds are completed the same way as in Gadget-OS, which only slightly differs from Gadget-Buildroot. Steps to set up/modify/build/flash are as follows:

#### For CHIP Pro
`./scripts/init-container`

`make -f sandmanDoppler.Makefile sandmanDoppler_defconfig`

`make -f sandmanDoppler.Makefile menuconfig`

`make -f sandmanDoppler.Makefile linux-menuconfig`

`make -f sandmanDoppler.Makefile savedefconfig`

`make -f sandmanDoppler.Makefile`

`sudo ./scripts/flash-gadget-chip-toshiba`

All defconfigs now point to copies in `sandmanDoppler/configs` or `sandmanDoppler/board/sandmanDoppler/chippro/configs`