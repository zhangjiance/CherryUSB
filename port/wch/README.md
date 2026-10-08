# Note

> To compile support for CherryUSB on WCH chips, please refer to the repository: https://github.com/Links0617/wch-support-cherryusb.git

## Support Chip List

## USBFS

- CH32L103
- CH32M103
- CH32F20x
- CH32V20x
- CH32V30x
- CH32V31x
- CH32H417

## USBHS

- CH32V205
- CH32V4x7
- CH32H417
- CH32X305
- CH58x
- CH645

## CH32V30x USBHS (port/wch/ch32v30x)

- CH32V30x

CH32V30x carries a **separate** high-speed device controller in addition to the
one covered above. It is a distinct IP: the register layout differs
(`CONTROL/HOST_CTRL/INT_EN/DEV_AD/FRAME_NO/...` versus
`CONTROL/BASE_MODE/INT_EN/DEV_AD/WAKE_CTRL/...`) and even the `R8_USB_CTRL` bit
assignment differs (`bit4 = DEV_PU_EN`, `bit5 = HIGH_SPEED` vs. `bit3 =
PHY_SUSPENDM`, `bit4 = DMA_EN`, `bit5 = DEV_EN`). It therefore lives in its own
directory instead of `port/wch/usbhs`.

Both controllers are present on the chip: USBFS is on PA11/PA12, USBHS is on the
dedicated high-speed pins. Pick the one your board is wired to.
