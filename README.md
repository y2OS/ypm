# ypm — y2OS Package Manager
**ypm** is a lightweight, POSIX-compliant package manager originally built for y2OS, but designed to be completely distro-agnostic. It operates entirely without Bash, relying solely on standard UNIX tools.
ypm ensures perfect version isolation, transactional safety, and a "self-hosting" ecosystem.
## Usage & Commands
ypm is designed to be intuitive, fast, and supports batch processing for managing multiple packages and versions simultaneously.
 * **ypm add <package(s)>** or **ypm add <package> <version(s)>**
   Downloads and installs the specified packages. If no version is provided, the latest version is fetched automatically.
 * **ypm use <package> <version>**
   Switches the active system symlinks to the specified version of the package.
 * **ypm del <package(s)>** or **ypm del <package> <version(s)>**
   Completely removes the specified packages or specific versions from the system and local database.
 * **ypm sync [package]**
   Checks the upstream repository for updates and syncs the active packages.
 * **ypm max <count> [package]**
   Sets the maximum number of old versions to retain for a package (or all packages). Older versions are automatically pruned to save disk space.
 * **ypm save <package> <version>**
   Protects a specific version from being automatically deleted by the max limit.
## External Installation (Distro-Agnostic)
ypm can be installed on any external Linux distribution without conflicting with the native package manager. It operates entirely within its own isolated /ypm directory.
You can download the standalone ypm.sh installer script from the official y2TOOL repository:

Make it executable
chmod +x ypm.sh

Move it to your system PATH
sudo mv ypm.sh /usr/bin/ypm

> **Note:** Wget must be installed for the package manager to work. We cannot guarantee that the package manager will work on every device.
> 

## License
Unless otherwise explicitly stated within a specific file or package recipe, all original software, scripts, and documentation in this repository are licensed under the Apache License 2.0.
**Copyright (c) 2026 Yusuf Evran**
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at
http://www.apache.org/licenses/LICENSE-2.0

## Third-Party Software & Licenses

Third-party software installed via ypm recipes retain their original respective licenses as dictated by their upstream developers.

    Recipe Metadata: Every package recipe includes comment blocks or metadata fields pointing to the official upstream repository and its licensing model.

    Package Inclusions: Pre-compiled binaries or packages distributed via ypm stores retain their original license text within their target installation directory (typically under /ypm/pkgs/<package>/<version>/usr/share/licenses/ or the package's root rootfs structure) to respect the authors' intellectual property and maintain compliance with FOSS ethics.
