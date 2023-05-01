# rpioled

This is a daemon to show information on raspberry pi

## Dependencies

```bash
sudo dnf install -y \
    arm-none-eabi-binutils-cs \
    arm-none-eabi-gcc-cs \
    arm-none-eabi-gcc-cs-c++ \
    arm-none-eabi-newlib \
    gcc-arm-linux-gnu \
    "mingw32-32" \
    "mingw64-*"

rustup target add arm-unknown-linux-gnueabihf
rustup target add armv7-unknown-linux-gnueabihf 
```

## Build

```bash
cross build --target=arm-unknown-linux-gnueabihf  
cross build --target=armv7-unknown-linux-gnueabihf  


scp target/arm-unknown-linux-gnueabihf/debug/daemon christian@rp.local:/home/christian/


cross build --target=arm-unknown-linux-gnueabihf --release && scp target/arm-unknown-linux-gnueabihf/release/rpi-oled-daemon christian@rp.local:/home/christian/


```

## References

* <https://chacin.dev/blog/cross-compiling-rust-for-the-raspberry-pi/>
