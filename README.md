# memory_slint

Memory card game written in Rust with the Slint GUI framework, cross-compiled for the LuckFox Pico Ultra W (ARMv7) — renders at 720×720 via the LinuxKMS software backend, no GPU required.

## Key Technologies

- **Target:** LuckFox Pico Ultra W (ARMv7, `armv7-unknown-linux-gnueabihf`)
- **Language:** Rust 2021
- **UI:** Slint 1.14.1 (`backend-linuxkms-noseat`, `renderer-software`)
- **Cross-compilation:** `cross` tool with `ghcr.io/slint-ui/slint/armv7-unknown-linux-gnueabihf` Docker image
- **Build:** Cargo, optimised for binary size (`opt-level="z"`, LTO, strip)

## Getting Started

**Install cross:**
```bash
cargo install cross
```

**Build for LuckFox Pico (hard-float ABI):**
```bash
cross build --target armv7-unknown-linux-gnueabihf --release
```

**Deploy and run on device:**
```bash
scp target/armv7-unknown-linux-gnueabihf/release/memory_slint root@<device>:
ssh root@<device> sudo ./memory_slint
```

---

Built by Owen O'Hehir — embedded Linux, IoT, Matter & Rust consulting at [electronicsconsult.com](https://electronicsconsult.com). Available for contract and consulting work.
