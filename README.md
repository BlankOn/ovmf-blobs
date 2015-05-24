# UEFI bios for QEMU

## Building

### Preparation

```
git clone https://github.com/tianocore/edk2.git
cd edk2

```

### bios32.bin

```
OvmfPkg/build.sh -a IA32 -n 4
cp Build/OvmfX64/DEBUG_GCC4?/FV/OVMF.fd bios32.bin
```

### bios64.bin

```
OvmfPkg/build.sh -a X64 -n 4
cp Build/OvmfX64/DEBUG_GCC4?/FV/OVMF.fd bios64.bin
```


## Using

### 32-bit UEFI in 64-bit system (emulating BayTrail)

```
qemu-system-x86_64 -bios /path/to/bios32.bin ....<other qemu options>.... 
```

### 64-bit UEFI in 64-bit system

```
qemu-system-x86_64 -bios /path/to/bios64.bin ....<other qemu options>.... 
```

### 32-bit UEFI in 32-bit system (emulating old Macs

```
qemu-system-i386 -bios /path/to/bios32.bin ....<other qemu options>.... 
```
