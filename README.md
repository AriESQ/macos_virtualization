# MacOS Virtualization
Notes on macos virtualization with a focus on running guest OS on Apple M1 Silicon

## Tutorials
https://developer.apple.com/documentation/virtualization/running_macos_in_a_virtual_machine_on_apple_silicon_macs
## macos images
https://mrmacintosh.com/macos-12-monterey-full-installer-database-download-directly-from-apple/

## Docker
Docker corp instructions for running AMD64 linux images on M1 macs using Rosetta.  
https://docs.docker.com/desktop/mac/install/

Simon Willison's Docker on M1 Tutorial  
https://til.simonwillison.net/macos/running-docker-on-remote-m1

Running Macos in a docker container  
https://hakin9.org/docker-osx-run-mac-in-a-docker-container/

Running X64 Linux containers via Podman  
https://edofic.com/posts/2021-09-12-podman-m1-amd64/

## UTM
UTM uses QEMU to run virtual machines (and containers?) on Macos. It can be thought of as a free alternative to Parallels.
https://github.com/utmapp/UTM

## Does QEMU use the new Apple Virtualization framework or the old Apple Hypervisor Framework? 
The context of my question is running X86 virtual machines on Apple Silicon. From what I can tell QEMU does not implement the new Virtualization Framework. The VM app UTM appears to support both QEMU, and then UTM natively supports Apple Virtualization Framework.

https://gitlab.com/qemu-project/qemu/-/blob/master/target/arm/hvf/hvf.c?ref_type=heads


The QEMU changelog is kind of useless, it doesn't appear to be in-repo; and on the website it is broken up over several pages. https://wiki.qemu.org/ChangeLog


Are these docs contradictory?  
* https://lima-vm.io/docs/config/multi-arch/#fast-mode-2
  > Rosetta is known to be much faster than QEMU User Mode Emulation. Rosetta is available for VZ instances on ARM hosts.  
* https://lima-vm.io/docs/config/vmtype/#vz
  > Virtualization.framework doesn’t support running “intel guest on arm” and vice versa


https://wiki.qemu.org/ChangeLog/6.2
> On macOS hosts with Apple Silicon CPUs we now support the 'hvf' accelerator for running AArch64 guests

https://wiki.qemu.org/ChangeLog/8.2
> User-mode emulation
> runtime
> Since this release, qemu linux-user implements and provides vdso for most popular architectures.
> arm/arm64/aarch64

    Emulated /proc/cpuinfo output in linux-user



What is VDSO? Virtual Dynamic Shared Object  
https://www.baeldung.com/linux/vdso-vsyscall-memory-regions 

Why does qemu/target/arm/arm64/aarch64 not exist in QEMU sources? C.f. /qemu/target/i386/hvf(Apple Hypervisor Framework)  

https://gitlab.com/qemu-project/qemu/-/tree/master/target/i386/hvf

## Reference

The electric Light Company freeware utilities  
https://eclecticlight.co/downloads/

The Electric Light Company M1 Macs articles  
https://eclecticlight.co/m1-macs/

Investigating sandbox logging  
https://ubrigens.com/posts/sandbox_coverage.html

VirtIO documentation  
https://docs.oasis-open.org/virtio/virtio/v1.3/virtio-v1.3.html

### Apple Documentation
Hypervisor Documentation  
https://developer.apple.com/documentation/hypervisor

App Sandbox in depth legacy documentation  
https://developer.apple.com/library/archive/documentation/Security/Conceptual/AppSandboxDesignGuide/AppSandboxInDepth/AppSandboxInDepth.html

App Sandbox modern documentation  
https://developer.apple.com/documentation/security/app_sandbox

Code Signing Provisioning Profiles  
https://developer.apple.com/documentation/technotes/tn3125-inside-code-signing-provisioning-profiles

Checking app entitlements  
https://developer.apple.com/library/archive/qa/qa1798/_index.html

Security landing page 
https://developer.apple.com/documentation/security/

macos / Darwin man pages  
https://ss64.com/osx/  
https://keith.github.io/xcode-man-pages/

### Useful Macos Commands
`security` - Command line interface to keychains and Security framework  
https://keith.github.io/xcode-man-pages/security.1.html

`plutil` - Property list utility  
https://keith.github.io/xcode-man-pages/plutil.1.html

`certtool` - Create key pairs, certificates and certificate signing requests for use with Keychains  
https://keith.github.io/xcode-man-pages/certtool.1.html

`codesign` - Create and manipulate code signatures  
https://keith.github.io/xcode-man-pages/codesign.1.html
