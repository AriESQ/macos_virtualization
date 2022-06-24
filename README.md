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

## Reference

The electric Light Company freeware utilities  
https://eclecticlight.co/downloads/

The Electric Light Company M1 Macs articles  
https://eclecticlight.co/m1-macs/

Investigating sandbox logging  
https://ubrigens.com/posts/sandbox_coverage.html

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
