# stm32_tpm2_spi

This is an extremely bare-bones implementation of TPM2 comms over SPI, because I couldn't find another one on the Internet. Connects over uart at 38400, tested against SLB9670 (which does *not* require an SPI wait state).

References:

- https://stackoverflow.com/questions/71972273/spi-hardware-protocol-of-trusted-platform-modules-looking-for-minimal-working-e
- https://google.github.io/tpm-js/
- https://trustedcomputinggroup.org/resource/pc-client-work-group-pc-client-specific-tpm-interface-specification-tis/
