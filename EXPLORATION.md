# Set up

- Download Swift version 6.0 (https://www.swift.org/download/#snapshots)
- Set your version of Swift in your CLI to the latest version
    - What version are you running? `swift --version`
    - Switch to the latest version of swift `export TOOLCHAINS=swift`
- Install qemu (https://www.qemu.org/download/#macos) or `brew install qemu` if you have qemu
- Check the qemu version `qemu-system-riscv64 --version`

# QEMU targets available

qemu-system-aarch64       qemu-system-mips          qemu-system-s390x
qemu-system-alpha         qemu-system-mips64        qemu-system-sh4
qemu-system-arm           qemu-system-mips64el      qemu-system-sh4eb
qemu-system-avr           qemu-system-mipsel        qemu-system-sparc
qemu-system-cris          qemu-system-nios2         qemu-system-sparc64
qemu-system-hppa          qemu-system-or1k          qemu-system-tricore
qemu-system-i386          qemu-system-ppc           qemu-system-x86_64
qemu-system-loongarch64   qemu-system-ppc64         qemu-system-xtensa
qemu-system-m68k          qemu-system-riscv32       qemu-system-xtensaeb
qemu-system-microblaze    qemu-system-riscv64       
qemu-system-microblazeel  qemu-system-rx            

# Targets available for embedded swift

riscv32-none-none-eabi, riscv64-none-none-eabi, i686-unknown-none-elf, armv7-apple-none-macho, armv6m-none-none-eabi, aarch64-none-none-elf, wasm64-unknown-none-wasm, arm64-apple-macos, i686-unknown-windows-msvc, x86_64-unknown-none-elf, x86_64-unknown-windows-msvc, arm64-apple-none-macho, armv7-none-none-eabi, armv7em-none-none-eabi, arm64e-apple-macos, x86_64-apple-macos, armv6-apple-none-macho, armv6m-apple-none-macho, wasm32-unknown-none-wasm, armv7em-apple-none-macho, armv6-none-none-eabi

# Running commands
swiftc -target riscv32-none-none-eabi -enable-experimental-feature Embedded -wmo main.swift -c -o spark_riscv32
qemu-system-riscv32 -machine virt -nographic -bios none -kernel spark_riscv32