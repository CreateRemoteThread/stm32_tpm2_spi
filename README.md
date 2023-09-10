# stm32_tpm2_spi

This is an extremely bare-bones implementation of TPM2 comms over SPI, because I couldn't find another one on the Internet. Connects over uart at 38400, tested against SLB9670 (which does *not* require an SPI wait state).

Commands:

- 't' sends startup + getrandom
- 'z' sends startup, createprimary
- 'r' resets the device + small wait
- '-' and '+' change chipselect off/on
- 0a 0b 0c inserts a hexbyte into the buffer
- 's' sends a raw SPI frame (needs manual chipselect control)
- 'v' sends a raw command (does not need chipselect)

Uses a stdio retarget from https://shawnhymel.com/1873/how-to-use-printf-on-stm32/ for convenience.

References:

- https://stackoverflow.com/questions/71972273/spi-hardware-protocol-of-trusted-platform-modules-looking-for-minimal-working-e
- https://google.github.io/tpm-js/
- https://trustedcomputinggroup.org/resource/pc-client-work-group-pc-client-specific-tpm-interface-specification-tis/
